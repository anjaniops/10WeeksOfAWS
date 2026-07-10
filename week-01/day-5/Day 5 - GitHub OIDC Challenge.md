# Day 5 - GitHub OIDC Challenge 

Did this one mainly because storing AWS keys in GitHub secrets always bugged me a
little. OIDC gets rid of that entirely - GitHub proves who it is with a short-lived
token, AWS trusts it for a few minutes, done. No keys sitting around anywhere.

## How it actually flows

```
GitHub Actions -> OIDC token -> AWS IAM OIDC Provider -> AWS STS -> temporary creds
```

## What I did

- Added the OIDC provider in IAM (`token.actions.githubusercontent.com`, audience `sts.amazonaws.com`)
- Created a role - `github-oidc-challenge-role` - trusted only by that provider
- Locked the trust policy down to my repo specifically (`anjaniops/10WeeksOfAWS`), so
  no other repo could ever assume this role even if they knew the role ARN
- Wrote the workflow, pushed it, ran it manually

## Result

Ran clean first real attempt. `sts get-caller-identity` came back with the assumed
role, `aws s3 ls` worked, whole job finished in 18 seconds. Zero secrets in the repo.

Run: https://github.com/anjaniops/10WeeksOfAWS/actions/runs/29090935864

## Files

- `oidc/trust-policy.json`
- `.github/workflows/aws-oidc-challenge.yml`

## What clicked for me

The trust policy's `sub` condition is doing all the real work here. It's not enough
that the token came from GitHub - it has to be *this exact repo*. Change one
character in that condition and the whole thing falls apart, which is honestly a
good sign that it's actually enforcing something instead of just being decoration.

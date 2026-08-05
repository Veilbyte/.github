# Veilbyte GitHub Organization configuration checklist

> **v1.1 placement note:** Store Issue Forms in `.github/ISSUE_TEMPLATE/`. A CODEOWNERS file is repository-specific and is not inherited from `Veilbyte/.github`; copy and adapt `CODEOWNERS.template` into `.github/CODEOWNERS` in every repository that needs code-owner reviews. Teams used in CODEOWNERS must be visible and have explicit Write access.

Date: **August 5, 2026**. GitHub UI wording and feature availability may vary by plan and later updates.

## 1. Public `.github` repository

- [ ] Create the public `Veilbyte/.github` repository.
- [ ] Upload this pack.
- [ ] Verify `profile/README.md` appears on the organization page.
- [ ] Complete all contact placeholders.
- [ ] Create teams, then activate `CODEOWNERS`.

## 2. Member privileges

- [ ] Base permissions: **No permission**.
- [ ] Disable repository creation for ordinary members.
- [ ] Allow creation only by the owner and delegated administrators through the available role/process.
- [ ] Disable member repository deletion, transfer, and visibility changes.
- [ ] Disable private-repository forking by default.
- [ ] Limit Pages to approved repositories.

## 3. Authentication

- [ ] Do not enforce organization-wide 2FA initially, per the selected policy.
- [ ] Manually monitor and strongly recommend secure 2FA.
- [ ] The owner must use 2FA and retain offline recovery codes.
- [ ] The owner should configure multiple independent recovery methods.
- [ ] Reassess the sole-owner risk before commercially critical launches.

## 4. Teams

Create `administrators`, `maintainers`, `developers`, `reviewers`, and `security`. Use repository Admin, Maintain, Write, Triage/Read, and narrowly scoped security access respectively. Outside collaborators receive repository-specific access and are not added to teams.

## 5. GitHub Actions

- [ ] Allow Veilbyte actions/reusable workflows and selected verified actions.
- [ ] Pin third-party actions to full commit SHAs where practical.
- [ ] Default workflow token permission: read-only contents.
- [ ] Disable workflow PR creation/approval unless a reviewed automation needs it.
- [ ] Never expose secrets to untrusted fork PR workflows.
- [ ] Limit organization secrets to selected repositories.
- [ ] Use protected environments and required reviewers for release/production.

## 6. Repository defaults

- [ ] Default branch `main`; create `develop`.
- [ ] Enable squash merge and merge commits; disable rebase merge.
- [ ] Automatically delete merged head branches.
- [ ] Enable Issues and, for public user-facing projects, Discussions.
- [ ] Add required files and repository-specific licensing.

## 7. `main` ruleset

- [ ] Active enforcement.
- [ ] Restrict deletion and block force pushes.
- [ ] Require Pull Requests.
- [ ] Default one approval; two for security/network/cryptography/updater/build/release changes.
- [ ] Dismiss stale approvals.
- [ ] Require CODEOWNERS reviews for critical paths.
- [ ] Require resolution of conversations.
- [ ] Require status checks and signed commits.
- [ ] Owner-only bypass with documented reason.

Stable check names: `build`, `test`, `lint`, `format`, `dependency-review`, `secret-scan`, `security-scan`.

## 8. `develop`, release, hotfix, and tags

- [ ] Protect `develop` with PRs, signed commits, checks, no force push, and no deletion.
- [ ] Protect `release/*` and `hotfix/*` from force push and deletion.
- [ ] Protect `v*` tags from unauthorized creation, update, or deletion.
- [ ] Validate SemVer in the release workflow.

## 9. Security features

- [ ] Dependency Graph.
- [ ] Dependabot alerts and security updates.
- [ ] Secret scanning and push protection where available.
- [ ] Code scanning/CodeQL or another SAST.
- [ ] Private vulnerability reporting for public repositories.
- [ ] Completed `SECURITY.md`.

## 10. Licensing and contributions

- [ ] A repository-specific `LICENSE` in every repository.
- [ ] Legal review before using the restricted source template.
- [ ] Use an OSI-approved license for any project described as open source.
- [ ] Preserve CLA confirmation in the PR template.
- [ ] Review dependency and copied-code licenses.

## 11. Quarterly owner audit

Review members, outside collaborators, teams, repository permissions, tokens, deploy keys, GitHub Apps, OAuth Apps, organization/repository/environment secrets, ruleset bypass, archived repositories, and security alerts.

## 12. Archival

After 12 months without meaningful activity, review project status. Publish at least 30 days' notice, identify the last recommended version, revoke secrets and deployment access, define whether continuation forks are permitted, prohibit Veilbyte brand use, and let only the owner archive or transfer the repository.

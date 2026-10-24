# RFC-0008: Roles and review capacity

The team has far more PRs than time to review them: since Oct 10, about
1000 more PRs are opened than merged every day. Each app gets a small
team that reviews and merges its PRs, and maintainers keep the changes
that affect the whole suite.

## Roles

- **Contributor**: anyone with a merged PR. Discord tiers carry no
  repository rights.
- **Triager**: GitHub Triage on one app's repo: labels, closing and
  marking duplicates. The app team appoints triagers.
- **App team member**: GitHub Write on one app's repo; reviews and
  approves its PRs. Each repo lists its team in a pinned issue. Until
  outside members join, an app's team is the maintainers the owners
  assign to it.
- **Maintainer** and **Owner**: as in RFC-0000.

## Merging

- A PR merges automatically with one approval from an app team member or
  maintainer and green required checks.
- An approval doesn't count from the author, or for a PR written by an
  agent the approver ran.
- These also need a maintainer's approval:
  - shared code and tooling;
  - CI, releases and signing;
  - new dependencies and licence changes;
  - security boundaries;
  - changes that break saved files, settings or user data;
  - features or architecture beyond the agreed direction;
  - any PR a maintainer asks to review.
- `CODEOWNERS` assigns the paths tied to these items to the maintainers
  (`craft-app-team`), and the branch ruleset requires code owner review.
- A maintainer can revert any merge, and says why. If the app team
  disagrees, an owner (a storytold org admin, as in RFC-0000) decides.

## Joining a team

- A contributor with 10 merged PRs in an app over at least 4 weeks can
  be nominated to its team.
- Two team members nominate the person on the pinned issue, with the
  reason. While a team has fewer than two members, maintainers nominate.
- Any team member or maintainer can raise a concern within 7 days. A
  concern gives a reason and says what would resolve it. It pauses the
  nomination until it is resolved or a maintainer decides.
- With no open concern after 7 days, the person joins.
- Before the first outside member joins, the app's repo is set up so
  that only maintainers create release tags, release secrets sit behind
  a protected environment, and changes to `CODEOWNERS` need a maintainer.

## Leaving a team

- 60 days without activity in the app ends membership. The person can
  rejoin the same way.
- A maintainer can remove a member, and says why.

## Opening PRs

- Each app repo limits open PRs from users without Write.
- Anyone with fewer than 5 merged PRs in an app gets a team member's
  go-ahead on an issue before opening a feature or large
  refactor PR.

# Preserved development history

The default branch is the maintained source. The tags below preserve earlier source or separate candidates at exact commits.
No archived candidate gains new build, package, or gameplay acceptance through this cleanup.

A tag is a fixed source snapshot. Existing tree URLs and `git clone --branch <name>` can select these tags.
For local inspection, use `git fetch origin --tags` followed by `git switch --detach refs/tags/<name>`.
To resume development, create a temporary branch from the tag. Do not move an archive tag.

| Tag | Preserved commit | Disposition |
|---|---|---|
| `archive/pre-wave2-main-20260831` | [`865579da83338c4ad40758edea16a42dafd014c5`](https://github.com/Alexbeav/duke-nukem-time-to-kill-recomp/tree/865579da83338c4ad40758edea16a42dafd014c5) | Separate historical source; no unrelated-history merge. |

Recorded 2026-09-13. Existing version tags and releases remain unchanged.

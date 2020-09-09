---
name: ADO Release Deployment
about: Request/track the deployment of a release of MMS to Azure DevOps scale units
title: 'ADO Deployment: M {{ env.sprint }}'
labels: 'deployment'
assignees: ''
---

**Note to approver: If this is upgrading Scale Units to a new sprint release, rotateSecrets should be set to true, otherwise set it to false to save time and increase reliability. You should also kick off both Preflight and mms-wcus-0 concurrrently to save time while doing hotfix deployment**

Release: _ADO release url_

Reason: _Sprint deployment or hotfix reason_
  
## Rollout speed (check one)
* [ ] I'm following the Safe Deployment Guidelines below
* [ ] Custom: _explain rollout plan and provide justification_

Progress:

- [ ] Ring 0 AT: Day 1, 9 AM
- [ ] Ring 1 AT: Day 1, 2 PM
- [ ] Ring 0 DT: Day 2, 9 AM
- [ ] Ring 2 AT: Day 2, 9 AM
- [ ] Ring 1 DT: Day 2, 2 PM
- [ ] Ring 3 AT: Day 2, 2 PM
- [ ] Ring 2 DT: Day 3, 9 AM
- [ ] Ring 3 DT: Day 3, 2 PM

## Safe Deployment Guidelines

This applies to both new milestone deployments and hotfix deployments:

* Day 1, 9 AM: Ring 0 binaries
* Day 1, 2 PM: Ring 1 binaries
* Day 2, 9 AM: Ring 2 binaries, Ring 0 DBs
* Day 2, 2 PM: Ring 3 binaries, Ring 1 DBs
* Day 3, 9 AM: Ring 2 DBs
* Day 3, 2 PM: Ring 3 DBs
(Total deploy time: 3 days)

To mitigate a live site incident, we will go faster but that should depend on customer impact. **If there is no customer impact then follow the guidance above.** If we are going to go faster, customer impact should be stated so it is clear to anyone looking at the issue why we did not follow the standard practice. 

## Upon completion

Tell `@chkimes` to update this pinned Slack message: https://github.slack.com/archives/CN97RDQF3/p1590084231365600

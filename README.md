# test-actions
temp for testing github actions

# notes

Env variables:

on push to master:

```
GITHUB_WORKSPACE=/home/runner/work/test-actions/test-actions
GITHUB_REPOSITORY=Kirill888/test-actions
GITHUB_SHA=ee2941207cc3def3ab09fe89473a4a7ade99c643
GITHUB_REF=refs/heads/master
GITHUB_HEAD_REF=
GITHUB_BASE_REF=

GITHUB_EVENT_NAME=push
GITHUB_EVENT_PATH=/home/runner/work/_temp/_github_workflow/event.json
GITHUB_ACTOR=Kirill888

GITHUB_ACTIONS=true
GITHUB_WORKFLOW=CI
GITHUB_ACTION=run4
GITHUB_RUN_NUMBER=11
GITHUB_RUN_ID=64997462
```

### List files that changed since last build

Note: have to checkout sufficient depth in your checkout step

```yaml
    - uses: actions/checkout@v2
      with:
        fetch-depth: 0
```

```bash
git diff --name-only $(jq -r '.before,.after' ${GITHUB_EVENT_PATH})
```

Repro sandbox for debugging actions/cache#1491.

On this **non-default branch**, there's a **tag-triggered** workflow:
https://github.com/zoomin-software/github-actions-cache-repro/actions/workflows/test.yaml

That workflow creates a cache. See existing caches on this URL: https://github.com/zoomin-software/github-actions-cache-repro/actions/caches

Notice from the workflow's logs, how:

1. The build triggered by tag `v5.0` has created a cache under key `CI-cache1.r1.#5.attempt#1 ` visible in web UI (the /actions/caches URL).

2. The build triggered by tag `v5.1` **does not restore** the cache for key `CI-cache1.r1.[…]` which clearly exists in the repo.

https://github.com/zoomin-software/github-actions-cache-repro/actions

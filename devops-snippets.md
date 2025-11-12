---
layout: default
title: DevOps Snippets
---

{% include nav.html %}

# DevOps Snippets

A curated collection of small shell commands, pipeline fragments, and tooling tricks. Replace the examples below with your own frequently used snippets.

## Git Helpers

```bash
# Show branches with recent activity
git for-each-ref --sort=-committerdate refs/heads/ --format='%(refname:short) — %(committerdate:relative)'
```

## CI/CD Templates

```yaml
# Basic GitLab job skeleton
job_template:
  stage: test
  image: registry.gitlab.com/gitlab-org/gitlab-runner:alpine
  script:
    - echo "Replace with real test commands"
```

## Observability Shortcuts

```bash
# Tail logs from the last successful Kubernetes pod
graceful_pod=$(kubectl get pods --sort-by=.status.startTime -o jsonpath='{.items[-1:].metadata.name}')
kubectl logs "$graceful_pod" --follow
```

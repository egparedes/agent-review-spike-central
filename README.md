# agent-review-spike-central

**Throwaway design spike — will be deleted.** A reusable GitHub Actions
workflow (`on: workflow_call`) that runs a sandboxed coding-agent review of a
pull request, packaged so that other repositories call it with a short caller
workflow. Only the `stub` harness is included; it calls no model.

- `.github/workflows/review.yml`: the reusable pipeline (authorize, prepare,
  review, publish).
- `.github/workflows/called-probe.yml`, `called-probe-unpinned.yml`: probes
  of what a called workflow sees (contexts, secrets, token, OIDC claims).
- `.github/workflows/selftest.yml`: this repository's CI, the pipeline end
  to end with the stub harness through a local call.
- `.github/agent-review/`: driver, stub adapter, AWF configuration, prompt.
- `MARKER`: changes between commits, so a caller can prove which commit of
  this repository a run used.

<h1 align="center">
  <a href="https://tracer.cloud" target="_blank">
    <img alt="Tracer" src="https://github.com/user-attachments/assets/5bbbdcee-11ca-4f09-b042-a5259309b7e4" height="80">
  </a>
  <br>
  Tracer Client GitHub Action
</h1>

<p align="center"><b>
  Instantly monitor and optimize your scientific pipelines in GitHub Actions with Tracer.
</b></p>

<p align="center">
  <a href="https://tracer.cloud">Website</a> •
  <a href="https://sandbox.tracer.cloud">Try Sandbox</a> •
  <a href="https://github.com/Tracer-Cloud/tracer-client">Tracer CLI</a>
</p>

---

## Overview

**Tracer** is a system-level observability platform purpose-built for scientific computing and workflow automation.  
This GitHub Action installs the Tracer CLI, enabling you to monitor, analyze, and optimize your pipelines directly within GitHub Actions workflows.

- **Monitor Nextflow, WDL, CWL, Bash, and Python pipelines in CI/CD**
- **Track execution time, cost, and bottlenecks per step**
- **Get instant dashboards for every workflow run**
- **Works out-of-the-box with GitHub-hosted runners**

---

## Quick Start

### 1. Add Tracer to Your GitHub Workflow

```yaml
- name: Install Tracer Client
  uses: Tracer-Cloud/setup-cli@v1
  with:
    tracer_user_id: ${{ secrets.TRACER_USER_ID }} # Optional
    cli_branch: main # Optional, defaults to main
    installer_branch: main # Optional, defaults to main
```

### 2. Monitor Your Pipeline

Add Tracer steps to your workflow to initialize and monitor your pipeline:

```yaml
- name: Initialize Tracer
  run: sudo tracer init

- name: Run your pipeline
  run: nextflow run main.nf # or your workflow command

- name: View Tracer Info
  run: tracer info
```

> **Tip:** All Tracer metrics and logs are available in your [Tracer dashboard](https://sandbox.tracer.cloud).

---

## Why Monitor Pipelines in GitHub Actions with Tracer?

- **End-to-end observability** for scientific and data pipelines
- **Real-time dashboards** for every workflow run
- **Step-level timing and cost analysis**
- **Works with any language or tool (Nextflow, WDL, CWL, Bash, Python, etc.)**
- **No code changes required**—just install and go!

---

## Example Workflow

```yaml
name: Monitor Pipeline with Tracer
on: [push, workflow_dispatch]
jobs:
  tracer:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Install Tracer Client
        uses: Tracer-Cloud/setup-cli@v1
        with:
          tracer_user_id: ${{ secrets.TRACER_USER_ID }}
      - name: Initialize Tracer
        run: sudo tracer init
      - name: Run Pipeline
        run: nextflow run main.nf
      - name: Tracer Info
        run: tracer info
```

---

## Try Tracer with Example Workflows

Looking for ready-to-use pipelines to test Tracer? Check out our curated set of example workflows:

👉 [Nextflow & Bioinformatics Test Pipelines (GitHub Actions)](https://github.com/Tracer-Cloud/nextflow-test-pipelines?tab=readme-ov-file)

These workflows demonstrate Tracer in action across Nextflow, WDL, CWL, and more. Fork or run them directly to see Tracer's observability in your own CI/CD environment!

---

## Security & Privacy

- Tracer runs locally in your workflow runner; your data never leaves your infrastructure unless you choose.
- Enterprise-grade security and compliance.

---

## Key Features

- **Monitor pipelines in GitHub Actions** (SEO: monitor pipelines, GitHub Actions, CI/CD observability)
- **Track time and cost per dataset**
- **Identify bottlenecks and optimize performance**
- **Works with Nextflow, WDL, CWL, Bash, Python, and more**
- **Seamless integration with cloud and on-prem environments**

---

## Resources

- [Tracer Client Documentation](https://github.com/Tracer-Cloud/tracer-client)
- [Tracer Website](https://tracer.cloud)
- [Open an Issue](https://github.com/Tracer-Cloud/setup-cli/issues)

---

## License

This project is licensed under the [GNU GPL v3](./LICENSE).

---

> _Empowering scientists and engineers with DevOps intelligence for the world's most critical challenges._

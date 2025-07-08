# Install Tracer Client GitHub Action

Easily install the Tracer Client in your GitHub Actions workflows. This action sets up the Tracer CLI for use in subsequent workflow steps.

---

## Usage

Add this action to your workflow to install the Tracer Client:

```yaml
- name: Install Tracer Client
  uses: Tracer-Cloud/setup-cli@v1
  with:
    tracer_user_id: ${{ secrets.TRACER_USER_ID }} # Optional
```

### Example Workflow

```yaml
name: Example using Tracer Client
on: [push]
jobs:
  tracer:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Install Tracer Client
        uses: Tracer-Cloud/setup-cli@v1
        with:
          tracer_user_id: ${{ secrets.TRACER_USER_ID }} # Optional
      - name: Use Tracer
        run: tracer info
```

---

## Support

- For questions or issues, please [open an issue](https://github.com/Tracer-Cloud/setup-cli/issues).
- Learn more about Tracer at [https://tracer.cloud](https://tracer.cloud).

---

## License

This project is licensed under the [GNU GPL v3](./LICENSE).

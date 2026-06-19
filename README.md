# Dependabot

**Automated Dependency Update Configurations & Best Practices**

This repository provides ready-to-use Dependabot configurations, templates, and guidance for keeping dependencies up to date across multi-language technical projects — with a focus on the needs of exploratory R&D, AI/agent systems, mesh networking, blockchain, and prototype development.

Part of the **XenoTech / Nexus** technical ecosystem.

## Why This Repo?

Managing dependencies manually across Python, Rust, Docker, GitHub Actions, and other tools is time-consuming and error-prone. Dependabot automates this process by opening pull requests with updates.

This repo helps you:
- Quickly bootstrap Dependabot in new or existing projects
- Use sensible defaults that reduce notification noise
- Apply best practices for grouping, scheduling, and security updates
- Maintain consistency across multiple repositories

## Quick Start

1. Copy the desired `dependabot.yml` example into your project's `.github/` folder
2. Commit and push
3. Dependabot will start creating update PRs according to the schedule

Example:
```bash
git checkout -b add-dependabot
mkdir -p .github
cp examples/github-actions-only.yml .github/dependabot.yml
git add .github/dependabot.yml
git commit -m "ci: add Dependabot configuration"
git push origin add-dependabot
```

Then open a Pull Request.

## Available Configurations

| Example | Description | Best For |
|---------|-------------|----------|
| [github-actions-only.yml](examples/github-actions-only.yml) | Updates only GitHub Actions | Documentation-heavy or workflow-only repos |
| [python-github-actions.yml](examples/python-github-actions.yml) | Python + GitHub Actions | Skills, AI agents, data tools |
| [rust-github-actions.yml](examples/rust-github-actions.yml) | Rust + GitHub Actions | High-performance tools (e.g. Grok Launcher) |
| [full-multi-language.yml](examples/full-multi-language.yml) | Python, Rust, Docker, npm, GitHub Actions | Complex monorepos or full-stack projects |
| [docker-focused.yml](examples/docker-focused.yml) | Docker + GitHub Actions | Containerized deployments |

## Recommended Best Practices

- **Group updates** — Bundle related packages into fewer PRs (reduces noise)
- **Weekly schedule** — Avoid daily spam in active R&D repos
- **Berlin time** — Aligns with Central European development rhythm
- **Security + Version updates** — Dependabot handles both; you can restrict to security-only if preferred
- **Open PR limit** — Set reasonable caps (3–10) to prevent overwhelming the repo
- **Combine with CI** — Require Dependabot PRs to pass your lint/test workflows before merging
- **Review strategically** — Auto-merge patch/minor updates after initial trust is built; keep manual review for major bumps and Actions

## Integration with CI/CD

Pair this with a GitHub Actions CI workflow (see the [xenotech](https://github.com/digitaldesignerjazz/xenotech) repo for a ready example). Recommended pattern:

- Dependabot opens PRs
- CI runs linting, tests, and security scans on the PR
- Branch protection requires green CI before merge

## Customization Tips

You can modify any example to:
- Change `interval` (daily / weekly / monthly)
- Adjust `open-pull-requests-limit`
- Add `target-branch` for update PRs
- Enable `rebase-strategy: auto`
- Add ecosystem-specific settings (e.g. `allow` / `ignore` patterns)

## Future Expansions

Planned additions:
- More ecosystem-specific templates (Go, Terraform, Helm, etc.)
- Scripts for bulk-adding Dependabot to multiple repos
- GitHub App / Action for centralized Dependabot management
- Security-focused minimal configs

## Contributing

Contributions welcome! Especially:
- New high-quality example configurations
- Improvements to existing templates
- Documentation and best-practice guides

Open an issue or pull request with your proposal.

## License

MIT License — see [LICENSE](LICENSE) file.

---

*Maintained as part of the XenoTech technical infrastructure by digitaldesignerjazz / Esslinger & Co.*
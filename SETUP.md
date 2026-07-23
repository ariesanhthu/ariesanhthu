# Setup

This package is intended for the GitHub profile repository:

```text
ariesanhthu/ariesanhthu
```

## Files

```text
README.md
.github/
└── workflows/
    └── update-stats.yml
profile/
└── .gitkeep
```

The workflow will generate these files after its first successful run:

```text
profile/
├── stats.svg
└── top-langs.svg
```

## Install

After cloning `ariesanhthu/ariesanhthu`, copy the contents of this package into
the repository root.

PowerShell example:

```powershell
Copy-Item -Path ".\ariesanhthu-profile-action\*" `
  -Destination ".\ariesanhthu" `
  -Recurse `
  -Force
```

Then commit and push:

```bash
git add README.md .github profile
git commit -m "feat: generate profile statistics with GitHub Actions"
git push origin main
```

The first push should start the workflow because `update-stats.yml` was added or
changed.

You can also run it manually:

1. Open the repository on GitHub.
2. Open **Actions**.
3. Select **Update GitHub Stats**.
4. Select **Run workflow**.
5. Wait for the workflow to finish, then refresh the profile.

## If the workflow cannot push

Open:

```text
Repository → Settings → Actions → General → Workflow permissions
```

Select:

```text
Read and write permissions
```

Then save and run the workflow again.

No Personal Access Token is needed for public repository statistics. The
workflow uses the repository-scoped `GITHUB_TOKEN`.

Private repository statistics are not enabled in this package.

# Push this repository to GitHub

Repository URL:

- `https://github.com/sophierlewis-code/test.git`

## Where to run this

Run these commands in a **Terminal** (or Git Bash) on your own computer,
inside the folder where this repo is cloned.

Example:

```bash
cd /path/to/your/local/test
```

Run these commands from your local machine in this repo:

```bash
cd /workspace/test
git remote remove origin 2>/dev/null || true
git remote add origin https://github.com/sophierlewis-code/test.git
git push -u origin work
```

If GitHub asks for `main` instead of `work`, use:

```bash
cd /workspace/test
git branch -M main
git push -u origin main
```

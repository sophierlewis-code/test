# Push this repository to GitHub

Repository URL:

- `https://github.com/sophierlewis-code/test.git`

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

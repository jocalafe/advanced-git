## Reflog
- Mistakes where made
- Recover commits or branches

```bash
git reflog

### select the state hash before the mistake

git reset --hard <STATE_HASH>

git checkout -b fix-git-mistake <STATE_HASH>
```

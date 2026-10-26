# Docker & CI/CD Debugging Cheatsheet

## 1. Debugging order

1. **Read the error** — find the first meaningful failure.
2. **Check configuration** — `docker compose config`
3. **Check logs** — `docker compose logs`
4. **Check build** — `docker compose build`
5. **Fix one thing at a time** — test again.

## 2. Common errors

| Error | Likely cause | Fix |
|---|---|---|
| `DOCKER_USERNAME` not set | Missing environment variable | Check `.env` |
| `invalid reference format` | Invalid image name | Check `docker compose config` |
| `invalid file request node_modules/...` | Host dependencies included in build | Add `node_modules` to `.dockerignore` |
| Container exits | App or configuration error | Run `docker compose logs` |
| Works locally, fails in CI | Environment or configuration differs | Inspect the failed GitHub Actions step |

## 3. Useful commands

```powershell
docker compose config
docker compose ps
docker compose logs
docker compose build
docker compose up
```

## 4. Remember

- `.gitignore` → Git
- `.dockerignore` → Docker build files
- `.env` → Local Compose variables
- GitHub Actions secrets/variables → CI/CD configuration
- Docker Hub login ≠ setting `DOCKER_USERNAME`

## 5. Record new errors

For each new error, add only:

- **Error:**
- **Cause:**
- **Fix:**


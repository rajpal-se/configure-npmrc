# 📦 Configure `.npmrc` File

This GitHub Action configures an `.npmrc` file for a specific npm scope and registry, supporting both public and private packages. It is especially useful when working with scoped packages hosted on GitHub Packages, npmjs, or custom registries.

## ✨ Features

- Creates a scoped `.npmrc` in your repository
- Supports both public and private registries
- Adds authentication token for private registries
- Outputs path to generated `.npmrc` for further use in the workflow

## 👤 Author

**Rajpal Singh**

---

## 🛠️ Inputs

| Name              | Description                                                                 | Required | Default                       |
| ----------------- | --------------------------------------------------------------------------- | -------- | ----------------------------- |
| `scope`           | Scope to configure (e.g. `@myorg`)                                          | ✅ Yes   | —                             |
| `registry`        | Registry URL to use for the given scope                                     | ❌ No    | `https://npm.pkg.github.com/` |
| `authToken`       | Authentication token for accessing private registries                       | ✅ Yes   | —                             |
| `directory`       | Directory where the `.npmrc` file will be created                           | ❌ No    | `./`                          |
| `registryAuthUrl` | Registry Auth URL (used for authentication, without protocol)               | ❌ No    | `//npm.pkg.github.com/`       |
| `public`          | Whether the registry is public (set to `"true"` to skip writing auth token) | ❌ No    | `"false"`                     |

---

## 🚀 Usage

Add the following step to your GitHub Actions workflow:

```yaml
- name: Configure .npmrc
  uses: your-username/configure-npmrc-action@v1
  with:
    scope: "@myorg"
    authToken: ${{ secrets.NPM_TOKEN }}
```

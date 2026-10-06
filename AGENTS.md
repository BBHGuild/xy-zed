# AI Agent Guidelines & Repository Workflow

## Repository Context

This repository is a fork of [`zarifpour/xy-zed`](https://github.com/zarifpour/xy-zed) maintained by [`BBHGuild`](https://github.com/BBHGuild). It provides the **XY-Zed** theme extension for the [Zed](https://zed.dev) editor.

### Remotes

* **`origin`**: `git@github.com:BBHGuild/xy-zed.git` (Fork — all pushes go here)
* **`upstream`**: `https://github.com/zarifpour/xy-zed.git` (Original upstream author — read/fetch only)

---

## Branch Strategy

* **`light-theme`** *(default working branch)*:
  * Contains the custom fork changes (including the Light mode theme variant).
  * **Always push changes to this branch**: `git push origin light-theme`.
* **`main`**:
  * Clean mirror of `upstream/main`.
  * **Never commit custom fork changes directly to `main`**.

---

## Git Operations

### Pushing Changes
Whenever making changes to the theme or repository:
1. Verify you are on `light-theme`: `git branch --show-current`
2. Commit your changes: `git commit -m "..."`
3. Push to the fork: `git push origin light-theme`

### Syncing Upstream Updates
When the original author updates `upstream/main`:
1. Update local `main`:
   ```bash
   git checkout main
   git pull upstream main
   git push origin main
   ```
2. Merge into the working branch:
   ```bash
   git checkout light-theme
   git merge main
   git push origin light-theme
   ```

---

## Project Structure

* `extension.toml`: Extension manifest (ID, version, metadata).
* `themes/xy-zed.json`: The theme definition file containing colors, token styles, and UI theme rules.
* `public/`: Logos and preview screenshots.

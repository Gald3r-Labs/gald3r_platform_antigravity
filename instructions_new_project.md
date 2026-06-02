# Starting a New Project with Gald3r (Antigravity)

Set up a brand-new project with gald3r pre-installed for **Antigravity**.

For an existing project, see [instructions_existing_project.md](./instructions_existing_project.md).

---

## Step 1 - Get this repo

```bash
git clone https://github.com/wrm3/gald3r_platform_antigravity.git
```

Or download the ZIP from GitHub (**Code -> Download ZIP**) and unzip it.

---

## Step 2 - Copy the `antigravity/` contents into your new project

**bash / macOS / Linux:**
```bash
mkdir my-new-project
cp -r gald3r_platform_antigravity/antigravity/. my-new-project/
cd my-new-project
```

**Windows PowerShell:**
```powershell
New-Item -ItemType Directory my-new-project
Copy-Item -Recurse -Force .\gald3r_platform_antigravity\antigravity\* .\my-new-project\
Set-Location .\my-new-project
```

---

## Step 3 - Open in Antigravity

Open the project folder in Antigravity. gald3r auto-loads on first launch.

---

## Step 4 - Verify

In Antigravity, type `@g-status` -- you should see a gald3r session-context block.

---

*Full docs: [README.md](./README.md) | [CHANGELOG.md](./CHANGELOG.md) | [all 34 tools](https://github.com/wrm3/gald3r)*

# OpenCode Setup – Skills, MCP Servers and Plugins

Overview of a reusable OpenCode configuration: installed skills, configured MCP
servers, and plugins.

## Layout

- MCP configuration: `~/.config/opencode/opencode.json`
- Skills: `~/.agents/skills/` (tracked by `~/.agents/.skill-lock.json`)
- Plugins: managed via `opencode plugin`

## MCP Servers

| Server | Type | Purpose |
|---|---|---|
| `context7` | remote | Up-to-date documentation and code examples for libraries and frameworks |
| `playwright` | local | Browser automation via Playwright MCP (uses a local browser executable) |
| OpenCode (built-in) | built-in | Session/worktree/model management and MCP resource access |

Example `opencode.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "context7": {
      "type": "remote",
      "url": "https://mcp.context7.com/mcp/oauth",
      "enabled": true
    },
    "playwright": {
      "type": "local",
      "command": ["npx", "@playwright/mcp@latest"],
      "enabled": true
    }
  }
}
```

## Plugins

No plugins are currently installed. Manage with:

```bash
opencode plugin list
opencode plugin add <package>
opencode plugin remove <package>
```

## Skills (32)

### Caveman / communication compression (16)

| Skill | Purpose | Source |
|---|---|---|
| `cavecrew` | Delegate to investigator/builder/reviewer with compressed output | JuliusBrussee/caveman |
| `caveman` | Terse caveman voice (`/caveman`) | JuliusBrussee/caveman |
| `caveman-commit` | Conventional Commits messages | JuliusBrussee/caveman |
| `caveman-compress` | Compress memory files (CLAUDE.md, todos) | JuliusBrussee/caveman |
| `caveman-discover` | Label LLM workflows in a repo | JuliusBrussee/caveman |
| `caveman-evidence-review` | Read-only review of Caveman Cloud evidence | JuliusBrussee/caveman |
| `caveman-explore` | Read-only repository explorer | JuliusBrussee/caveman |
| `caveman-help` | Caveman mode reference | JuliusBrussee/caveman |
| `caveman-learn` | Apply suggestions from a learn report | JuliusBrussee/caveman |
| `caveman-manage` | Manage Caveman Cloud experiments | JuliusBrussee/caveman |
| `caveman-optimize` | Evaluate an optimization observation | JuliusBrussee/caveman |
| `caveman-review` | Compressed code review | JuliusBrussee/caveman |
| `caveman-setup` | Wire a repo through the Caveman gateway | JuliusBrussee/caveman |
| `caveman-stats` | Token and mode statistics | JuliusBrussee/caveman |
| `megacave` | Caveman in wenyan (Classical Chinese) | JuliusBrussee/caveman |
| `ultracave` | Maximum compression | JuliusBrussee/caveman |

### Ponytail (6)

| Skill | Purpose | Source |
|---|---|---|
| `ponytail` | Lazy senior dev: smallest change that solves the task | dietrichgebert/ponytail |
| `ponytail-audit` | Whole-repo quality audit | dietrichgebert/ponytail |
| `ponytail-debt` | List `shortcut:`/`ponytail:` comments | dietrichgebert/ponytail |
| `ponytail-gain` | Show benchmark savings | dietrichgebert/ponytail |
| `ponytail-help` | Ponytail reference | dietrichgebert/ponytail |
| `ponytail-review` | Review a change | dietrichgebert/ponytail |

### Development workflow (6)

| Skill | Purpose | Source |
|---|---|---|
| `investigate-first` | Diagnose before editing | JuliusBrussee/caveman |
| `lean-build` | Narrow end-to-end feature implementation | JuliusBrussee/caveman |
| `migration` | Safe schema/data/API migrations | JuliusBrussee/caveman |
| `safe-refactor` | Behavior-preserving refactoring | JuliusBrussee/caveman |
| `surgical-patch` | Narrow bug fix | JuliusBrussee/caveman |
| `verify-and-stop` | Verify without expanding scope | JuliusBrussee/caveman |

### Design (1)

| Skill | Purpose | Source |
|---|---|---|
| `frontend-design` | Distinctive, intentional UI design | anthropics/skills |

### Security (2)

| Skill | Purpose | Source |
|---|---|---|
| `security-review` | Security checklist and patterns | affaan-m/ECC |
| `security-scan` | Audit `.claude` configuration | affaan-m/ECC |

### Library documentation (1)

| Skill | Purpose | Source |
|---|---|---|
| `context7-mcp` | Library/framework docs via Context7 MCP | local (not tracked in skill-lock) |

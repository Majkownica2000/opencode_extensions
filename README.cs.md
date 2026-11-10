# OpenCode Setup – Skills, MCP servery a pluginy

Přehled znovupoužitelné konfigurace OpenCode: nainstalované skills, nakonfigurované MCP
servery a pluginy.

## Rozložení

- Konfigurace MCP: `~/.config/opencode/opencode.json`
- Skills: `~/.agents/skills/` (sledováno souborem `~/.agents/.skill-lock.json`)
- Pluginy: spravováno přes `opencode plugin`

## MCP servery

| Server | Typ | Účel |
|---|---|---|
| `context7` | remote | Aktuální dokumentace a ukázky kódu pro knihovny a frameworky |
| `playwright` | local | Automatizace prohlížeče přes Playwright MCP (používá lokální spustitelný soubor prohlížeče) |
| OpenCode (vestavěný) | built-in | Správa sessions/worktree/modelů a přístup k MCP zdrojům |

Příklad `opencode.json`:

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

## Pluginy

Žádné pluginy nejsou momentálně nainstalovány. Správa:

```bash
opencode plugin list
opencode plugin add <package>
opencode plugin remove <package>
```

## Skills (32)

### Caveman / kompresní komunikace (16)

| Skill | Účel | Zdroj |
|---|---|---|
| `cavecrew` | Delegace na investigator/builder/reviewer s komprimovaným výstupem | JuliusBrussee/caveman |
| `caveman` | Stručný caveman hlas (`/caveman`) | JuliusBrussee/caveman |
| `caveman-commit` | Zprávy Conventional Commits | JuliusBrussee/caveman |
| `caveman-compress` | Kompresní paměťové soubory (CLAUDE.md, todos) | JuliusBrussee/caveman |
| `caveman-discover` | Označení LLM workflow v repozitáři | JuliusBrussee/caveman |
| `caveman-evidence-review` | Read-only přehled Caveman Cloud evidence | JuliusBrussee/caveman |
| `caveman-explore` | Read-only průzkumník repozitáře | JuliusBrussee/caveman |
| `caveman-help` | Referenční karta režimu caveman | JuliusBrussee/caveman |
| `caveman-learn` | Aplikace návrhů z learn reportu | JuliusBrussee/caveman |
| `caveman-manage` | Správa Caveman Cloud experimentů | JuliusBrussee/caveman |
| `caveman-optimize` | Vyhodnocení optimalizačního pozorování | JuliusBrussee/caveman |
| `caveman-review` | Kompresní review kódu | JuliusBrussee/caveman |
| `caveman-setup` | Zapojení repa přes Caveman gateway | JuliusBrussee/caveman |
| `caveman-stats` | Statistiky tokenů a režimů | JuliusBrussee/caveman |
| `megacave` | Caveman ve wenyan (klasická čínština) | JuliusBrussee/caveman |
| `ultracave` | Maximální komprese | JuliusBrussee/caveman |

### Ponytail (6)

| Skill | Účel | Zdroj |
|---|---|---|
| `ponytail` | Líný senior dev: nejmenší změna, která úkol vyřeší | dietrichgebert/ponytail |
| `ponytail-audit` | Audit kvality celého repa | dietrichgebert/ponytail |
| `ponytail-debt` | Výpis komentářů `shortcut:`/`ponytail:` | dietrichgebert/ponytail |
| `ponytail-gain` | Zobrazení úspor z benchmarku | dietrichgebert/ponytail |
| `ponytail-help` | Referenční karta ponytail | dietrichgebert/ponytail |
| `ponytail-review` | Review změny | dietrichgebert/ponytail |

### Vývojový workflow (6)

| Skill | Účel | Zdroj |
|---|---|---|
| `investigate-first` | Diagnostika před úpravou | JuliusBrussee/caveman |
| `lean-build` | Úzká end-to-end implementace funkce | JuliusBrussee/caveman |
| `migration` | Bezpečné migrace schématu/dat/API | JuliusBrussee/caveman |
| `safe-refactor` | Refaktoring zachovávající chování | JuliusBrussee/caveman |
| `surgical-patch` | Úzká oprava chyby | JuliusBrussee/caveman |
| `verify-and-stop` | Ověření bez rozšiřování rozsahu | JuliusBrussee/caveman |

### Design (1)

| Skill | Účel | Zdroj |
|---|---|---|
| `frontend-design` | Výrazný, záměrný UI design | anthropics/skills |

### Security (2)

| Skill | Účel | Zdroj |
|---|---|---|
| `security-review` | Security checklist a vzory | affaan-m/ECC |
| `security-scan` | Audit konfigurace `.claude` | affaan-m/ECC |

### Dokumentace knihoven (1)

| Skill | Účel | Zdroj |
|---|---|---|
| `context7-mcp` | Dokumentace knihoven/frameworků přes Context7 MCP | local (nesledováno v skill-lock) |

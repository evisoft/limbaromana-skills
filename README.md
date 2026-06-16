# limbaromana

Plugin [Claude Code](https://docs.claude.com/en/docs/claude-code) cu skill-uri pentru limba română.

Plugin-ul grupează trei *Agent Skills*, fiecare în propriul director sub `skills/`, cu un fișier `SKILL.md` (frontmatter `name` + `description` și instrucțiunile aferente).

## Skill-uri incluse

| Skill | Invocare | Descriere |
|-------|----------|-----------|
| `profesor-roman` | `/limbaromana:profesor-roman` | Corector intransigent de limba română — verifică gramatică, ortografie, diacritice, stil, cacofonii și pleonasme. Se activează la „verifică", „corectează", „greșeli", „diacritice", „ortografie", „gramatică". |
| `poet-roman` | `/limbaromana:poet-roman` | Generator de poezie în limba română — versuri, rimă, strofe, în context educațional, creativ sau literar. Se activează la „poezie", „versuri", „poem", „rimă", „strofă". |
| `scriitor-roman` | `/limbaromana:scriitor-roman` | Generator de proză literară în limba română — povestiri, basme, texte narative. Se activează la „povestire", „proză", „basm", „text narativ". |

## Instalare ca plugin

În Claude Code, adaugă repository-ul ca marketplace și instalează plugin-ul:

```
/plugin marketplace add evisoft/limbaromana
/plugin install limbaromana@limbaromana
```

Skill-urile devin disponibile imediat și se activează automat când contextul conversației se potrivește cu descrierea lor (vezi cuvintele-cheie din tabel). Pot fi invocate și explicit, prin numele namespace-uit `/limbaromana:<skill>`.

## Instalare manuală (fără plugin)

Dacă preferi să copiezi skill-urile direct în folderul tău de skill-uri:

```bash
git clone https://github.com/evisoft/limbaromana.git
for s in profesor-roman poet-roman scriitor-roman; do
  cp -r "limbaromana/skills/$s" ~/.claude/skills/
done
```

## Structură

```
limbaromana/
├── .claude-plugin/
│   ├── plugin.json        # manifest plugin
│   └── marketplace.json   # definiție marketplace (pentru instalare directă din repo)
└── skills/
    ├── profesor-roman/SKILL.md
    ├── poet-roman/SKILL.md
    └── scriitor-roman/SKILL.md
```

## Licență

[MIT](LICENSE)

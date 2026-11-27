# LegalMike for Claude and ChatGPT

**Make your case.** From legal question to your advice, with the sources to back it.

[LegalMike](https://legalmike.ai) researches Dutch and EU law from primary
sources: case law, legislation, disciplinary law, local regulations, EU law,
ECHR case law, dispute committees, parliamentary papers and legal literature.
Every answer links each ruling and article it relies on, so a lawyer can open
the source and verify it.

This repository contains the LegalMike plugin. It connects your AI assistant to
the LegalMike service and adds two skills:

| Skill | What it does |
|---|---|
| `legal-research` | Researches a question of Dutch or EU law and presents LegalMike's answer with every source linked. |
| `check-citations` | Checks the ECLIs, articles and claims in a draft against the sources, one verdict per reference. |

## Install

**Claude** (claude.ai, Claude Desktop, Cowork): Customize → Plugins → Add
marketplace, then enter `LegalMikeAI/legalmike-plugins`.

**Claude Code:**

```
/plugin marketplace add LegalMikeAI/legalmike-plugins
/plugin install legalmike@legalmike
```

**ChatGPT:** coming to the ChatGPT plugin directory.

On first use you sign in with your LegalMike account. No account yet? See
[legalmike.ai](https://legalmike.ai).

## Using it

Ask a legal question in your assistant, in Dutch or English. For example:

- *Wanneer verjaart een vordering tot schadevergoeding uit onrechtmatige daad?*
- *Mag een werkgever een zieke werknemer ontslaan?*
- *Check the citations in this memo.*

Answers are in Dutch by default; ask for English and the analysis is written in
English, while quoted statutory and judicial text stays in Dutch.

## Legal research, not legal advice

LegalMike provides legal research from public sources, made with AI. Its
answers are a starting point for review by a qualified lawyer and are not
legal advice.

## Privacy and terms

- Privacy statement: https://legalmike.ai/privacyverklaring/
- Terms of use: https://legalmike.ai/gebruiksvoorwaarden/
- Support: https://legalmike.ai/support/ or info@legalmike.ai

## License

Proprietary. You may use this plugin with the LegalMike service; see
[LICENSE](LICENSE). © Novitec B.V., trading as LegalMike.

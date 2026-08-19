# Skills

De 20 skills fra [The Automation Playbook for Claude](../../the-automation-playbook-for-claude.md), udtrukket fra guiden og lagt i det layout Claude Code læser: én mappe per skill med en `SKILL.md`.

Artiklen beskriver claude.ai-vejen — zip mappen, upload under Customize → Skills. Den er unødvendig her. Claude Code læser `.claude/skills/<navn>/SKILL.md` direkte fra repoet, så filerne er aktive i enhver session i dette repo uden yderligere opsætning.

## De fem stadier

| Stadie | Spørgsmålet det afgør | Skills |
| --- | --- | --- |
| 1. Map | Hvad er arbejdet, trin for trin, og hvor går timerne? | `process-mapper`, `task-inventory`, `bottleneck-finder`, `data-readiness-checker` |
| 2. Score | Hvilken kandidat er den ene, der er værd at bygge? | `impact-scorer`, `feasibility-rater`, `roi-modeler`, `risk-screener` |
| 3. Build | Hvad bliver der præcis leveret, og hvordan ved vi, det virker? | `workflow-architect`, `agent-spec-writer`, `integration-mapper`, `test-case-generator` |
| 4. Deploy | Hvem kører det, hvad sker der når det knækker, og bruger nogen det? | `rollout-sequencer`, `sop-rewriter`, `owner-escalation-designer`, `adoption-tracker` |
| 5. Prove | Hvad gav det, og kan tallet forsvares? | `baseline-capturer`, `kpi-architect`, `savings-auditor`, `board-memo-writer` |

`baseline-capturer` hører til stadie 5 efter formål, men skal køres i stadie 2 efter timing. Måler du ikke før bygningen, kan du ikke måle bagefter.

## Brug

Kald en skill direkte med `/process-mapper`, eller beskriv opgaven og lad Claude matche mod `description`-linjen. Direkte kald er bedst i starten, så du ved hvilken skill der producerede hvilket output.

Skal de være tilgængelige i alle repoer og ikke kun dette, så kopiér mapperne til `~/.claude/skills/`.

## Ændringer i forhold til guiden

Ingen. Filerne er gengivet som de står i artiklen, med `name` og `description` i frontmatter. Claude Code understøtter også `allowed-tools` — det er ikke tilføjet, da ingen af de 20 er skrevet til at bruge værktøjer endnu.

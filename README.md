# FuldaHPC: High-Performance Computing at Hochschule Fulda

This organization collects the research, teaching, and administrative repositories of the HPC group at Hochschule Fulda – University of Applied Sciences.

All repositories sit side by side on one level. There are no nested folders or sub-organizations: the **repository name** and its **GitHub topics** carry all the structure, and both follow the rules below.

## 1. Repository Categories

| Category    | Name pattern                               | Example                            | Required topics                                          |
| ----------- | ------------------------------------------ | ---------------------------------- | -------------------------------------------------------- |
| `paper`     | `paper-<venue><year>-<slug>`               | `paper-eurompi26-coll-tuning`      | `paper`, `<venue>`, `<year>`, `<research-area>`          |
| `artifact`  | `artifact-<venue><year>-<slug>`            | `artifact-eurompi26-coll-tuning`   | `artifact`, `<venue>`, `<year>`, `<research-area>`       |
| `benchmark` | `benchmark-<venue><year>-<slug>`           | `benchmark-sc26-malleable-jobs`    | `benchmark`, `<venue>`, `<year>`, `<research-area>`      |
| `talk`      | `talk-<event><year>-<slug>`                | `talk-isc26-task-runtimes`         | `talk`, `<event>`, `<year>`, `<research-area>`           |
| `poster`    | `poster-<event><year>-<slug>`              | `poster-sc26-src-jane-doe`         | `poster`, `<event>`, `<year>`, `<research-area>`         |
| `workshop`  | `workshop-<event><year>`                   | `workshop-amte26`                  | `workshop`, `<event>`, `<year>`                          |
| `proposal`  | `proposal-<funding-org><year>-<slug>`      | `proposal-dfg26-adaptive-resources`| `proposal`, `<funding-org>`, `<year>`, `<research-area>` |
| `grant`     | `grant-<funding-org><year>-<slug>`         | `grant-dfg27-adaptive-resources`   | `grant`, `<funding-org>`, `<year>`, `<research-area>`    |
| `tool`      | `tool-<slug>`                              | `tool-edumpi`                      | `tool`, `<research-area>`                                |
| `topic`     | `topic-<slug>`                             | `topic-mpi-sessions`               | `topic`, `<research-area>`                               |
| `teaching`  | `teaching-<course>-<semester>-<slug>`      | `teaching-pp-ws26-exercises`       | `teaching`, `<course>`, `<semester>`, `<research-area>`  |
| `teaching`  | `teaching-<thesis>-<year>-<name>`          | `teaching-ma-26-jane-doe`          | `teaching`, `<thesis>`, `<year>`, `<research-area>`      |
| `infra`     | `infra-<slug>`                             | `infra-linuxlab`                   | `infra`                                                  |
| `protocol`  | `protocol-<date>-<slug>`                   | `protocol-2026-11-04-dfg-kickoff`  | `protocol`, `<date>`, `<research-area>`                  |
| `cv`        | `cv-<name>`                                | `cv-jane-doe`                      | `cv`                                                     |
| `travel`    | `travel-<year>-<destination>-<slug>`       | `travel-26-hamburg-isc`            | `travel`, `<year>`, `<destination>`                      |
| `template`  | `template-<slug>`                          | `template-thesis`                  | `template`                                               |
| `misc`      | `misc-<slug>`                              | `misc-headshots`                   | optional                                                 |

**Notes on categories**

- `tool` is for long-lived software that outlives any single paper (e.g., research tools, teaching systems). Paper-specific code belongs in `artifact-*`.
- `workshop` is for workshops we organize: CFP, website sources, program, and organizational material. Review content never goes into these repositories.
- `infra` is for configuration and deployment of systems we operate (teaching clusters, GPU servers, platforms for students).
- `template` is for reusable starting points (thesis, meeting logs, AI rules). Mark these repositories as GitHub template repositories where possible.
- `misc` is the last resort. If several `misc-*` repositories share a purpose, give them their own category.

## 2. Naming Rules

The same rules apply to every identifier in this organization, whether repository name, topic, or slug:

- lowercase only
- words separated by hyphens; no spaces, no underscores
- short, descriptive, and stable over time

Keeping names this uniform makes them easy to filter, script against, and archive.

### Vocabulary

**Categories**

```
paper | artifact | benchmark | talk | poster | workshop | proposal | grant | tool | topic | teaching | infra | template | protocol | cv | travel | misc
```

**`<venue>`**: acronym of a conference or journal.

```
sc, isc, europar, ipdps, cluster, eurompi, ppam, wamta, tpds, jpdc, fgcs
```

**`<event>`**: any event code, including venue acronyms, workshops, and poster tracks.

```
sc, isc, europar, amte, pmbs, eesp, sc-src
```

**`<funding-org>`**: acronym of the funding body.

```
dfg, bmftr, hmwk, eu, hsf
```

**`<course>`**: course acronym as used internally.

```
pp, hpc, llm-agents
```

**`<semester>`**: `ssYY` (summer) or `wsYY` (winter).

```
ss26, ws26
```

**`<thesis>`**: thesis type.

```
ba, ma
```

**`<name>`**: first and last name.

```
jane-doe
```

**`<year>`**: two digits.

```
25, 26, 27
```

**`<date>`**: ISO 8601 (`YYYY-MM-DD`).

```
2026-11-04
```

**`<destination>`**: full city name, hyphenated; abbreviations only if globally unambiguous.

```
hamburg, st-louis, new-york, hong-kong
```

**`<slug>`**: a short, readable label for the specific content of the repository.

```
coll-tuning, adaptive-resources, task-runtimes
```

**`<research-area>`**: one or more values from this fixed list:

| Value                     | Scope                                                              |
| ------------------------- | ------------------------------------------------------------------ |
| `programming-models`      | MPI, OpenMP, CUDA, and other parallel programming models           |
| `runtime-systems`         | task-based and asynchronous many-task runtimes                     |
| `resource-management`     | scheduling, malleability, dynamic and adaptive resources           |
| `io-storage`              | parallel I/O and storage systems                                   |
| `performance-engineering` | benchmarking, profiling, performance modeling, reproducibility     |
| `hpc-education`           | teaching tools, course material, and HPC didactics                 |

Use as few values as needed. If none fits, talk to the organization admins before creating the repository.

## 3. Topics

Topics are **mandatory** and are the **only** way to express hierarchy.

- They follow the naming rules above.
- Only values from the vocabulary above are allowed; do not invent new ones.
- A topic should still make sense in five years.

## 4. Visibility

New repositories are **private**. Making a repository public needs a reason, such as a published artifact, released tool, or public teaching material.

### Ruleset for Public Repositories

Every public repository protects `main` with a ruleset named **`main-protection`**, configured exactly as follows:

- **Bypass:** organization admins
- **Target:** branch pattern `main`
- **Rules:**
  - restrict deletions
  - require linear history
  - require a pull request before merging, with
    - 1 required approval
    - stale approvals dismissed on new commits
    - review from code owners
    - approval of the most recent push
    - all conversations resolved
    - merge methods limited to squash and rebase
  - block force pushes

## 5. The `.github` Repository

`.github` holds the organization-wide defaults:

- this README (`profile/README.md`)
- issue and pull request templates
- contribution guidelines, where needed

## 6. Repository Hygiene

A repository is a **record**, not a scratch space. Anyone opening it later, whether a student, reviewer, or funder, should understand it without asking.

Examples of what this means in practice:

- **`paper-*`**
  - small, meaningful commits
  - Git tags for every submitted, revised, and accepted version, with the reviews stored alongside
  - the current compiled PDF is committed and always matches the sources
- **`artifact-*` and `benchmark-*`**
  - experiments are scripted end to end and can be rerun on another system without manual steps
  - results are stored together with the exact configuration that produced them

These are examples, not a complete list. The same standard applies to every category.

## 7. Meeting Logs

Supervision and project meetings use a shared Markdown template, one file per meeting, so that decisions and tasks stay traceable.

Template: [`template-meeting-log`](https://github.com/FuldaHPC/template-meeting-log)

`paper-*` and `teaching-*` repositories use this template unless a documented reason says otherwise.

## 8. AI Coding Assistants

Shared rules for AI coding assistants (e.g., Claude Code, Cursor) live in [`template-ai-rules`](https://github.com/FuldaHPC/template-ai-rules). Reference them in your editor to keep language, style, and editing conventions consistent across projects.

## 9. Why This Structure

The scheme is meant to:

- work across many years and many projects
- survive students and staff coming and going
- be readable by reviewers, students, and funding agencies
- replace implicit knowledge and ad-hoc names with explicit rules

When a repository doesn't fit, we change the scheme, not the repository.

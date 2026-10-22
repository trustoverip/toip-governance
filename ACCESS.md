# Trust over IP — team access to repositories

## Bottom line up front

- `config.yaml` at `7280235` defines **46 teams**, **64 repositories** (all public) and **104 team-to-repository grants** covering **41 distinct people**: 51 `admin`, 43 `maintain`, 10 `write`.
- **5 of the 64 managed repositories are empty** — created on GitHub and never pushed to: `kswg-main-glossary`, `tswg-did-method-webs-specification`, `dtgwg-ux-tf`, `dtgwg-rcards-tf`, `aimwg-tsp-enabled-ai-agent-protocols`.
- **2 teams hold no repository at all** (`kswg-suc`, `ufwg`) — both are `m00sey` alone, so the config carries them without granting anything.
- **4 repositories have no `teams:` key**, so no team has access and only org owners can reach them: `dtgwg-ux-tf`, `tswg-trust-registry-query-language`, `vLEI-EGF-3.0-Annual-Update-Public-Review`, `vLEI-EGF-4.0-Annual-Update-Public-Review`.
- Access is concentrated: `dtgwg-maintainers` (16 repos), `dtgwg-admins` (15) and `tswg` (10) carry **40 of the 104 grants**, while 29 teams hold exactly one repository each.
- Every team holds exactly **one** permission level across every repository it is granted on, so the one-level-per-team rule is clean. Fourteen team names do not state the level they grant.

## Scope and method

Access below is **only** what `config.yaml` declares; CLOWarden applies it to the `trustoverip` org. Org owners and GitHub-side direct collaborator grants are outside this file and are not shown. Emptiness is not expressible in the config, so it was read from GitHub's REST API read-only on 2026-10-22: a repository is called empty when `GET /repos/trustoverip/<name>/commits` returns `409 Git Repository is empty` and `size` is `0`.

`CODEOWNERS` restricts changes to this file to `@trustoverip/lfstaff` and `@trustoverip/toip-admins`.

## Access by repository

`—` means the repository declares no teams.

| Repository | admin | maintain | write | Teams | Notes |
|---|---|---|---|---|---|
| `.github` | `toip-admins` |  |  | 1 |  |
| `aimwg-agent-fiduciary-duties` | `aimwg-agent-fiduciary-duties-admins` | `aimwg-agent-fiduciary-duties-maintainers` |  | 2 |  |
| `aimwg-tmcp-specification` | `aimwg-tmcp-specification-admins` | `tswg-aimt-tf` |  | 2 |  |
| `aimwg-trust-enabled-agents` | `aimwg-tsp-enabled-ai-agent-protocols-admins` |  |  | 1 |  |
| `aimwg-tsp-enabled-ai-agent-protocols` | `aimwg-tsp-enabled-ai-agent-protocols-admins` |  |  | 1 | **empty** (created 2026-08-25, never pushed) |
| `credential-exchange-protocols` | `credential-exchange-protocols-admins` |  | `tswg-cep-tf` | 2 |  |
| `ctwg-general-glossary` | `ctwg-admins` |  |  | 1 |  |
| `ctwg-main-glossary` | `ctwg-admins`, `ctwg-main-glossary-admins` |  |  | 2 |  |
| `ctwg-terminology-governance-guide` | `ctwg-admins` |  |  | 1 |  |
| `dtgwg-agent-names-spec` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-agent-names-tf` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-cred-spec` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-cred-tf` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-general` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-htx-tf` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-rahp-tf` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-rcards-tf` |  | `dtgwg-maintainers` |  | 1 | **empty** (created 2026-07-30, never pushed) |
| `dtgwg-trust-tasks-spec` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-trust-tasks-tf` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-ux-tf` |  |  |  | — | **empty** (created 2026-07-23, never pushed); **no team access** |
| `dtgwg-vds-spec` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-vds-tf` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-vsc-registry` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-vti-spec` | `dtgwg-admins` | `dtgwg-maintainers` |  | 2 |  |
| `dtgwg-zkp-spec` | `dtgwg-admins`, `dtgwg-zkp-tf-admins` | `dtgwg-maintainers` |  | 3 |  |
| `dtgwg-zkp-tf` | `dtgwg-admins`, `dtgwg-zkp-tf-admins` | `dtgwg-maintainers` |  | 3 |  |
| `EasyCLA` | `toip-admins` | `lfstaff` |  | 2 |  |
| `egwg-governance-metamodel` |  | `egwg-learning-pathways-wg` |  | 1 |  |
| `egwg-learning-pathways` |  | `egwg-learning-pathways-wg` |  | 1 |  |
| `egwg-reporting-tf-prototype-mcp` |  | `egwg-reporting-tf-prototype-mcp-maintainers` |  | 1 |  |
| `governance` |  | `lfstaff`, `toip-maintainers` |  | 2 |  |
| `high-assurance-verifiable-identifiers` |  | `high-assurance-verifiable-identifiers-wg` |  | 1 |  |
| `kerisuite-glossary` | `keri-suite-wg` |  |  | 1 |  |
| `kswg-acdc-specification` | `keri-admins` | `tswg` | `tswg-acdc-tf` | 3 |  |
| `kswg-cesr-specification` | `keri-admins` | `tswg` | `tswg-acdc-tf` | 3 |  |
| `kswg-did-method-webs-specification` |  | `tswg`, `tswg-did-webs-tf` |  | 2 |  |
| `kswg-dossier-specification` | `tswg-dossier-specification-tf` |  |  | 1 |  |
| `kswg-keri-specification` | `keri-admins` | `tswg` | `tswg-acdc-tf` | 3 |  |
| `kswg-main-glossary` | `ctwg-admins`, `kswg` |  |  | 2 | **empty** (created 2025-01-14, never pushed) |
| `kswg-said-urn-charter` | `kswg` | `kswg-said-urn-charter-maintainers` |  | 2 |  |
| `logo-assets` | `toip-admins` |  |  | 1 |  |
| `PDF-Deliverable-Review` | `toip-admins` |  |  | 1 |  |
| `spec-up` | `toip-admins` |  |  | 1 |  |
| `spec-up-t` | `keri-admins`, `spec-up-t-admins` |  | `spec-up-t-writers` | 3 |  |
| `spec-up-t-demo-external-ref-1` | `spec-up-t-demo-external-ref-1-admins` |  |  | 1 |  |
| `spec-up-t-demo-external-ref-2` | `spec-up-t-demo-external-ref-2-admins` |  |  | 1 |  |
| `spec-up-t-healthcheck` | `spec-up-t-healthcheck-admins` |  |  | 1 |  |
| `spec-up-t-starter-pack` | `ctwg-admins` |  |  | 1 |  |
| `spec-up-t-website` | `ctwg-admins` |  |  | 1 |  |
| `specification-template` |  | `tswg` |  | 1 |  |
| `TechArch` | `techarch-admins` |  | `techarch-writers` | 2 |  |
| `toip` |  | `toip-maintainers` | `toip-writers` | 2 |  |
| `toip-governance` |  | `toip-governance-maintainers` |  | 1 |  |
| `toip-template` | `toip-template-admins` | `toip-template-maintainers` |  | 2 |  |
| `tswg-authentic-ai` | `tswg-authentic-ai-admins` |  |  | 1 |  |
| `tswg-did-method-webs-specification` |  | `tswg`, `tswg-did-webs-tf` |  | 2 | **empty** (created 2026-03-12, never pushed) |
| `tswg-did-x509-method-specification` |  | `tswg`, `tswg-did-x509-tf` |  | 2 |  |
| `tswg-tech-architecture-spec` | `tswg-tech-architecture-spec-admins` | `tswg-ta-tf` |  | 2 |  |
| `tswg-trust-registry-protocol` | `tswg-trust-registry-protocol-admins` | `tswg` | `tswg-tr-tf` | 3 |  |
| `tswg-trust-registry-query-language` |  |  |  | — | **no team access** |
| `tswg-trust-registry-service-profile` |  | `tswg` | `tswg-tr-tf` | 2 |  |
| `tswg-tsp-specification` |  | `tswg` | `tswg-tsp-tf` | 2 |  |
| `vLEI-EGF-3.0-Annual-Update-Public-Review` |  |  |  | — | **no team access** |
| `vLEI-EGF-4.0-Annual-Update-Public-Review` |  |  |  | — | **no team access** |

## Access by team

Each team's single permission level, its headcount, and the repositories it is granted on. Maintainers are the team's GitHub team maintainers, not a permission level.

| Team | Grants | Repos | People | Maintainers | Repositories |
|---|---|---|---|---|---|
| `aimwg-agent-fiduciary-duties-admins` | `admin` | 1 | 1 | wenjing | `aimwg-agent-fiduciary-duties` |
| `aimwg-agent-fiduciary-duties-maintainers` | `maintain` | 1 | 2 | wenjing | `aimwg-agent-fiduciary-duties` |
| `aimwg-tmcp-specification-admins` | `admin` | 1 | 2 | swatchen, wenjing | `aimwg-tmcp-specification` |
| `aimwg-tsp-enabled-ai-agent-protocols-admins` | `admin` | 2 | 1 | wenjing | `aimwg-trust-enabled-agents`, `aimwg-tsp-enabled-ai-agent-protocols` |
| `credential-exchange-protocols-admins` | `admin` | 1 | 1 | mathieuglaude | `credential-exchange-protocols` |
| `ctwg-admins` | `admin` | 6 | 4 | m00sey | `ctwg-general-glossary`, `ctwg-main-glossary`, `ctwg-terminology-governance-guide`, `kswg-main-glossary`, `spec-up-t-starter-pack`, `spec-up-t-website` |
| `ctwg-main-glossary-admins` | `admin` | 1 | 1 | darrellodonnell | `ctwg-main-glossary` |
| `dtgwg-admins` | `admin` | 15 | 5 | talltree | `dtgwg-agent-names-spec`, `dtgwg-agent-names-tf`, `dtgwg-cred-spec`, `dtgwg-cred-tf`, `dtgwg-general`, `dtgwg-htx-tf`, `dtgwg-rahp-tf`, `dtgwg-trust-tasks-spec`, `dtgwg-trust-tasks-tf`, `dtgwg-vds-spec`, `dtgwg-vds-tf`, `dtgwg-vsc-registry`, `dtgwg-vti-spec`, `dtgwg-zkp-spec`, `dtgwg-zkp-tf` |
| `dtgwg-maintainers` | `maintain` | 16 | 14 | talltree | `dtgwg-agent-names-spec`, `dtgwg-agent-names-tf`, `dtgwg-cred-spec`, `dtgwg-cred-tf`, `dtgwg-general`, `dtgwg-htx-tf`, `dtgwg-rahp-tf`, `dtgwg-rcards-tf`, `dtgwg-trust-tasks-spec`, `dtgwg-trust-tasks-tf`, `dtgwg-vds-spec`, `dtgwg-vds-tf`, `dtgwg-vsc-registry`, `dtgwg-vti-spec`, `dtgwg-zkp-spec`, `dtgwg-zkp-tf` |
| `dtgwg-zkp-tf-admins` | `admin` | 2 | 3 | talltree | `dtgwg-zkp-spec`, `dtgwg-zkp-tf` |
| `egwg-learning-pathways-wg` | `maintain` | 2 | 1 | carlyh-micb | `egwg-governance-metamodel`, `egwg-learning-pathways` |
| `egwg-reporting-tf-prototype-mcp-maintainers` | `maintain` | 1 | 2 | carlyh-micb | `egwg-reporting-tf-prototype-mcp` |
| `high-assurance-verifiable-identifiers-wg` | `maintain` | 1 | 9 | andorsk, talltree | `high-assurance-verifiable-identifiers` |
| `keri-admins` | `admin` | 4 | 2 | henkvancann | `kswg-acdc-specification`, `kswg-cesr-specification`, `kswg-keri-specification`, `spec-up-t` |
| `keri-suite-wg` | `admin` | 1 | 2 | henkvancann | `kerisuite-glossary` |
| `kswg` | `admin` | 2 | 3 | m00sey, pfeairheller, SmithSamuelM | `kswg-main-glossary`, `kswg-said-urn-charter` |
| `kswg-said-urn-charter-maintainers` | `maintain` | 1 | 2 | wenjing | `kswg-said-urn-charter` |
| `kswg-suc` | — | 0 | 1 | m00sey | **none** |
| `lfstaff` | `maintain` | 2 | 1 | ryjones | `EasyCLA`, `governance` |
| `spec-up-t-admins` | `admin` | 1 | 1 | chris-h-sg | `spec-up-t` |
| `spec-up-t-demo-external-ref-1-admins` | `admin` | 1 | 1 | kordwarshuis | `spec-up-t-demo-external-ref-1` |
| `spec-up-t-demo-external-ref-2-admins` | `admin` | 1 | 1 | kordwarshuis | `spec-up-t-demo-external-ref-2` |
| `spec-up-t-healthcheck-admins` | `admin` | 1 | 1 | kordwarshuis | `spec-up-t-healthcheck` |
| `spec-up-t-writers` | `write` | 1 | 2 | ryjones | `spec-up-t` |
| `techarch-admins` | `admin` | 1 | 3 | henkvancann, kordwarshuis, wenjing | `TechArch` |
| `techarch-writers` | `write` | 1 | 1 | talltree | `TechArch` |
| `toip-admins` | `admin` | 5 | 3 | m00sey | `.github`, `EasyCLA`, `PDF-Deliverable-Review`, `logo-assets`, `spec-up` |
| `toip-governance-maintainers` | `maintain` | 1 | 3 | carlyh-micb | `toip-governance` |
| `toip-maintainers` | `maintain` | 2 | 4 | m00sey, RieksJ | `governance`, `toip` |
| `toip-template-admins` | `admin` | 1 | 1 | geoffturk | `toip-template` |
| `toip-template-maintainers` | `maintain` | 1 | 6 | talltree | `toip-template` |
| `toip-writers` | `write` | 1 | 1 | kordwarshuis | `toip` |
| `tswg` | `maintain` | 10 | 5 | m00sey | `kswg-acdc-specification`, `kswg-cesr-specification`, `kswg-did-method-webs-specification`, `kswg-keri-specification`, `specification-template`, `tswg-did-method-webs-specification`, `tswg-did-x509-method-specification`, `tswg-trust-registry-protocol`, `tswg-trust-registry-service-profile`, `tswg-tsp-specification` |
| `tswg-acdc-tf` | `write` | 3 | 3 | m00sey | `kswg-acdc-specification`, `kswg-cesr-specification`, `kswg-keri-specification` |
| `tswg-aimt-tf` | `maintain` | 1 | 3 | m00sey | `aimwg-tmcp-specification` |
| `tswg-authentic-ai-admins` | `admin` | 1 | 1 | wenjing | `tswg-authentic-ai` |
| `tswg-cep-tf` | `write` | 1 | 2 | m00sey | `credential-exchange-protocols` |
| `tswg-did-webs-tf` | `maintain` | 2 | 3 | m00sey | `kswg-did-method-webs-specification`, `tswg-did-method-webs-specification` |
| `tswg-did-x509-tf` | `maintain` | 1 | 7 | m00sey | `tswg-did-x509-method-specification` |
| `tswg-dossier-specification-tf` | `admin` | 1 | 4 | dhh1128, m00sey | `kswg-dossier-specification` |
| `tswg-ta-tf` | `maintain` | 1 | 3 | andorsk, m00sey | `tswg-tech-architecture-spec` |
| `tswg-tech-architecture-spec-admins` | `admin` | 1 | 1 | darrellodonnell | `tswg-tech-architecture-spec` |
| `tswg-tr-tf` | `write` | 2 | 5 | andorsk, m00sey | `tswg-trust-registry-protocol`, `tswg-trust-registry-service-profile` |
| `tswg-trust-registry-protocol-admins` | `admin` | 1 | 1 | darrellodonnell | `tswg-trust-registry-protocol` |
| `tswg-tsp-tf` | `write` | 1 | 4 | m00sey | `tswg-tsp-specification` |
| `ufwg` | — | 0 | 1 | m00sey | **none** |

## Team membership

| Team | Maintainers | Members |
|---|---|---|
| `aimwg-agent-fiduciary-duties-admins` | wenjing | *(none)* |
| `aimwg-agent-fiduciary-duties-maintainers` | wenjing | swatchen |
| `aimwg-tmcp-specification-admins` | swatchen, wenjing | *(none)* |
| `aimwg-tsp-enabled-ai-agent-protocols-admins` | wenjing | *(none)* |
| `credential-exchange-protocols-admins` | mathieuglaude | *(none)* |
| `ctwg-admins` | m00sey | henkvancann, kordwarshuis, talltree |
| `ctwg-main-glossary-admins` | darrellodonnell | *(none)* |
| `dtgwg-admins` | talltree | geoffturk, martipos, NickyHickman, stormer78 |
| `dtgwg-maintainers` | talltree | albertoleon7794, bmiller59, ebjune, geoffturk, GlinzCO, martipos, mitchuski, NickyHickman, peacekeeper, sankarshanmukhopadhyay, ScottJeezey, simmunity, stormer78 |
| `dtgwg-zkp-tf-admins` | talltree | mitchuski, ScottJeezey |
| `egwg-learning-pathways-wg` | carlyh-micb | *(none)* |
| `egwg-reporting-tf-prototype-mcp-maintainers` | carlyh-micb | sankarshanmukhopadhyay |
| `high-assurance-verifiable-identifiers-wg` | andorsk, talltree | darrellodonnell, JohnOnGH, peacekeeper, sankarshanmukhopadhyay, trbouma, tweeddalex, wenjing |
| `keri-admins` | henkvancann | kordwarshuis |
| `keri-suite-wg` | henkvancann | kordwarshuis |
| `kswg` | m00sey, pfeairheller, SmithSamuelM | *(none)* |
| `kswg-said-urn-charter-maintainers` | wenjing | carlyh-micb |
| `kswg-suc` | m00sey | *(none)* |
| `lfstaff` | ryjones | *(none)* |
| `spec-up-t-admins` | chris-h-sg | *(none)* |
| `spec-up-t-demo-external-ref-1-admins` | kordwarshuis | *(none)* |
| `spec-up-t-demo-external-ref-2-admins` | kordwarshuis | *(none)* |
| `spec-up-t-healthcheck-admins` | kordwarshuis | *(none)* |
| `spec-up-t-writers` | ryjones | pandyapreksha16-beep |
| `techarch-admins` | henkvancann, kordwarshuis, wenjing | *(none)* |
| `techarch-writers` | talltree | *(none)* |
| `toip-admins` | m00sey | darrellodonnell, talltree |
| `toip-governance-maintainers` | carlyh-micb | ScottSPerryCPA, talltree |
| `toip-maintainers` | m00sey, RieksJ | darrellodonnell, talltree |
| `toip-template-admins` | geoffturk | *(none)* |
| `toip-template-maintainers` | talltree | carlyh-micb, henkvancann, kordwarshuis, martipos, ScottSPerryCPA |
| `toip-writers` | kordwarshuis | *(none)* |
| `tswg` | m00sey | danielbachgit, darrellodonnell, talltree, wenjing |
| `tswg-acdc-tf` | m00sey | pfeairheller, SmithSamuelM |
| `tswg-aimt-tf` | m00sey | swatchen, wenjing |
| `tswg-authentic-ai-admins` | wenjing | *(none)* |
| `tswg-cep-tf` | m00sey | mathieuglaude |
| `tswg-did-webs-tf` | m00sey | jrayback, kentbull |
| `tswg-did-x509-tf` | m00sey | jacqueslatour, kudrixD, mathieuglaude, scouten-adobe, talltree, wenjing |
| `tswg-dossier-specification-tf` | dhh1128, m00sey | kentbull, SmithSamuelM |
| `tswg-ta-tf` | andorsk, m00sey | talltree |
| `tswg-tech-architecture-spec-admins` | darrellodonnell | *(none)* |
| `tswg-tr-tf` | andorsk, m00sey | a-fox, carlyh-micb, darrellodonnell |
| `tswg-trust-registry-protocol-admins` | darrellodonnell | *(none)* |
| `tswg-tsp-tf` | m00sey | SmithSamuelM, talltree, wenjing |
| `ufwg` | m00sey | *(none)* |

## Empty repositories

Five managed repositories hold no commits. For each, `created_at` and `pushed_at` are the same second, so they were created on GitHub and never initialised — not emptied later.

| Repository | Created | Teams granted | Comment |
|---|---|---|---|
| `kswg-main-glossary` | 2025-01-14 | `ctwg-admins`: `admin`, `kswg`: `admin` | Granted `admin` to two teams (`ctwg-admins`, `kswg`) for content that does not exist. `ctwg-main-glossary` is the live glossary. |
| `tswg-did-method-webs-specification` | 2026-03-12 | `tswg`: `maintain`, `tswg-did-webs-tf`: `maintain` | Name-duplicates `kswg-did-method-webs-specification`, which holds the real spec and the identical grants. This shell is the one to retire. |
| `dtgwg-ux-tf` | 2026-07-23 | **none** | Also has no teams — an empty repository nobody can reach. |
| `dtgwg-rcards-tf` | 2026-07-30 | `dtgwg-maintainers`: `maintain` | The only `dtgwg-*` repository that grants `dtgwg-maintainers` without also granting `dtgwg-admins` `admin`. |
| `aimwg-tsp-enabled-ai-agent-protocols` | 2026-08-25 | `aimwg-tsp-enabled-ai-agent-protocols-admins`: `admin` | Its team `aimwg-tsp-enabled-ai-agent-protocols-admins` also holds `aimwg-trust-enabled-agents`, which has the content. |

## Teams with no repositories

These teams exist in the config but appear in no repository's `teams:` map, so CLOWarden creates them on GitHub and grants them nothing.

| Team | Maintainers | Members |
|---|---|---|
| `kswg-suc` | m00sey | *(none)* |
| `ufwg` | m00sey | *(none)* |

Both are `m00sey` with no members. A 2026-10-05 audit found these two held zero repositories on GitHub as well, so this is not drift hiding real access.

## Repositories with no teams

These four declare `visibility: public` and no `teams:` key. Nobody has repository-level access through this config; only org owners can administer or write to them.

| Repository | Empty? | Comment |
|---|---|---|
| `dtgwg-ux-tf` | **yes** | Empty *and* unreachable — a placeholder with nothing and nobody. |
| `tswg-trust-registry-query-language` | no | 16 files, spec-up-t scaffolding. The sibling `tswg-trust-registry-protocol` and `tswg-trust-registry-service-profile` both grant `tswg` and `tswg-tr-tf`; this one grants nothing. |
| `vLEI-EGF-3.0-Annual-Update-Public-Review` | no | 11 files of review material. Public-review drop boxes; no team was ever attached. |
| `vLEI-EGF-4.0-Annual-Update-Public-Review` | no | 26 files of review material. Same pattern as the 3.0 repository. |

## Observations

### Concentration

| Team | Level | Repositories |
|---|---|---|
| `dtgwg-maintainers` | `maintain` | 16 |
| `dtgwg-admins` | `admin` | 15 |
| `tswg` | `maintain` | 10 |
| `ctwg-admins` | `admin` | 6 |
| `toip-admins` | `admin` | 5 |
| `keri-admins` | `admin` | 4 |
| `tswg-acdc-tf` | `write` | 3 |
| `aimwg-tsp-enabled-ai-agent-protocols-admins` | `admin` | 2 |

Twenty-nine teams hold exactly one repository. Most of those are single-repository `-admins` teams with one maintainer and no members, i.e. one person's access expressed as a team.

### Team names that do not state the level they grant

By the convention that `-admins` grants `admin`, `-maintainers` grants `maintain` and `-writers` grants `write`, fourteen granted teams are named for what the group *is* rather than what it holds. `lfstaff` is deliberately exempt.

| Team | Grants |
|---|---|
| `egwg-learning-pathways-wg` | `maintain` |
| `high-assurance-verifiable-identifiers-wg` | `maintain` |
| `keri-suite-wg` | `admin` |
| `kswg` | `admin` |
| `tswg` | `maintain` |
| `tswg-acdc-tf` | `write` |
| `tswg-aimt-tf` | `maintain` |
| `tswg-cep-tf` | `write` |
| `tswg-did-webs-tf` | `maintain` |
| `tswg-did-x509-tf` | `maintain` |
| `tswg-dossier-specification-tf` | `admin` |
| `tswg-ta-tf` | `maintain` |
| `tswg-tr-tf` | `write` |
| `tswg-tsp-tf` | `write` |

### Repositories whose grants break their family's pattern

- Every `dtgwg-*` repository pairs `dtgwg-admins: admin` with `dtgwg-maintainers: maintain`, except `dtgwg-rcards-tf` (maintainers only) and `dtgwg-ux-tf` (nothing).
- `keri-admins` holds `admin` on the three flagship KERI specs (`kswg-acdc-specification`, `kswg-cesr-specification`, `kswg-keri-specification`) plus `spec-up-t`, while the KSWG chairs in `tswg-acdc-tf` hold only `write` on those same specs.
- `keri-suite-wg` and `keri-admins` have identical membership (`henkvancann` maintaining, `kordwarshuis` a member); the former exists only to hold `admin` on `kerisuite-glossary`.
- `tswg` carries standing `maintain` on 10 repositories, four of them `kswg-*`, which is the widest non-DTGWG grant in the file.

### Zero-member teams

No team is completely empty of people, but 21 of the 46 have maintainers and no members. `lfstaff` (`ryjones`) is one of them, and it is granted on only two repositories — `EasyCLA` and `governance` — so LF staff access here is deliberately narrow.


# Gapwise organization defaults

This repository contains the public GitHub organization profile and shared community-health files for **Gapwise**.

Gapwise has one canonical web application in `gapwise`, with `data`, `android`, `ios`, `ai`, `docs`, `status`, and `cli` serving distinct responsibilities across all supported universities. This `.github` repository owns organization-wide metadata and defaults.

## What lives here

- `profile/README.md` — organization overview rendered on the Gapwise GitHub profile.
- `CONTRIBUTING.md` — default contribution guidance for repositories that do not define a more specific policy.
- `CODE_OF_CONDUCT.md` — organization-wide participation expectations.
- `SECURITY.md` — default vulnerability-reporting guidance.
- `SUPPORT.md` — default support routing.
- `.github/PULL_REQUEST_TEMPLATE.md` — shared pull-request checklist.
- `.github/ISSUE_TEMPLATE/` — shared bug and feature-request forms plus support/security routing.

Repository-local files take precedence when a component needs more specific instructions.

## Source-of-truth map

| Area | Canonical repository |
| --- | --- |
| Web/PWA product, deterministic student-day behavior, public API and SDK source | [`gapwise`](https://github.com/GapwiseHQ/gapwise) |
| Native Android client and Android device integration | [`android`](https://github.com/GapwiseHQ/android) |
| Native iOS client and Apple-platform integration | [`ios`](https://github.com/GapwiseHQ/ios) |
| AI/MCP delegation boundary | [`ai`](https://github.com/GapwiseHQ/ai) |
| Public campus facts, provenance and validation | [`data`](https://github.com/GapwiseHQ/data) |
| University integration scaffolding and validation | [`cli`](https://github.com/GapwiseHQ/cli) |
| Public developer documentation | [`docs`](https://github.com/GapwiseHQ/docs) |
| Independent service monitoring and incident communication | [`status`](https://github.com/GapwiseHQ/status) |

Gapwise provides dedicated editions for 13 universities across 15 campus models in Canada: University of Toronto ([gapwise.ca](https://gapwise.ca)), Carleton University ([carleton.gapwise.ca](https://carleton.gapwise.ca)), Toronto Metropolitan University ([tmu.gapwise.ca](https://tmu.gapwise.ca)), Queen's University ([queens.gapwise.ca](https://queens.gapwise.ca)), Wilfrid Laurier University ([laurier.gapwise.ca](https://laurier.gapwise.ca)), York University ([york.gapwise.ca](https://york.gapwise.ca)), McMaster University ([mcmaster.gapwise.ca](https://mcmaster.gapwise.ca)), Western University ([western.gapwise.ca](https://western.gapwise.ca)), University of Guelph ([guelph.gapwise.ca](https://guelph.gapwise.ca)), University of Ottawa ([uottawa.gapwise.ca](https://uottawa.gapwise.ca)), Brock University ([brock.gapwise.ca](https://brock.gapwise.ca)), the University of British Columbia ([ubc.gapwise.ca](https://ubc.gapwise.ca)), and the University of Waterloo ([waterloo.gapwise.ca](https://waterloo.gapwise.ca)).

For product information, visit [gapwise.ca](https://gapwise.ca). For developer documentation, visit [docs.gapwise.ca](https://docs.gapwise.ca).

Original organization profile and community documentation are available under the [MIT License](LICENSE).

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

Gapwise supports 38 universities across 90 campus models through one shared web application. [gapwise.ca](https://gapwise.ca) is the global landing page; university and campus editions, including [UTM](https://utm.gapwise.ca), provide the campus-specific application. The [university directory](https://gapwise.ca/universities) and [canonical registry](https://github.com/GapwiseHQ/gapwise/blob/main/universities.json) list maintained editions and their capabilities.

For product information, visit [gapwise.ca](https://gapwise.ca). For developer documentation, visit [docs.gapwise.ca](https://docs.gapwise.ca).

Original organization profile and community documentation are available under the [MIT License](LICENSE).

# Lux Open-Source Policy

This policy describes how Lux Industries Inc. produces, licenses, accepts contributions to, and uses open-source software.

## Lux as Open-Source Producer

### License Defaults

- New repositories default to **BSD-3-Clause** unless they qualify for Eco-tier protection.
- A repository qualifies for Eco when it implements patentable Lux inventions, embodies competitive advantages, or implements specifications Lux intends to commercialize.
- The decision between BSD-3 and Eco is made at repository creation by engineering leadership in consultation with legal. Once licensed under Eco, no migration to BSD-3 is planned.
- Closed repositories live under `github.com/lux-private/*` and use proprietary all-rights-reserved terms.

See [LICENSING-POLICY.md](LICENSING-POLICY.md) for the full three-tier framework.

### License File Hygiene

Every public repository must include:

1. A `LICENSE` file at the root, containing the full license text.
2. SPDX identifiers in source-file headers (`SPDX-License-Identifier: BSD-3-Clause` or `SPDX-License-Identifier: LicenseRef-Lux-Eco`).
3. A `NOTICE` file where required by upstream-license obligations from incorporated third-party code.
4. A `CONTRIBUTING.md` referencing this policy and the [Contributor License Agreement](CONTRIBUTOR-AGREEMENT.md).

TODO[counsel-review]: confirm SPDX identifier `LicenseRef-Lux-Eco` is consistent with Lux Eco License text and registered if appropriate.

### Code Review

All commits to public repositories are reviewed by a Lux maintainer before merge. The reviewer is responsible for:

- Code quality, correctness, and consistency with project conventions.
- License compatibility of any newly introduced dependencies.
- CLA status of any outside contributor.
- Absence of secrets, credentials, or third-party Confidential Information.

## Accepting Outside Contributions

### CLA Requirement

- Trivial contributions (typo fixes, single-line documentation corrections) may be accepted without a CLA at the maintainer's discretion.
- Substantial contributions (as defined in the [Contributor License Agreement](CONTRIBUTOR-AGREEMENT.md)) require a signed CLA.
- Contributors employed by an organization should sign a corporate CLA on behalf of that organization where the organization holds rights to the contributor's work.

### Provenance

Maintainers should verify, to a reasonable standard, that submitted contributions are the contributor's original work and not copied from incompatible upstream sources. Use of `git log` author metadata, signed-off-by lines, and DCO-style attestations is encouraged.

### Patches from Anonymous or Pseudonymous Contributors

Substantial contributions from contributors who decline to provide identifying information sufficient to execute a CLA shall not be merged. Trivial contributions may be accepted at the maintainer's discretion.

TODO[counsel-review]: confirm policy on pseudonymous contributors aligns with intended openness; some projects (e.g., Bitcoin) accept pseudonymous contributions, others require legal identity.

## Lux as Open-Source Consumer

When Lux uses third-party open-source software in its own projects, the following rules apply:

### Approved Licenses

The following licenses are pre-approved for use in any Lux repository (including Eco and Closed repos):

- BSD-2-Clause, BSD-3-Clause.
- MIT.
- Apache 2.0.
- ISC.

### Conditionally Approved Licenses

The following licenses require legal review before use:

- LGPL-2.1, LGPL-3.0 (acceptable for dynamic linking; static linking requires review).
- MPL-2.0 (acceptable; review obligations to publish file-level modifications).

### Restricted Licenses

The following licenses are restricted:

- GPL-2.0, GPL-3.0 — not permitted in Eco or Closed repositories. Permitted in BSD-3 repositories only with legal review and clear separation.
- AGPL-3.0 — not permitted in any Lux repository, including BSD-3, due to network-copyleft propagation.
- SSPL — not permitted in any Lux repository.
- Custom or unrecognized licenses — require legal review.

TODO[counsel-review]: confirm restricted-license list aligns with current legal posture and any specific commercial commitments to Eco licensees regarding non-copyleft dependency profiles.

### License Audit

New dependencies must be evaluated for license compatibility before being added. CI tooling that scans dependencies for license metadata should be in place for all production repositories.

## Forks of Upstream Projects

When Lux maintains a fork of an upstream open-source project, the fork retains the upstream license. Lux contributions to the fork are licensed under the upstream license. Lux may not apply Eco or proprietary terms to a forked codebase that is licensed under terms incompatible with that.

Where Lux wishes to commercialize work derived from a fork, the work must be cleanly separated from the fork (for example, in a separate Lux-owned repository) and may then be licensed under Lux terms.

## Public Communication

Maintainers and Lux personnel communicating in public forums (GitHub issues, discussion boards, conferences, social media) about Lux open-source projects:

- Speak respectfully and professionally to outside contributors and users.
- Do not commit Lux Industries Inc. to features, timelines, or commercial terms without authorization.
- Do not disclose Confidential Information.
- Avoid statements that could be interpreted as legal advice; refer questions to **legal@lux.network**.

## Cross-references

- [LICENSING-POLICY.md](LICENSING-POLICY.md)
- [CONTRIBUTOR-AGREEMENT.md](CONTRIBUTOR-AGREEMENT.md)
- [PATENT-POLICY.md](PATENT-POLICY.md)
- [TRADEMARK-POLICY.md](TRADEMARK-POLICY.md)

Last reviewed: TODO[counsel-review].

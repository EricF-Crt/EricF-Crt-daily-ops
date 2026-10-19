# tools

This folder contains scripts, utilities, and small automations for daily work.

## Suggested structure
- Small helper scripts
- One-off automations that become reusable
- Notes on usage and maintenance

## Thermal tooling handoff

No thermal execution tools or platform integrations are currently supplied here.
The [thermal framework](../docs/thermal-framework.html) defines the common approach;
the [profile template](../docs/thermal-project-profile.template.json) is documentation,
not executable configuration.

Before implementing changes, the SW tooling owner must identify existing tool source
locations, versions, owners, supported platforms, and validation commands. Prefer
configuration and small extensions to those tools over a new runner or project forks.
Pilot the common approach on representative platforms, including a constrained product,
and report requested versus achieved load, validity, capability gaps, and coverage.
Hardware execution and vendor support remain pending; this handoff does not provide them.

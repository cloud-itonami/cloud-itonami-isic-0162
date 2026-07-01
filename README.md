# cloud-itonami-0162

Open Business Blueprint for **ISIC Rev.5 0162**: agronomy support — soil and crop scouting, advisory, and targeted treatment for smallholders.

This repository designs a forkable OSS business for community agronomy support:
run by a qualified operator so a community keeps its own operating records
instead of renting a closed SaaS.

## Robotics premise

All cloud-itonami verticals are designed on the premise that a **robot performs
the physical domain work**. Here a field robot performs sampling, scouting and targeted treatment in the field under an actor that proposes
actions and an independent **Agronomy Governor** that gates them. The governor never
dispatches hardware itself; `:high`/`:safety-critical` actions (such as
operating near people, livestock or water sources) require human sign-off.

## Core Contract

```text
intake + identity + identity records
        |
        v
Advisor -> Agronomy Governor -> proceed, hold, or human approval
        |
        v
robot actions (gated) + operating records + audit ledger
```

No automated advice can dispatch a robot action the governor refuses, suppress
an operating record, or disclose sensitive data without governor approval and
audit evidence.

## Capability layer

Resolves via [`kotoba-lang/industry`](https://github.com/kotoba-lang/industry)
(ISIC `0162`). Required capabilities:

- `:robotics`
- `:identity`
- `:forms`
- `:dmn`
- `:bpmn`
- `:audit-ledger`
- `:telemetry`

See [`docs/business-model.md`](docs/business-model.md) and
[`docs/operator-guide.md`](docs/operator-guide.md).

## License

AGPL-3.0-or-later.

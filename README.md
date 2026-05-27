# zos-config

Zero-OS Config provides global configuration definitions for all Zero-OS nodes. It specifies network parameters, feature flags, and operational settings that nodes fetch at startup. The repository acts as the single source of truth for grid-wide node behavior and capabilities.

## What this is

This repository holds the public, generic configuration consumed by ZOS / Zero-OS nodes at boot time. Rather than baking configuration into OS releases, nodes retrieve their settings from this repository. This allows operational changes — such as network endpoint updates, feature toggles, or capacity parameters — to be rolled out without requiring a full OS redeploy, reducing network load and maintenance overhead.

## What this repository contains

- **Network configuration** — endpoints, bootstrap URLs, and connectivity parameters for each environment
- **Feature flags** — toggles that enable or disable capabilities across the node fleet
- **Operational settings** — runtime parameters that control node behavior and resource limits
- **Schema-validated config files** — changes must pass schema validation and administrative review before merging

Configuration is organized by network environment (e.g., production, test, QA, development).

## Role in the stack

ZOS / Zero-OS nodes fetch configuration from this repository during startup. The configuration drives how nodes connect to the network, which features are active, and how they report capacity and workloads. By externalizing configuration from the OS image, the stack can evolve operational parameters independently of release cycles.

## ZOS / Zero-OS

ZOS, also known as Zero-OS, is the operating system layer used to run and manage nodes. It provides the low-level runtime environment for workloads, networking, storage, and automation. This repository supplies the live configuration that ZOS nodes rely on to operate correctly within their target environment.

## Relation to ThreeFold

This technology is used within the ThreeFold ecosystem and was first deployed on the ThreeFold Grid. The component itself is designed as reusable infrastructure technology and should be understood by its technical function first, independent of any specific deployment.

## Ownership

This repository is owned and maintained by TF-Tech NV, a Belgian company responsible for the development and maintenance of this technology.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.
Copyright (c) TF-Tech NV.

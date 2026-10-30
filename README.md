# AEROSIM

### Aircraft Systems & Failure Simulation

> **Project status:** Planning and initial development. The functionality described below is the intended roadmap, not a claim that a working simulator is already available.

## Overview

**AEROSIM** is an open-source-oriented engineering project to develop a modular aircraft systems and failure simulation application, primarily in **C**.

The software is intended to model the behavior and interactions of **fictional aircraft subsystems**—including engines, electrical power distribution, hydraulics, and fault detection—using simplified, documented physical models. An interactive desktop dashboard will let users observe changing system states, adjust inputs, inject simulated faults, and analyze their effects.

AEROSIM is an **engineering and software-testing simulation**, not a flight simulator or a representation of any real military aircraft.

## Project Goals

- Build a maintainable and extensible application in C17.
- Explore numerical simulation with deterministic, fixed-timestep updates.
- Model dependencies and failure propagation between subsystems.
- Provide clear monitoring, diagnostics, event logs, and reproducible scenarios.
- Apply professional software engineering: modular architecture, tests, documentation, and CI.
- Use AI-assisted development tools such as Claude Code while reviewing and validating all generated code.

## Planned Features

| Subsystem / Feature | Intended functionality |
| --- | --- |
| **Engine** | Simplified engine speed, temperature, and power response |
| **Electrical** | Fictional generators, battery, electrical buses, and loads |
| **Hydraulics** | Simplified pumps, pressure, leaks, and actuator availability |
| **Fault Management** | Fault injection, severity classification, warnings, and propagation |
| **Dashboard** | Live parameters, status indicators, charts, and controls |
| **Event Logging** | Timestamped events and diagnostic history |
| **Scenario Engine** | Repeatable normal and failure scenarios |
| **Verification** | Unit tests, integration tests, and model sanity checks |

## Architecture (Proposed)

```text
User Inputs / Scenarios
          |
          v
+-------------------------+
| Simulation Controller   |  fixed timestep / state updates
+-------------------------+
          |
          v
+-------------------------+
| Aircraft Systems Model  |
|  - Engine               |
|  - Electrical           |
|  - Hydraulic            |
+-------------------------+
          |
          v
+-------------------------+
| Fault & Diagnostic Layer|
+-------------------------+
       /          \
      v            v
 Dashboard      Event Log
```

**Design principles:** separate simulation logic from presentation, use explicit units and documented assumptions, keep state updates deterministic where practical, and test subsystem interfaces independently.

## Technology Stack (Planned)

- **Language:** C17
- **Build system:** CMake
- **Graphics and input:** [raylib](https://www.raylib.com/)
- **Testing:** CTest and C unit tests
- **Version control / CI:** Git, GitHub, and GitHub Actions
- **Primary development environment:** Visual Studio or VS Code

## Proposed Repository Structure

```text
AEROSIM/
├── CMakeLists.txt
├── README.md
├── include/
│   ├── aircraft.h
│   ├── engine.h
│   ├── electrical.h
│   ├── hydraulic.h
│   ├── fault_manager.h
│   └── simulation.h
├── src/
│   ├── main.c
│   ├── aircraft.c
│   ├── engine.c
│   ├── electrical.c
│   ├── hydraulic.c
│   ├── fault_manager.c
│   └── simulation.c
├── gui/
├── scenarios/
├── tests/
├── docs/
└── .github/workflows/
```

*This structure is a design target and may evolve during implementation.*

## Development Roadmap

- [ ] **v0.1 — Foundation:** CMake setup, fixed-timestep simulation loop, basic engine model, minimal raylib dashboard, and initial tests.
- [ ] **v0.2 — Electrical system:** simplified generator, battery, bus, and load models.
- [ ] **v0.3 — Hydraulic system:** pressure, pump, leak, and actuator models.
- [ ] **v0.4 — Fault management:** configurable faults, warnings, and subsystem interactions.
- [ ] **v0.5 — Diagnostics:** event logging, repeatable scenarios, and basic analysis views.
- [ ] **v1.0 — Integrated application:** documented models, expanded UI, automated tests, CI, and packaged releases.

## Building and Running

**A runnable build is not yet available.** Build instructions will be added once the first implementation and dependency configuration are committed.

The planned build workflow uses CMake and a supported C17 compiler. The exact raylib dependency setup will be documented and validated for the supported platforms before publishing commands.

## Testing and Validation

Planned testing activities include:

- Unit tests for subsystem calculations and state transitions.
- Boundary-value and invalid-input tests.
- Integration tests for interactions between subsystems.
- Deterministic replay of defined simulation scenarios.
- Sanity checks against simplified analytical expectations.
- Static analysis and compiler warnings in CI.

Simulation models are **educational abstractions**; their limitations and assumptions will be documented. They are not intended for certification, operational decision-making, maintenance, or flight safety use.

## AI-Assisted Development

Claude Code may be used to support architecture exploration, implementation, code review, debugging, refactoring, documentation, and test generation. All contributions—including AI-generated code—should be reviewed, tested, and committed through the same development workflow.

## Security, Safety, and Data Policy

AEROSIM uses **fictional aircraft designs, synthetic data, and publicly available engineering principles only**.

The repository must not contain classified, restricted, proprietary, export-controlled, or internal Bundeswehr/Airbus documentation, software, procedures, configurations, or datasets. It is an independent personal project and is **not affiliated with or endorsed by the Bundeswehr, Airbus, or any aircraft manufacturer**.

## Contributing

Suggestions and contributions are welcome as the project develops. Please open an issue to discuss major changes before submitting a pull request. Contributions must follow the project's safety and data policy.

## License

**License decision pending.** A license file will be added once the intended permissions for reuse and distribution are finalized. Until then, no open-source license is granted by this README alone.

---

**AEROSIM** — Exploring aircraft systems engineering through simulation, C programming, and software verification.

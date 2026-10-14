# Awesome-Real-Time-Transport-Dispatch-Exception-Routing

## Top Real-Time Transport Dispatch & Exception Routing Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Dynamic Route Recalculation, Exception Management & On-Demand Dispatch*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Real-Time Transport Dispatch & Exception Routing**. These tools help logistics operators recalculate routes on the fly when delays, breakdowns, or new orders disrupt the plan — ensuring drivers get updated sequences, dispatchers see exceptions immediately, and customers receive accurate ETAs.

**Examples** include Samsara, Motive, Trimble Transportation, Wise Systems, OptimoRoute, Routific, Onfleet, Circuit, Bringg, and DispatchTrack (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, custom VRP solvers, and transparent exception handling — ideal for logistics engineers prioritizing data sovereignty, developers building dispatch pipelines, and teams avoiding per-vehicle monthly fees.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Samsara](https://www.samsara.com/)**  
  Connected operations platform with real-time fleet tracking, route optimization, and exception alerts for delays, deviations, and safety events.

- **[Motive](https://gomotive.com/)**  
  Fleet management platform with dispatch, routing, and real-time exception detection for logistics operations.

- **[Trimble Transportation](https://transportation.trimble.com/)**  
  Enterprise transportation management with dynamic routing, dispatch, and exception handling for carriers and shippers.

- **[Wise Systems](https://wisesystems.com/)**  
  AI-powered dispatch and routing platform that continuously optimizes routes as conditions change, with real-time exception management.

- **[OptimoRoute](https://optimoroute.com/)**  
  Route planning and optimization software with dynamic re-routing and real-time order insertion for delivery fleets.

- **[Routific](https://routific.com/)**  
  Route optimization platform for last-mile delivery with real-time dispatch and exception handling.

- **[Onfleet](https://onfleet.com/)**  
  Delivery management platform with real-time dispatch, route optimization, and exception alerts for on-demand logistics.

- **[Circuit](https://getcircuit.com/)**  
  Route planning and dispatch platform for delivery drivers with real-time re-routing and exception management.

- **[Bringg](https://bringg.com/)**  
  Delivery orchestration platform with dynamic routing, real-time exception handling, and customer communication.

- **[DispatchTrack](https://dispatchtrack.com/)**  
  Last-mile delivery management with AI-powered routing, real-time dispatch, and exception tracking.

## Open-Source GitHub Projects

- **[VROOM](https://github.com/VROOM-Project/vroom)**  
  **The leading open-source route optimization engine**, written in C++20. Solves TSP, CVRP, VRPTW, multi-depot heterogeneous VRPTW, and **PDPTW (pickup-and-delivery with time windows)** in milliseconds [citation:12]. Models a VRP with vehicles, jobs, and shipments — supporting capacity on arbitrary metrics, time windows, skills, priority, driver breaks, and open trips [citation:12]. Works out-of-the-box on OSRM, Openrouteservice, and Valhalla [citation:12]. The foundational engine behind **better-route** and many commercial dispatch systems.

- **[better-route](https://github.com/EijunnN/better-route)**  
  **Self-hosted route optimization and delivery management platform** powered by VROOM + OSRM. No per-driver fees [citation:15]. Full stack: Next.js 16 frontend, PostgreSQL + Drizzle ORM, Redis cache, MapLibre GL maps, Centrifugo WebSocket for real-time updates, and Flutter mobile app [citation:15]. Handles company onboarding, RBAC, and real-time dispatch. The most complete open-source alternative to commercial dispatch SaaS.

- **[Lynxo](https://github.com/TRADLY-PLATFORM/lynxo)**  
  **Production-ready starter kit for last-mile delivery** and order management [citation:2]. Built with React 19, TypeScript, Vite 7, and Tailwind CSS. Features live product listings, smart search, easy checkout, **real-time order tracking with status updates every 10 seconds**, and offline-first mock mode for development without API keys [citation:2]. Integrates with Tradly headless commerce for product sync, orders, and payments [citation:2].

- **[pdptw-lns-solver](https://pypi.org/project/pdptw-lns-solver/0.1.1/)**  
  **Fast PDPTW solver built for online / on-demand transit dispatch** [citation:6]. Inserts new ride requests into live fleet schedules using **Large Neighborhood Search (LNS)** — respecting capacities, time windows, and pickup-before-dropoff order [citation:6]. Never drops committed rides: if a new request can't be served, only that request is rejected [citation:6]. Parallel-safe (each solver instance independent), no external solver license, works with OSRM or a provided travel time matrix [citation:6]. `check_feasibility` returns feasible time windows with cost ratios for offering pickup choices [citation:6].

- **[oway-dispatch-console](https://github.com/faalbane/oway-dispatch-console)**  
  **Carrier dispatch console for LTL shipments** with capacity constraints and **status-aware route generation** [citation:4]. Ships ASSIGNED (full pickup + delivery), PICKED_UP (delivery only — re-routing skips completed pickup), and excludes DELIVERED/CANCELLED [citation:4]. Time windows estimated at 25 mph effective speed + 20 min service per stop, with window violations **flagged but not removed** — ops decides [citation:4]. Score = `distance + 2 × window_violation_minutes − 5 × adjacent_hazmat_pairs` [citation:4]. Reassignment between vehicles invalidates both routes atomically [citation:4].

- **[mpee](https://github.com/punnerud/mpee)**  
  **Offline routing, multi-vehicle VRP & street geocoding** for one downloaded area [citation:5]. Rust engine (`brooom` / `dijeng`) with five equal surfaces: Rust crate, Python (`pip install mpee`), CLI, HTTP API (`brooom --serve 8088`), and JSON config [citation:5]. Native paired `shipments` (PDPTW) in the Rust core; Python binding currently requires each half as a job [citation:5]. Suitable for embedded dispatch where connectivity is unreliable.

- **[smart-logistics-vrp](https://github.com/rodrigope12/smart-logistics-vrp)**  
  **Full-stack last-mile logistics with VRP optimization and offline sync** [citation:8]. Uses Google OR-Tools for route optimization with **hard security checkpoint constraints** (e.g., mandatory checkpoints in high-risk zones) [citation:8]. React Native mobile app with **offline-first capability** — drivers complete deliveries and capture proof-of-delivery without internet [citation:8]. FastAPI backend, Google Sheets as zero-cost database, automated PDF invoicing and WhatsApp logs on delivery [citation:8].

- **[RouteOpt](https://github.com/INFORMSJoC/2025.1415)**  
  **First open-source modular exact solver for VRPs** [citation:1][citation:7]. State-of-the-art performance on CVRP and VRPTW, with modular design allowing custom branching, cutting-plane, and variable reduction modules [citation:1]. Novel node restoration mechanism enables efficient parallel branch-and-bound processing [citation:1]. GPLv3 licensed, interfaces with CPLEX/Gurobi via solver-adapter layer [citation:13]. Best for research and small-to-medium instances where optimality proof matters.

### Additional Strong Open-Source Options

- **[Nextroute](https://pypi.org/project/nextroute/1.8.0.dev2/)** — Feature-rich VRP solver in pure Go with Python bindings. Supports alternate stops, compatibility attributes, cluster constraints, custom matrices/objectives/operators, early/late arrival penalties, maximum route distance/duration/stops, precedence, stop duration multipliers, stop groups, time windows, unplanned penalties, and vehicle activation penalties [citation:11]. **Source-available** (not open-source) [citation:11].

- **Vantal Tech Exception Kit** — Lightweight starter kit for retail/ecommerce/logistics exception handling: ingest events from operational systems, apply auditable rules, alert teams in Slack, maintain audit trail. Local-first, runnable in minutes [citation:3].

- **Agentic Logistics — Shipment Exception** — SQL-based shipment-exception agent that joins late shipments with customer SLA tolerance, recalls similar past exceptions, and drafts customer notice + carrier dispatch in one call [citation:9]. Demonstrates exception routing pattern for AI agent integration [citation:9].

- **VRP Library (PyVRP)** — Python package implementing hybrid genetic search for VRPTW and 6+ core VRP variants. Balances flexibility and efficiency with C++ performance-critical components and Python customization [citation:13].

- **Vroom Docker** — Pre-bundled Docker setup with `vroom-express` HTTP wrapper for quick deployment [citation:12].

**Frameworks for building custom systems**: Combine **VROOM** or **better-route** for route optimization and dispatch UI, **pdptw-lns-solver** for online order insertion into live schedules, **oway-dispatch-console** for status-aware LTL routing with window violations, **mpee** for offline-capable embedded solving, and **Vantal Tech Exception Kit** or **Agentic Logistics** for exception detection and alerting to build a complete self-hosted dispatch and exception routing stack.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Transport dispatch and routing tools must comply with transportation regulations (HOS, DOT, FMCSA), data protection laws, and safety standards. Route optimization outputs must be validated against real-world constraints (road closures, vehicle restrictions, driver hours) before dispatch.
- Self-hosted open-source solutions require proper OSRM/Valhalla map data management, solver tuning, and integration with telematics and TMS systems.

---

**Made for logistics engineers, dispatch operators, fleet managers, and developers building real-time transport routing platforms.**  
Let's make real-time transport dispatch more open, responsive, and exception-aware.

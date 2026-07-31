# COTEMS — Campus Occupant Tracking & Emergency Mustering System

Prototype built for the CIN815 (Postgraduate Diploma in Information Systems) group project,
Fiji National University — College of Engineering, Science and Technology.

**Group:** Jotame Halofaki, Suka Buadromo, Viliame Kolinisau, Sushil Pipaliya

## What this is

A functional, browser-based prototype of COTEMS as specified in the project proposal: a system
that tracks staff, student, and visitor presence across FNU's Nasinu campus via checkpoint
scans, and generates a live, digital muster roll during emergencies instead of relying on manual
paper-based headcounts.

**[Live demo →](https://jhadmin-iig.github.io/cotems-fnu/)**

**[Mobile app prototype →](https://jhadmin-iig.github.io/cotems-fnu/mobile-app/index.html)**

## Features

- **Role-based sign-in** — Student/Staff, Visitor, Security Warden, System Administrator
- **Checkpoint check-in/out** — simulates tapping a posted QR code at a building entrance
- **Visitor self-registration kiosk** — issues a visitor pass, logs entry/exit
- **Live warden dashboard** — real-time occupancy per building, checkpoint activity feed
- **Emergency mustering** — declare an event, auto-generate a muster roll grouped by assembly
  point, track accounted-for status live via a tide-gauge visual
- **Admin console** — manage buildings and users, batch CSV import (in place of live middleware
  to the legacy student system, per the project's scope), data governance & privacy policy
  reference, full searchable audit log
- **Analytics** — occupancy by building, minutes-to-accounted-for by drill, bottleneck muster
  points across past events

## Running it

No build step — it's a single static HTML file per page.

```bash
# clone, then just open it
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

Or serve it locally:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Repository structure

```
index.html                     Full system prototype (current version)
mobile-app/index.html           Mobile-first app design and clickable prototype
diagrams/erd.svg                Entity-relationship diagram
diagrams/bpmn-as-is.svg          Current manual mustering process
diagrams/bpmn-to-be.svg          Proposed COTEMS digital process
archive/cotems-prototype-v1.html Earlier single-role prototype (kept for reference)
```

## Data & persistence

This prototype runs entirely in-browser using in-memory state — there is no backend server or
database wired up, and data resets on page reload. This is intentional for a pilot-stage
prototype/demonstration deliverable. The project's design document specifies the intended
production stack (Node.js/Express or Flask, PostgreSQL, Redis, JWT auth, Firebase Cloud
Messaging) for a future implementation phase.

## Scope note

Out of scope for this prototype, per the project proposal: continuous GPS/indoor positioning,
biometric identification, native mobile app store deployment, and direct integration with FNU's
legacy student management system.

## License

Academic project submission — CIN815, Fiji National University, 2026.

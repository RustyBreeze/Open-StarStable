# Open-StarStable

**An open source, free revival of Star Stable Online's 2014 client.**

Project inspired by [Story of Alicia](https://github.com/Story-Of-Alicia) - a free, open source alternative/hub for private servers where anyone can fork the project to host their own server. No single person should have a monopoly over preserving an old game.

> **Status:** Pre-development. Static analysis complete (~95%). Actively looking for contributors.

---

## Why 2014?

Star Stable Online has changed dramatically since its early years. The 2014 version represents an era many players remember deeply - dark and mystical themes, a unique atmosphere, the iconic stable doors loading screen, and a fundamentally different feeling to the world of Jorvik. This project exists to preserve and revive what was lost.

---

## What we have

- The 2014 client binary, statically analyzed to ~95% using IDA Free
- Mapped patch targets for bypassing server-side entity validation (the primary offline blocker)
- Mapped network login subsystem with known bypass addresses
- The 3D stable doors model from the original web launcher loading screen
- Documentation of all known PXStudio engine file formats
- Full understanding of the original NPAPI web launcher architecture
- The BetterSSO (2017) client/launcher source as a structural reference

## What we need

- A server developer (Python, Go, Node.js - language choice is flexible)
- Someone familiar with network protocol reverse engineering
- A frontend developer for the launcher recreation
- Anyone with PXStudio engine knowledge or old SSO experience

---

## Project goals

1. **Launcher recreation** - Recreate the original web launcher as a standalone desktop app, complete with the 3D stable doors loading screen and original music. First milestone, no server required.
2. **Client patching** - Patch the 2014 executable to run in offline/demo mode.
3. **Server implementation** - Build a server the patched client can connect to, based on protocol reverse engineering.
4. **Open hub** - A foundation others can fork to run their own servers, Story of Alicia style.

---

## Technical summary

The 2014 client runs on the **PXStudio engine**, a proprietary C/C++ engine confirmed by its original author Anders. The client launched via an NPAPI Chrome extension (now a dead technology), and hangs on the tip screen due to four entity null checks in `sub_4519E0` failing without a server. These are the two primary problems to solve.

Full technical documentation is in the [Wiki](../../wiki).

---

## Repository structure
```
/docs        - Reverse engineering notes and technical documentation  
/launcher    - Launcher recreation (planned)  
/server      - Server implementation (planned)  
/tools       - Patching utilities (planned)  
```

---

## Contributing

You do not need to know Star Stable Online. All SSO-specific knowledge is documented in the Wiki. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

GPL-2.0 — see [LICENSE](LICENSE).

---

## Legal note

This project targets the abandoned 2014 client which cannot connect to any official servers. It does not touch the modern live SSO service. No original game assets are distributed in this repository.

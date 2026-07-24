# Dear Stranger 💙

> **Because sometimes it's easier to talk to a stranger.**

![Kotlin](https://img.shields.io/badge/Kotlin-2.0-blueviolet?logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-UI-4285F4?logo=jetpackcompose&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Clean%20%2B%20MVVM-2ea44f)
![Firebase](https://img.shields.io/badge/Backend-Firebase-FFCA28?logo=firebase&logoColor=black)
![Status](https://img.shields.io/badge/status-in%20development-yellow)

An anonymous peer-support platform where people can safely share their thoughts,
emotions, and life experiences without fear of being judged. No likes, no followers,
no popularity contests — just honest, empathetic conversations between strangers.

  ---

## 📱 Screenshots

> _Coming soon — Sprint 1 is building the foundation._

| Feed | Post | Profile |
  |------|------|---------|
| _tbd_ | _tbd_ | _tbd_ |

  ---

## ✨ Features (MVP)

- 🔐 **Auth** — Email/Password & Google Sign-In, persistent sessions
- 📰 **Community Feed** — browse anonymous stories, pull-to-refresh, infinite scroll
- ✍️  **Create Posts** — share anonymously, with categories and optional images
- 💬 **Comments** — supportive, anonymous conversations
- 🔍 **Search & Categories** — find stories that match your situation
- 🔖 **Saved Posts** — bookmark meaningful stories (offline-ready)
- 🛡️  **Safety** — report content, block users, community guidelines
- 🔔 **Notifications** — replies and updates

  ---

## 🏗️  Tech Stack

| Layer | Technology |
  |-------|-----------|
| **Language** | Kotlin |
| **UI** | Jetpack Compose · Material 3 |
| **Architecture** | Clean Architecture + MVVM |
| **DI** | Hilt |
| **Async** | Coroutines · Flow |
| **Backend** | Firebase (Auth · Firestore · Storage · FCM) |
| **Local** | Room · DataStore |
| **Images** | Coil |

  ---

## 📐 Architecture

Dear Stranger follows **Clean Architecture** with an **MVVM** presentation layer and
unidirectional data flow:

UI (Compose) → ViewModel → UseCase → Repository → Firebase / Room

See [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) for the full breakdown.

  ---

## 📚 Documentation

- [Product Vision](docs/PRODUCT.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Roadmap](docs/ROADMAP.md)
- [Features](docs/FEATURES.md)
- [Coding Standards](docs/CODING_STANDARDS.md)

  ---

## 🚧 Project Status

**Sprint 1 — Foundation** (in progress): project setup, design system, navigation,
and authentication. Track progress on the [project board](https://github.com/users/thanhthuykma/projects/3).

  ---

## 👩‍ Author

Built by [Thuy](https://github.com/thanhthuykma)
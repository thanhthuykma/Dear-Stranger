# Architecture

## Overview

Dear Stranger follows **Clean Architecture** with the **MVVM** presentation pattern.

The architecture is designed to achieve:

- Separation of concerns
- Scalability
- Testability
- Maintainability

The project follows Google's recommended Android architecture while keeping the codebase simple enough for a solo developer.

---

# Tech Stack

## Language

- Kotlin

## UI

- Jetpack Compose
- Material 3
- Navigation Compose

## Architecture

- MVVM
- Clean Architecture

## Dependency Injection

- Hilt

## Local Storage

- Room Database
- DataStore

## Backend

- Firebase Authentication
- Cloud Firestore
- Firebase Cloud Storage
- Firebase Cloud Messaging

## Background Processing

- WorkManager

## Image Loading

- Coil

## Asynchronous Programming

- Kotlin Coroutines
- Kotlin Flow

---

# Project Structure

```
app/
│
├── core/
│   ├── common/
│   ├── designsystem/
│   ├── ui/
│   ├── navigation/
│   └── util/
│
├── data/
│   ├── local/
│   ├── remote/
│   ├── repository/
│   └── mapper/
│
├── domain/
│   ├── model/
│   ├── repository/
│   └── usecase/
│
├── feature/
│   ├── auth/
│   ├── feed/
│   ├── post/
│   ├── comment/
│   ├── profile/
│   ├── notification/
│   └── search/
│
└── di/
```

---

# Layer Responsibilities

## Presentation Layer

Responsible for:

- UI
- State management
- User interactions

Components:

- Compose Screens
- ViewModels
- UI State
- Navigation

The Presentation layer must never communicate directly with Firebase or Room.

---

## Domain Layer

Responsible for:

- Business logic
- Use Cases
- Domain Models
- Repository Interfaces

The Domain layer has **no dependency on Android Framework**.

---

## Data Layer

Responsible for:

- Fetching data
- Caching
- Repository implementations
- Mapping between local, remote and domain models

Data sources include:

- Firebase
- Room Database

---

# Feature-based Organization

Each feature owns its own presentation logic.

Example:

```
feature/
    feed/

        FeedScreen.kt

        FeedViewModel.kt

        FeedUiState.kt

        FeedEvent.kt
```

This keeps features isolated and easier to maintain.

---

# Data Flow

```
User Action
      │
      ▼
Compose Screen
      │
      ▼
ViewModel
      │
      ▼
Use Case
      │
      ▼
Repository
      │
      ├────────► Firebase
      │
      └────────► Room
      │
      ▼
Result
      │
      ▼
StateFlow
      │
      ▼
Compose UI
```

---

# Offline Strategy

Dear Stranger follows an **offline-first** approach whenever possible.

Strategy:

1. Read from Room.
2. Fetch latest data from Firebase.
3. Update local cache.
4. UI automatically updates.

This improves performance and allows users to continue browsing while offline.

---

# State Management

The application uses:

- StateFlow for UI state
- SharedFlow for one-time events

Each screen exposes a single immutable UI state.

Example:

```
FeedUiState
│
├── loading
├── posts
├── error
└── isRefreshing
```

---

# Error Handling

Errors are categorized into:

- Network
- Authentication
- Validation
- Unknown

The UI should always display meaningful error messages.

---

# Dependency Injection

Hilt is used to provide:

- Repositories
- Firebase services
- Room database
- Use Cases

Dependencies are injected through constructors whenever possible.

---

# Navigation

Navigation Compose is used.

Top-level destinations:

- Authentication
- Feed
- Search
- Notifications
- Profile
- Post Details

---

# Testing Strategy

## Unit Tests

- ViewModels
- Use Cases
- Repository

## UI Tests

- Compose UI Tests

## Manual Testing

Before each release:

- Authentication
- Feed
- Create Post
- Comment
- Notifications

---

# Engineering Principles

- Keep UI stateless whenever possible.
- Prefer immutable state.
- One responsibility per class.
- Avoid business logic inside Composables.
- Repository is the single source of truth.
- Build reusable UI components.
- Optimize for readability over cleverness.

---

# Future Improvements

Potential improvements after MVP:

- Multi-module architecture
- Offline write synchronization
- Remote Config
- Crashlytics
- Analytics
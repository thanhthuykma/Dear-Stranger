# Dear Stranger Roadmap

> **Product Goal**
>
> Build and publish a production-ready Android application that demonstrates modern Android development best practices while creating a safe community where people can anonymously share their thoughts without fear of being judged.

---

# Project Timeline

This roadmap assumes:

- One Android developer
- Part-time development (evenings & weekends)
- Learning while building
- Focus on quality over speed

Estimated duration: **12–16 weeks**

---

# Sprint 0 — Planning (1 Day)

## Goal

Turn the idea into a clear development plan.

## Deliverables

- ✅ Product Vision
- ✅ MVP Definition
- ✅ Tech Stack
- ✅ Architecture Overview
- ✅ GitHub Repository
- ✅ Project Documentation

---

# Sprint 1 — Foundation (2 Weeks)

## Goal

Build a solid project foundation.

## Features

- Android project setup
- Material 3 theme
- Navigation Compose
- Firebase configuration
- Email Authentication
- Google Sign-In
- Persistent login session

## Technical Tasks

- Setup Hilt
- Setup Version Catalog
- Configure Gradle
- Setup CI (optional)

## Definition of Done

A user can:

- Register
- Login
- Logout
- Stay logged in after reopening the app

---

# Sprint 2 — Community Feed (3 Weeks)

## Goal

Users can explore anonymous stories.

## Features

- Home Feed
- Pagination
- Categories
- Search
- Pull-to-refresh

## Technical Tasks

- Firestore integration
- Room caching
- Repository implementation
- Paging 3
- Loading & Error handling

## Definition of Done

Users can:

- Browse community posts
- Search posts
- Filter by category
- Read cached content offline

---

# Sprint 3 — Anonymous Discussions (3 Weeks)

## Goal

Users can participate in conversations.

## Features

- Create post
- Post details
- Anonymous comments
- Edit/Delete own posts
- Save posts
- User profile

## Technical Tasks

- Firebase Storage
- Form validation
- Image upload
- UI state management

## Definition of Done

Users can:

- Publish posts
- Comment anonymously
- Save favorite posts
- Manage their own content

---

# Sprint 4 — Engagement & Safety (2 Weeks)

## Goal

Make the community safer and more engaging.

## Features

- Push notifications
- Report content
- Block users
- Community Guidelines

## Technical Tasks

- Firebase Cloud Messaging
- WorkManager
- Notification Channels
- Background synchronization

## Definition of Done

Users can:

- Receive notifications
- Report harmful content
- Block unwanted users

---

# Sprint 5 — Polish & Release (2–4 Weeks)

## Goal

Prepare Dear Stranger for production.

## Tasks

### Quality

- Bug fixing
- UI polishing
- Accessibility improvements
- Performance optimization

### Testing

- Unit Tests
- UI Tests
- Manual Testing

### Play Store

- App Icon
- Feature Graphic
- Screenshots
- Privacy Policy
- Terms of Service
- Data Safety Form
- Internal Testing
- Production Release

## Definition of Done

- App is stable
- No critical bugs
- Successfully published on Google Play

---

# Version 1 Scope (MVP)

## Authentication

- Email & Password
- Google Sign-In

## Community

- Anonymous posts
- Comments
- Categories
- Search

## Profile

- Basic profile
- Saved posts
- Settings

## Notifications

- Push notifications

## Offline Support

- Room caching

## Safety

- Report
- Block

---

# Future Roadmap (Post MVP)

These features are intentionally excluded from Version 1.

## Community

- Trending posts
- Rich profiles
- Tags

## Matching

- Anonymous matching
- Private conversations

## Wellness

- Mood tracking
- Guided journaling
- Breathing exercises

## AI

- AI moderation
- AI journaling
- AI writing assistant

---

# Success Criteria

Version 1 is considered successful when:

- Users can register and sign in.
- Users can anonymously share stories.
- Users can interact with the community.
- Push notifications work correctly.
- Offline reading is supported.
- The application is available on Google Play.
- The project demonstrates production-level Android development skills.

---

# Engineering Principles

- Build one feature at a time.
- Ship early and iterate.
- Keep the MVP small.
- Prefer maintainability over clever code.
- Every sprint should end with a working application.
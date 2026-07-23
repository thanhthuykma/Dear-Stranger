# Features

> This document defines the functional scope of Dear Stranger MVP.
>
> Every feature includes:
>
> - User Story
> - Acceptance Criteria
> - Priority
> - Status
>
> Features may evolve throughout development as the product matures.

---

# MVP Features

## Authentication

### Goal

Allow users to securely access the application.

### User Stories

As a new user,
I want to create an account,
so that my data can be saved securely.

As a returning user,
I want to sign in quickly,
so that I can continue where I left off.

### Acceptance Criteria

- User can register with email & password
- User can sign in with email & password
- User can sign in with Google
- User stays signed in after reopening the app
- User can log out

### Priority

⭐⭐⭐⭐⭐

### Status

Planned

---

## Community Feed

### Goal

Allow users to discover anonymous stories.

### User Stories

As a user,
I want to browse stories,
so that I know I'm not alone.

### Acceptance Criteria

- Feed loads successfully
- Loading indicator is shown
- Empty state is supported
- Error state is supported
- Pull-to-refresh works
- Infinite scrolling works

### Priority

⭐⭐⭐⭐⭐

### Status

Planned

---

## Create Post

### Goal

Allow users to anonymously share their thoughts.

### User Stories

As a user,
I want to post anonymously,
so that I can express myself without fear of being judged.

### Acceptance Criteria

- User can write a post
- User can optionally attach an image
- User can select a category
- Validation is implemented
- Upload progress is shown

### Priority

⭐⭐⭐⭐⭐

### Status

Planned

---

## Post Details

### Goal

Allow users to read a story in detail.

### User Stories

As a user,
I want to open a post,
so that I can read the full story.

### Acceptance Criteria

- Full content is displayed
- Images load correctly
- Comments are displayed
- Loading & Error states are handled

### Priority

⭐⭐⭐⭐⭐

### Status

Planned

---

## Comments

### Goal

Enable meaningful anonymous conversations.

### User Stories

As a user,
I want to leave supportive comments,
so that I can encourage others.

### Acceptance Criteria

- User can add comments
- Comments update without reopening the screen
- Empty comment validation
- Delete own comment

### Priority

⭐⭐⭐⭐⭐

### Status

Planned

---

## Search

### Goal

Help users discover relevant stories.

### User Stories

As a user,
I want to search posts,
so that I can find stories related to my situation.

### Acceptance Criteria

- Keyword search
- Recent searches
- Empty state
- No-result state

### Priority

⭐⭐⭐⭐

### Status

Planned

---

## Categories

### Goal

Organize community posts.

### Acceptance Criteria

- Browse by category
- Filter feed
- Category chips
- Selected state

### Priority

⭐⭐⭐⭐

### Status

Planned

---

## Profile

### Goal

Allow users to manage their account.

### Acceptance Criteria

- View profile
- Edit display name
- View saved posts
- Logout

### Priority

⭐⭐⭐⭐

### Status

Planned

---

## Saved Posts

### Goal

Allow users to bookmark meaningful stories.

### Acceptance Criteria

- Save post
- Remove saved post
- Offline support

### Priority

⭐⭐⭐

### Status

Planned

---

## Notifications

### Goal

Keep users informed.

### Acceptance Criteria

- Receive push notifications
- Open related post
- Notification settings

### Priority

⭐⭐⭐

### Status

Planned

---

## Offline Support

### Goal

Allow users to continue reading without internet.

### Acceptance Criteria

- Feed cached locally
- Saved posts available offline
- Automatic synchronization

### Priority

⭐⭐⭐⭐

### Status

Planned

---

## Report Content

### Goal

Maintain a safe community.

### Acceptance Criteria

- Report post
- Report comment
- Select report reason
- Confirmation message

### Priority

⭐⭐⭐⭐

### Status

Planned

---

## Block User

### Goal

Protect users from unwanted interactions.

### Acceptance Criteria

- Block user
- Hide blocked user's content
- Unblock user

### Priority

⭐⭐⭐

### Status

Planned

---

# Future Features

These features are intentionally excluded from MVP.

## Anonymous Matching

Connect users with similar experiences.

Status: Future

---

## Private Chat

One-to-one anonymous conversations.

Status: Future

---

## Mood Tracker

Track emotional wellbeing over time.

Status: Future

---

## Guided Journal

Daily private journaling.

Status: Future

---

## AI Companion

AI-assisted emotional support.

Status: Future

---

## Wellness Exercises

Breathing exercises, meditation, gratitude journal.

Status: Future

---

# Non-Functional Requirements

The application should:

- Support Dark Mode
- Support offline reading
- Handle poor network conditions gracefully
- Follow Material Design 3
- Be responsive on different screen sizes
- Keep user data secure
- Provide meaningful loading and error states

---

# Definition of MVP

Version 1.0 is complete when:

- Authentication is fully functional.
- Users can create anonymous posts.
- Users can browse and search posts.
- Users can comment on posts.
- Push notifications work.
- Offline reading is supported.
- The application is successfully published on Google Play.
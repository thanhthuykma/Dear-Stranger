# Coding Standards

> This document defines the coding conventions used throughout the Dear Stranger project.
>
> The goal is to keep the codebase clean, consistent, and easy to maintain.

---

# General Principles

- Prefer readability over cleverness.
- Keep classes focused on a single responsibility.
- Avoid unnecessary abstractions.
- Write code for humans first.
- Follow Clean Architecture principles.

---

# Package Rules

## Business Logic

Business logic belongs in:

```
domain/
```

Never place business logic inside:

- Composable
- Activity
- Fragment
- Repository implementation

---

## UI

Every screen belongs to:

```
feature/<feature>
```

Example:

```
feature/feed
feature/profile
feature/post
```

---

## Shared Components

Reusable UI components belong to:

```
core/component
```

Examples:

- LoadingIndicator
- EmptyState
- ErrorView

---

## Design System

Reusable UI primitives belong to:

```
core/designsystem
```

Examples:

- DSButton
- DSTextField
- DSCard

---

# Naming Convention

## Classes

Use PascalCase.

Good

```kotlin
FeedViewModel
CreatePostUseCase
PostRepository
```

Avoid

```kotlin
feedVM
PostRepo
```

---

## Variables

Use camelCase.

Good

```kotlin
userName
currentUser
selectedCategory
```

Avoid

```kotlin
User_Name
Current_User
```

---

## Constants

Use UPPER_SNAKE_CASE.

```kotlin
MAX_POST_LENGTH

DEFAULT_PAGE_SIZE
```

---

# File Naming

Composable

```
FeedScreen.kt
```

ViewModel

```
FeedViewModel.kt
```

UI State

```
FeedUiState.kt
```

UI Event

```
FeedEvent.kt
```

Repository

```
PostRepository.kt
```

Repository Implementation

```
PostRepositoryImpl.kt
```

Use Case

```
CreatePostUseCase.kt
```

DTO

```
PostDto.kt
```

Entity

```
PostEntity.kt
```

Mapper

```
PostMapper.kt
```

---

# Compose Guidelines

## Screen

A Screen should:

- Display UI
- Receive UiState
- Receive callbacks

A Screen should NOT:

- Access Repository
- Access Firebase
- Launch coroutines
- Contain business logic

---

## ViewModel

ViewModel is responsible for:

- Business coordination
- Calling Use Cases
- Updating UI state

ViewModel should NOT:

- Know about Compose
- Reference UI components
- Hold Android Context

---

# UI State

Every screen owns one immutable UiState.

Example

```kotlin
data class FeedUiState(
    val isLoading: Boolean = false,
    val posts: List<Post> = emptyList(),
    val error: String? = null
)
```

Avoid multiple mutable states.

Bad

```kotlin
var loading by mutableStateOf(false)
var posts by mutableStateOf(...)
var error by mutableStateOf(...)
```

---

# UI Events

Use sealed interfaces.

```kotlin
sealed interface FeedEvent {

    data object Refresh : FeedEvent

    data class OpenPost(
        val id: String
    ) : FeedEvent
}
```

Every user interaction should go through:

```kotlin
viewModel.onEvent(...)
```

---

# State Management

Use:

```
StateFlow
```

for UI state.

Use:

```
SharedFlow
```

for one-time events.

Examples:

- Navigation
- Snackbar
- Toast

---

# Coroutines

Always launch coroutines inside:

```
viewModelScope
```

Never use:

```
GlobalScope
```

Avoid:

```
runBlocking
```

inside production code.

---

# Dependency Injection

Always prefer constructor injection.

```kotlin
class FeedViewModel @Inject constructor(
    private val getFeedUseCase: GetFeedUseCase
)
```

Avoid field injection whenever possible.

---

# Error Handling

Repositories return:

```kotlin
Result<T>
```

Never expose exceptions directly to the UI layer.

---

# Logging

Use:

```
Timber
```

Never use:

```
println()
```

Remove unnecessary debug logs before release.

---

# Comments

Write comments only when necessary.

Good

```kotlin
// Cache feed locally before emitting UI state.
```

Avoid

```kotlin
// Increment i
i++
```

Code should explain itself.

---

# Functions

A function should do one thing.

Prefer

```kotlin
fun uploadImage()

fun createPost()
```

instead of

```kotlin
fun uploadImageAndCreatePostAndRefreshFeed()
```

---

# Magic Numbers

Avoid

```kotlin
delay(3000)
```

Prefer

```kotlin
private const val SPLASH_DELAY = 3000L
```

---

# Commit Messages

Follow Conventional Commits.

Examples

```
feat: add Google Sign-In

fix: resolve feed pagination bug

refactor: simplify repository mapping

docs: update architecture

test: add login unit tests
```

---

# Project Conventions

## Repository Convention

Repositories expose only `suspend` functions or `Flow`.

Good

```kotlin
interface AuthRepository {

    suspend fun login(
        email: String,
        password: String
    ): Result<User>

    fun observeCurrentUser(): Flow<User?>
}
```

Repositories should never expose `LiveData`.

---

## UseCase Convention

Every UseCase should implement:

```kotlin
operator fun invoke()
```

Example

```kotlin
class LoginUseCase @Inject constructor(
    private val repository: AuthRepository
) {

    suspend operator fun invoke(
        email: String,
        password: String
    ): Result<User> {
        return repository.login(email, password)
    }
}
```

Usage

```kotlin
loginUseCase(email, password)
```

---

## Flow Naming Convention

Use meaningful names for asynchronous streams.

Examples

```kotlin
val uiState: StateFlow<FeedUiState>

val events: SharedFlow<FeedEvent>

val postsFlow: Flow<List<Post>>

val userFlow: Flow<User?>
```

---

## State Exposure Convention

Always expose immutable state.

```kotlin
private val _uiState = MutableStateFlow(FeedUiState())

val uiState = _uiState.asStateFlow()
```

Never expose `MutableStateFlow`.

---

## ViewModel Convention

A ViewModel should expose:

- One `StateFlow<UiState>`
- One `SharedFlow<Event>`

All UI interactions go through:

```kotlin
onEvent(...)
```

---

## Repository Responsibility

Repositories are responsible for:

- Fetching data
- Caching data
- Synchronizing local and remote sources
- Mapping data models

Repositories should NOT contain:

- UI logic
- Input validation
- Android UI dependencies

---

## UseCase Responsibility

One UseCase represents one business action.

Good

- LoginUseCase
- CreatePostUseCase
- SearchPostsUseCase

Avoid

```
LoginAndLoadProfileAndFetchPostsUseCase
```

---

# Definition of Done

A task is complete when:

- Code compiles successfully.
- No new warnings are introduced.
- UI follows Material Design 3.
- Business logic is tested where applicable.
- Documentation is updated if necessary.
- Self-review has been completed.
- Commit message follows Conventional Commits.

---

# Engineering Philosophy

When in doubt:

1. Choose the simpler solution.
2. Prefer readability over abstraction.
3. Keep business logic out of the UI.
4. Write code your future self will thank you for.
5. Build for maintainability over cleverness.
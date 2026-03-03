**📝 Task Manager App**

Product Requirements Document (PRD)

Version 1.0 \| Flutter Application

**1. Project Overview**

|                        |                               |
|------------------------|-------------------------------|
| **App Name**           | TaskFlow - Task Manager       |
| **Platform**           | Flutter (iOS & Android)       |
| **Version**            | 1.0.0                         |
| **Architecture**       | Clean Architecture + Riverpod |
| **Local Storage**      | Hive / SQLite                 |
| **Estimated Duration** | 3–4 Weeks                     |
| **GitHub Repo**        | flutter-task-manager          |

**Description**

TaskFlow is a local-first task management app built with Flutter. Users
can create, organize, prioritize, and track tasks without needing an
internet connection. The app focuses on simplicity, speed, and an
intuitive UI with smooth animations.

**2. Goals & Objectives**

- Allow users to manage daily tasks efficiently from their mobile device

- Provide filtering, sorting, and priority tagging for better
  organization

- Demonstrate Flutter best practices: Clean Architecture, Riverpod, Hive

- Serve as a strong GitHub portfolio reference project

**3. Tech Stack**

|                      |                                                   |
|----------------------|---------------------------------------------------|
| **Layer**            | **Technology**                                    |
| UI Framework         | Flutter 3.x                                       |
| State Management     | Riverpod 2.x                                      |
| Local Database       | Hive (NoSQL) or SQLite (drift)                    |
| Navigation           | GoRouter                                          |
| Dependency Injection | Riverpod Providers                                |
| Architecture         | Clean Architecture (Data / Domain / Presentation) |
| Testing              | flutter_test, mocktail                            |
| Code Quality         | flutter_lints, dart_code_metrics                  |

**4. Features & Requirements**

|  |  |  |
|----|----|----|
| **Feature** | **Priority** | **Notes** |
| Create / Edit / Delete Task | 🔴 Must Have | Title, description, due date, priority |
| Task List View | 🔴 Must Have | Sorted by priority and date |
| Filter by Status/Priority | 🔴 Must Have | Todo, In Progress, Done |
| Mark Task as Complete | 🔴 Must Have | Checkbox with animation |
| Local Persistence (Hive) | 🔴 Must Have | Data saved offline |
| Dark Mode Support | 🟡 Should Have | System-based toggle |
| Search Tasks | 🟡 Should Have | Real-time search bar |
| Due Date Reminder | 🟡 Should Have | Local notification |
| Statistics Screen | 🟢 Nice to Have | Tasks completed per day/week |
| Export to PDF | 🟢 Nice to Have | Using pdf package |

**5. Screens & Navigation**

**5.1 App Screens**

- Splash Screen – App logo with animation

- Home Screen – List of all tasks with filter chips

- Add/Edit Task Screen – Form with validation

- Task Detail Screen – Full view of task info

- Statistics Screen – Charts (fl_chart)

- Settings Screen – Theme toggle, notifications

**5.2 Navigation Flow**

GoRouter handles all navigation. Bottom navigation bar with 3 tabs:
Tasks, Stats, Settings.

**6. Data Models**

**Task Model**

```dart
class Task { 
  final String id; // UUID 
  final String title; // Required, max 100 chars 
  final String? description;// Optional 
  final DateTime? dueDate; // Optional 
  final Priority priority; // low | medium | high
  final TaskStatus status; // todo | inProgress | done 
  final DateTime createdAt; // Auto 
  final DateTime updatedAt; // Auto 
}
```

**7. Folder Structure**

```
lib/
├── core/
│   ├── constants/
│   ├── theme/
│   └── utils/
├── features/
│   └── tasks/
│       ├── data/
│       │   ├── models/
│       │   └── repositories/
│       ├── domain/
│       │   ├── entities/
│       │   └── usecases/
│       └── presentation/
│           ├── providers/
│           ├── screens/
│           └── widgets/
└── main.dart
```

**8. UI/UX Guidelines**

- Material Design 3 (Material You)

- Color Scheme: Primary \#1565C0 (Blue), Accent \#FF6F00 (Amber)

- Font: Google Fonts – Inter or Roboto

- Smooth animations using AnimatedList and Hero transitions

- Empty states with illustrated placeholders

- Swipe to delete with undo snackbar

**9. Testing Requirements**

**Unit Tests**

- All UseCases must have unit tests

- Repository tests with mocked data sources

**Widget Tests**

- Task list screen renders correctly

- Add task form validates properly

**Coverage Target**

Minimum 70% code coverage

**10. GitHub Setup**

- README.md with screenshots and setup instructions

- GitHub Actions CI for build and test

- .gitignore for Flutter projects

- Feature branches: feature/task-crud, feature/filters

- Commit convention: feat:, fix:, chore:, docs:

**11. Deliverables Checklist**

|                                |            |
|:-------------------------------|:----------:|
| **Deliverable**                | **Status** |
| Complete source code on GitHub |     ☐      |
| README with screenshots/GIFs   |     ☐      |
| APK release build              |     ☐      |
| Unit & Widget tests            |     ☐      |
| CI/CD workflow file            |     ☐      |

*Document prepared for AI Developer handoff. All requirements above are
mandatory unless marked 'Nice to Have'.*

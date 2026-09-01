# FitScan AI

### AI-Powered, Suitless 3D Fitness Scanning, Personalized Workouts, Multimodal Visual Intelligence & Adaptive Coaching

> **Understand your movement. Visualize your progress. Train smarter.**

FitScan AI is a React Native fitness application designed around a **suitless computer-vision scanning experience**.

Instead of requiring specialized physical scanning apparel, FitScan AI is designed to use a smartphone camera, guided capture workflows, computer vision, multimodal AI, fitness personalization, and adaptive coaching to create a richer fitness-tracking experience.

The platform combines:

* Suitless guided body scanning
* Computer-vision-assisted landmarks
* Silhouette analysis
* Multi-view capture
* Scan-quality validation
* Visual progress tracking
* Adaptive workouts
* AI fitness coaching
* Personalization AI
* Multimodal visual intelligence
* Workout feedback learning
* Multilingual UX
* RTL support
* Offline-aware architecture
* Privacy controls
* Recommendation systems
* Real-data persistence

FitScan AI is designed as a **fitness product**, not as a medical diagnostic platform. Measurements and visual estimates should be treated as estimates whose reliability depends on capture quality, device conditions, lighting, pose, camera placement, and the underlying computer-vision models.

---

# Table of Contents

* [1. Product Overview](#1-product-overview)
* [2. Vision](#2-vision)
* [3. Core Product Experience](#3-core-product-experience)
* [4. Architecture](#4-architecture)
* [5. Mobile Application Architecture](#5-mobile-application-architecture)
* [6. Suitless Scanning System](#6-suitless-scanning-system)
* [7. Multimodal Visual Intelligence](#7-multimodal-visual-intelligence)
* [8. AI Coach](#8-ai-coach)
* [9. Adaptive Workout Engine](#9-adaptive-workout-engine)
* [10. Personalization AI](#10-personalization-ai)
* [11. Progress Intelligence](#11-progress-intelligence)
* [12. Multilingual Architecture](#12-multilingual-architecture)
* [13. UI/UX System](#13-uiux-system)
* [14. Data Architecture](#14-data-architecture)
* [15. Privacy & Security](#15-privacy--security)
* [16. Offline-First Architecture](#16-offline-first-architecture)
* [17. API Architecture](#17-api-architecture)
* [18. AI Orchestration](#18-ai-orchestration)
* [19. Observability](#19-observability)
* [20. Testing](#20-testing)
* [21. Performance](#21-performance)
* [22. Project Structure](#22-project-structure)
* [23. Installation](#23-installation)
* [24. Environment Configuration](#24-environment-configuration)
* [25. Development Workflow](#25-development-workflow)
* [26. Example User Journeys](#26-example-user-journeys)
* [27. Monetization Architecture](#27-monetization-architecture)
* [28. Roadmap](#28-roadmap)
* [29. Contributing](#29-contributing)
* [30. License](#30-license)

---

# 1. Product Overview

FitScan AI is built around a simple idea:

> **A smartphone should become an intelligent fitness interface rather than just a workout timer.**

The application combines visual scanning with fitness intelligence.

```text
                         FITSCAN AI
                              │
       ┌──────────────────────┼──────────────────────┐
       │                      │                      │
       ▼                      ▼                      ▼
    SCANNING              WORKOUTS                COACH AI
       │                      │                      │
       ▼                      ▼                      ▼
 COMPUTER VISION         ADAPTIVE ENGINE       CONVERSATIONAL AI
       │                      │                      │
       └──────────────────────┼──────────────────────┘
                              ▼
                     PERSONALIZATION AI
                              │
                              ▼
                       USER TIMELINE
                              │
                              ▼
                       NEXT BEST ACTION
```

The central product loop is:

```text
SCAN
  ↓
UNDERSTAND
  ↓
PLAN
  ↓
TRAIN
  ↓
FEEDBACK
  ↓
LEARN
  ↓
ADAPT
  ↓
SCAN AGAIN
```

The application therefore becomes more useful over time.

---

# 2. Vision

## The Problem

Most fitness applications divide the experience into isolated features:

```text
Workout App
    +
Fitness Tracker
    +
Progress Charts
    +
AI Chatbot
    +
Camera Feature
```

These features often do not meaningfully communicate with one another.

FitScan AI attempts to unify them:

```text
                    USER
                     │
                     ▼
             VISUAL CAPTURE
                     │
                     ▼
               FITNESS DATA
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
      GOALS       WORKOUTS       HABITS
        │            │            │
        └────────────┼────────────┘
                     ▼
              PERSONALIZATION
                     │
                     ▼
                  AI COACH
                     │
                     ▼
              NEXT BEST ACTION
```

## Design Principles

### 1. Evidence before confidence

AI should distinguish between:

```text
OBSERVED
ESTIMATED
INFERRED
RECOMMENDED
UNCERTAIN
```

### 2. User control

Users should be able to control:

* personalization
* notifications
* saved visual assets
* AI processing
* language
* units
* appearance

### 3. Fitness, not appearance judgment

The application should emphasize:

* consistency
* movement
* strength
* mobility
* fitness behaviors
* exercise participation
* goals
* training routines

rather than ranking users against appearance ideals.

### 4. Real data over mock data

Development mocks may exist for tests and local development, but production flows should be designed around:

```text
REAL CAMERA INPUT
REAL DATABASE
REAL USER EVENTS
REAL WORKOUT HISTORY
REAL USER PREFERENCES
REAL AI REQUESTS
```

---

# 3. Core Product Experience

The primary navigation is:

```text
┌───────────────────────────────────────┐
│              FITSCAN AI               │
├───────────────────────────────────────┤
│                                       │
│ Home                                  │
│                                       │
│ Next Best Action                      │
│ ┌───────────────────────────────────┐ │
│ │ Your personalized recommendation │ │
│ │                                   │ │
│ │ [ Start ]                         │ │
│ └───────────────────────────────────┘ │
│                                       │
│ Recent Progress                       │
│                                       │
│ [ Scans ] [ Workouts ] [ Goals ]      │
│                                       │
│ FitScan AI                            │
│ Personalized insight                 │
│                                       │
└───────────────────────────────────────┘
```

Primary modules:

```text
Home
 ├── Personalized next action
 ├── AI insight
 ├── Progress snapshot
 └── Premium entry point

Scan
 ├── Camera setup
 ├── Guided capture
 ├── Frame quality
 ├── Coverage
 ├── Processing
 └── Scan result

Fitness
 ├── Workout discovery
 ├── Personalized plans
 ├── Live workout
 ├── Feedback
 └── History

Coach
 ├── Conversational AI
 ├── Scan explanations
 ├── Workout generation
 ├── Progress questions
 └── Recommendations

Progress
 ├── History
 ├── Visual comparison
 ├── Trends
 ├── Goals
 └── Weekly review

Profile
 ├── Preferences
 ├── Language
 ├── Units
 ├── Privacy
 └── Subscription
```

---

# 4. Architecture

FitScan AI uses a layered architecture designed to keep the mobile app, AI systems, data systems, and visual pipeline modular.

```text
┌─────────────────────────────────────────────────────┐
│                  REACT NATIVE APP                   │
│                                                     │
│ Home │ Scan │ Fitness │ Coach │ Progress │ Profile │
└───────────────────────┬─────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│                    APPLICATION                     │
│                                                     │
│ Navigation │ UI State │ Localization │ Analytics   │
└───────────────────────┬─────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│                   DOMAIN SERVICES                  │
│                                                     │
│ Scan │ Workout │ Coach │ Goals │ Personalization  │
└───────────────────────┬─────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│                    AI LAYER                        │
│                                                     │
│ Vision │ Coach │ Recommendations │ Planning       │
└───────────────────────┬─────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│                    DATA LAYER                      │
│                                                     │
│ PostgreSQL │ Cache │ Object Storage │ Analytics    │
└─────────────────────────────────────────────────────┘
```

## High-Level System Diagram

```mermaid
flowchart TD
    A[React Native App] --> B[API Gateway]

    B --> C[Scan Service]
    B --> D[Workout Service]
    B --> E[Coach Service]
    B --> F[Personalization Service]
    B --> G[Profile Service]
    B --> H[Notification Service]

    C --> I[Computer Vision]
    C --> J[Multimodal Vision AI]

    D --> K[Workout Engine]
    D --> J

    E --> L[Coach AI]
    E --> F

    F --> M[Recommendation Engine]

    C --> N[(PostgreSQL)]
    D --> N
    E --> N
    F --> N

    C --> O[(Object Storage)]
    J --> P[AI Providers]
    L --> P
```

---

# 5. Mobile Application Architecture

The application is built around a React Native / Expo-oriented architecture.

```text
mobile/
├── app/
│   ├── (tabs)/
│   │   ├── index.tsx
│   │   ├── scan.tsx
│   │   ├── fitness.tsx
│   │   ├── progress.tsx
│   │   └── profile.tsx
│   │
│   ├── scan/
│   ├── workouts/
│   ├── coach/
│   ├── goals/
│   └── settings/
│
├── src/
│   ├── ui/
│   ├── scan/
│   ├── workouts/
│   ├── coach/
│   ├── personalization/
│   ├── multimodal/
│   ├── i18n/
│   ├── analytics/
│   └── repositories/
│
└── package.json
```

## State Management

UI state is intentionally separated from domain state.

```text
UI STATE
 ├── loading
 ├── modal
 ├── selected tab
 ├── animation
 └── local form state

DOMAIN STATE
 ├── scan
 ├── workout
 ├── goal
 ├── coach session
 └── personalization profile
```

---

# 6. Suitless Scanning System

The scanning system is the core differentiator.

It is designed around guided smartphone capture rather than specialized scanning clothing.

## Scan Pipeline

```text
PHONE CAMERA
     │
     ▼
CAMERA PERMISSION
     │
     ▼
CAMERA READINESS
     │
     ▼
FRAME QUALITY
     │
     ├───────────┐
     ▼           ▼
 LIGHTING     SHARPNESS
     │           │
     └─────┬─────┘
           ▼
       BODY DETECTION
           │
           ▼
       POSE DETECTION
           │
           ▼
     FRAME STABILITY
           │
           ▼
      ANGLE TRACKING
           │
           ▼
      ROTATION GUIDE
           │
           ▼
     COVERAGE ENGINE
           │
           ▼
     FRAME SELECTION
           │
           ▼
      MULTI-VIEW AI
           │
           ▼
   MEASUREMENT ESTIMATION
           │
           ▼
     CONFIDENCE ENGINE
           │
           ▼
       QUALITY REPORT
```

## Scan State Machine

```mermaid
stateDiagram-v2
    [*] --> idle
    idle --> preparing
    preparing --> calibrating
    preparing --> failed
    calibrating --> capturing
    calibrating --> failed
    capturing --> processing
    capturing --> cancelled
    processing --> complete
    processing --> failed
    failed --> preparing
    cancelled --> idle
    complete --> [*]
```

## Scan Experience

```text
1. Ready
      ↓
2. Camera Check
      ↓
3. Position Yourself
      ↓
4. Full Body Detected
      ↓
5. Hold Steady
      ↓
6. Start Turning
      ↓
7. Live Rotation Guidance
      ↓
8. Coverage Tracking
      ↓
9. Final Angle
      ↓
10. Processing
      ↓
11. Scan Complete
```

---

## Frame Quality Model

Each frame can be evaluated using multiple signals.

```ts
interface FrameQuality {
  brightness: number;
  sharpness: number;
  framing: number;
  body: number;
  pose: number;
  total: number;
}
```

Conceptually:

```text
QUALITY =
    brightness   × 15%
  + sharpness    × 20%
  + framing      × 20%
  + body         × 25%
  + pose         × 20%
```

This can later be replaced with a learned model.

---

## Coverage Tracking

The scan divides the rotation into angle buckets:

```text
0° ─────────────── 360°

0°   30°   60°   90°
 │    │     │     │
 ▼    ▼     ▼     ▼

120° 150° 180° 210°
 │    │     │     │
 ▼    ▼     ▼     ▼

240° 270° 300° 330°
```

The coverage engine calculates:

```text
captured_angle_buckets
        ÷
total_angle_buckets
```

This prevents a user from completing a scan that technically contains too little rotational coverage.

---

## Rotation Guidance

```text
TOO FAST
   ↓
"Slow down your turn."

GOOD
   ↓
"Great pace. Keep turning."

TOO SLOW
   ↓
"Keep turning steadily."
```

---

## Scan Recovery

A scan should not be lost simply because:

* the user receives a notification
* the application enters the background
* capture is paused
* the phone orientation changes
* processing temporarily fails

Checkpoint state:

```ts
interface ScanRecoveryState {
  sessionId: string;
  frameCount: number;
  coverage: number;
  angle: number;
}
```

This allows a scan session to resume where practical.

---

# 7. Multimodal Visual Intelligence

FitScan AI treats visual data as a first-class domain.

```text
                  VISUAL INPUT
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
       IMAGE         VIDEO         LANDMARKS
        │              │              │
        └──────────────┼──────────────┘
                       ▼
                  SILHOUETTE
                       │
                       ▼
                  MULTI-VIEW
                       │
                       ▼
                    3D DATA
                       │
                       ▼
                  VISION AI
                       │
       ┌───────────────┼───────────────┐
       ▼               ▼               ▼
    INSIGHTS        GUIDANCE        VISUALIZATION
```

## Visual Asset Types

```ts
type VisualMediaType =
  | "image"
  | "video"
  | "landmark"
  | "silhouette"
  | "mesh"
  | "chart"
  | "animation";
```

---

## Landmark Pipeline

```text
RAW FRAME
   ↓
LANDMARK DETECTION
   ↓
CONFIDENCE FILTER
   ↓
NORMALIZATION
   ↓
TEMPORAL SMOOTHING
   ↓
LANDMARK TRACKER
   ↓
VISUAL OVERLAY
```

---

## Skeleton Visualization

```text
      HEAD
       │
   ┌───┴───┐
 SHOULDER SHOULDER
   │         │
   │         │
  HIP───────HIP
   │         │
 KNEE      KNEE
   │         │
ANKLE     ANKLE
```

The skeleton layer can be displayed as a live overlay during scanning or movement analysis.

---

## 3D Visualization

FitScan's visual architecture supports a future progression from:

```text
2D IMAGE
```

to:

```text
2D + LANDMARKS
```

to:

```text
SILHOUETTE
```

to:

```text
MULTI-VIEW REPRESENTATION
```

to:

```text
3D BODY REPRESENTATION
```

The current codebase intentionally keeps the 3D representation abstract so different reconstruction technologies can be plugged in later.

```ts
interface BodyMesh {
  vertices: MeshVertex[];
  triangles: Triangle[];
}
```

---

## Visual Comparison

```text
SCAN A                        SCAN B
──────                        ──────
IMAGE                         IMAGE
LANDMARKS                     LANDMARKS
QUALITY                       QUALITY
COVERAGE                      COVERAGE
   │                              │
   └─────────────┬────────────────┘
                 ▼
          COMPARISON ENGINE
                 │
       ┌─────────┼─────────┐
       ▼         ▼         ▼
    VISUAL    QUALITY   TIMELINE
    CHANGE   CONTEXT     CONTEXT
```

The system should avoid turning visual comparisons into appearance rankings.

---

# 8. AI Coach

FitScan AI Coach is designed as an application-level AI system rather than a generic chatbot.

```text
USER MESSAGE
     ↓
INTENT CLASSIFICATION
     ↓
COACH MODE
     ↓
USER CONTEXT
     ↓
MEMORY RETRIEVAL
     ↓
TOOL SELECTION
     ↓
REAL DATA ACCESS
     ↓
AI GENERATION
     ↓
RESPONSE CRITIC
     ↓
CONFIDENCE
     ↓
ACTION GENERATION
     ↓
USER
```

## Coach Modes

```text
GENERAL
WORKOUT
SCAN
PROGRESS
GOAL
MOVEMENT
HABIT
PLANNING
```

---

## Coach Tools

```text
get_latest_scan
get_progress
create_workout
get_goals
get_habits
```

The Coach can therefore transition from:

> "Here is generic fitness advice."

to:

> "Based on your current preferences and recent activity, here is a practical next step."

---

## Coach Evidence Model

Each response can carry evidence:

```ts
interface CoachEvidence {
  source:
    | "profile"
    | "scan"
    | "workout"
    | "movement"
    | "goal"
    | "habit"
    | "preference"
    | "user-message";

  referenceId?: string;

  statement: string;

  confidence: number;
}
```

The response architecture becomes:

```text
ANSWER
+
EVIDENCE
+
CONFIDENCE
+
LIMITATIONS
+
ACTIONS
```

---

## Coach Memory

The system can retain user-approved information such as:

```text
preferred workout duration
preferred workout types
preferred coach tone
favorite exercises
routine preferences
goal preferences
explicit user feedback
```

Memory should not be silently expanded into sensitive conclusions.

---

# 9. Adaptive Workout Engine

The workout engine transforms FitScan from a workout library into an adaptive system.

```text
USER PROFILE
     ↓
GOALS
     ↓
TIME AVAILABLE
     ↓
EQUIPMENT
     ↓
RECENT WORKOUTS
     ↓
EXERCISE PREFERENCES
     ↓
MOVEMENT FEEDBACK
     ↓
WORKOUT GENERATOR
     ↓
EXERCISE RANKING
     ↓
DIVERSITY FILTER
     ↓
AI OPTIMIZATION
     ↓
SAFETY VALIDATION
     ↓
WORKOUT
```

## Exercise Ranking

Each exercise can be scored by:

```text
equipment fit
+
difficulty fit
+
preference fit
+
novelty
+
historical completion
+
goal relevance
```

---

## Workout Structure

A generated session can be structured as:

```text
WARM-UP
   ↓
MAIN SESSION
   ↓
COOLDOWN
```

Example:

```text
20 MINUTES

Warm-up
03:00

Main
14:00

Cooldown
03:00
```

---

## Live Session

```text
WORKOUT
   │
   ▼
CURRENT EXERCISE
   │
   ├── TARGET
   ├── SETS
   ├── REST
   └── INSTRUCTIONS
          │
          ▼
       COMPLETE
          │
          ▼
     NEXT EXERCISE
```

---

## Feedback Loop

After a workout:

```text
How did it feel?

[ Easy ]
[ Comfortable ]
[ Challenging ]
```

That feedback updates personalization.

```text
WORKOUT
   ↓
FEEDBACK
   ↓
LEARNING SIGNAL
   ↓
PROFILE UPDATE
   ↓
NEXT WORKOUT
```

---

# 10. Personalization AI

Personalization is a shared intelligence layer.

```text
PROFILE
GOALS
WORKOUTS
SCANS
MOVEMENT
HABITS
COACH
SCHEDULE
ENGAGEMENT
FEEDBACK
     │
     ▼
SIGNAL ENGINE
     │
     ▼
RECENCY
     │
     ▼
CONFIDENCE
     │
     ▼
FEATURE AGGREGATION
     │
     ▼
PERSONALIZATION PROFILE
```

## Signal Example

```ts
interface PersonalizationSignalRecord {
  id: string;
  userId: string;

  type:
    | "preference"
    | "goal"
    | "workout"
    | "scan"
    | "movement"
    | "habit"
    | "coach"
    | "feedback"
    | "schedule"
    | "engagement";

  feature: string;
  value: number;
  confidence: number;
  timestamp: number;
}
```

---

## Recency

Recent behavior should generally have more influence than old behavior.

Conceptually:

```text
SIGNAL STRENGTH

100% ┤████████████████
 75% ┤████████████
 50% ┤████████
 25% ┤████
  0% ┤
      └────────────────────
       recent       older
```

---

## Exploration vs Exploitation

FitScan can balance:

```text
WHAT THE USER LIKES
```

with:

```text
WHAT THE USER HAS NOT TRIED
```

```text
LOW CONFIDENCE
     ↓
MORE EXPLORATION

HIGH CONFIDENCE
     ↓
MORE PERSONALIZATION
```

This prevents recommendations from becoming repetitive.

---

## Next Best Action

The home screen can use a recommendation score:

```text
goal fit
+ preference fit
+ schedule fit
+ recency fit
+ novelty
+ confidence
+ engagement
```

Example:

```text
User
 ↓
No workout recently
 ↓
Usually likes short sessions
 ↓
Goal = consistency
 ↓
Current time matches preferred schedule
 ↓
Recommendation:

"Try a short workout today."
```

---

# 11. Progress Intelligence

FitScan progress is designed to combine multiple dimensions.

```text
PROGRESS
├── Scan timeline
├── Workout consistency
├── Goal progress
├── Movement activity
├── Habit completion
├── User feedback
└── Coach reflections
```

## Progress Timeline

```text
JAN
 │
 ● Baseline
 │
 FEB
 │
 ● Workout milestone
 │
 MAR
 │
 ● New scan
 │
 APR
 │
 ● Goal milestone
```

---

## Progress Comparison

The comparison engine should account for scan quality:

```text
SCAN A
quality = high

SCAN B
quality = high

        ↓

better comparison confidence
```

versus:

```text
SCAN A
quality = high

SCAN B
quality = poor

        ↓

cautious comparison
```

This prevents low-quality data from being treated as equally reliable.

---

# 12. Multilingual Architecture

FitScan AI includes a centralized internationalization system.

Supported language architecture includes:

```text
English
French
Spanish
Portuguese
Arabic
Wolof
German
Italian
Japanese
Korean
```

## Translation Architecture

```text
UI
 │
 ▼
TRANSLATION KEY
 │
 ▼
LANGUAGE PROVIDER
 │
 ▼
TRANSLATION REGISTRY
 │
 ├── EN
 ├── FR
 ├── ES
 ├── PT
 ├── AR
 ├── WO
 ├── DE
 ├── IT
 ├── JA
 └── KO
```

---

## Fallback

Example:

```text
Wolof
   ↓
French
   ↓
English
```

This enables partial localization while translation coverage grows.

---

## RTL

Arabic uses RTL-aware presentation.

```text
LTR

ICON → TEXT → ACTION


RTL

ACTION ← TEXT ← ICON
```

The app architecture supports:

```ts
directionStyle(language)
localizedRow(language)
applyRTL(language)
```

---

## Localized AI

The AI Coach receives language context:

```text
USER LANGUAGE
      ↓
COACH LANGUAGE INSTRUCTION
      ↓
AI RESPONSE
      ↓
LOCALIZED UI
```

The same architecture can be applied to scan guidance, workout instructions, notifications, and progress summaries.

---

# 13. UI/UX System

FitScan AI uses a reusable UI system rather than individually styled screens.

```text
DESIGN TOKENS
     ↓
COMPONENTS
     ↓
SCREENS
     ↓
FLOWS
```

Core components include:

```text
Button
Card
Badge
Avatar
StatCard
ProgressBar
Skeleton
EmptyState
ErrorState
SectionHeader
SearchInput
FilterChip
IconButton
```

---

## Loading State

Instead of blank screens:

```text
┌──────────────────────────────┐
│██████████████████            │
│████████                        │
│                              │
│██████████████████████        │
│                              │
│████████████████              │
└──────────────────────────────┘
```

---

## Empty State

```text
       ✨

No scans yet

Complete your first guided
scan to create a baseline.

[ Start scan ]
```

---

## Error State

```text
Something went wrong

Your saved data is preserved.

[ Try again ]
```

---

## Scan UX

```text
CAMERA
  ↓
LIVE LANDMARKS
  ↓
QUALITY SCORE
  ↓
ROTATION ANGLE
  ↓
COVERAGE
  ↓
GUIDANCE
```

The user should always know:

```text
Where am I?
What should I do?
Is it working?
How much remains?
What happens next?
```

---

# 14. Data Architecture

FitScan is designed around real persisted data.

## Major Tables

```text
users
profiles
scans
scan_frames
measurements
workouts
workout_exercises
workout_sessions
workout_feedback
goals
habits
coach_sessions
coach_messages
coach_memories
coach_feedback
personalization_profiles
personalization_signals
visual_assets
visual_landmarks
visual_meshes
notifications
subscriptions
analytics_events
```

---

## Relational Model

```mermaid
erDiagram
    USERS ||--|| PROFILES : owns
    USERS ||--o{ SCANS : creates
    SCANS ||--o{ SCAN_FRAMES : contains
    SCANS ||--o{ MEASUREMENTS : produces

    USERS ||--o{ WORKOUTS : performs
    WORKOUTS ||--o{ WORKOUT_EXERCISES : contains
    WORKOUTS ||--o{ WORKOUT_SESSIONS : runs
    WORKOUT_SESSIONS ||--o{ WORKOUT_FEEDBACK : receives

    USERS ||--o{ GOALS : sets
    USERS ||--o{ HABITS : tracks

    USERS ||--o{ COACH_SESSIONS : starts
    COACH_SESSIONS ||--o{ COACH_MESSAGES : contains
    USERS ||--o{ COACH_MEMORIES : stores

    USERS ||--|| PERSONALIZATION_PROFILES : has
    USERS ||--o{ PERSONALIZATION_SIGNALS : generates

    USERS ||--o{ VISUAL_ASSETS : owns
```

---

# 15. Privacy & Security

Visual fitness data is sensitive and should be handled carefully.

## Privacy Principles

```text
DATA MINIMIZATION
       ↓
ACCESS CONTROL
       ↓
ENCRYPTION
       ↓
RETENTION POLICY
       ↓
USER DELETION
       ↓
AUDITABILITY
```

---

## Visual Privacy Settings

```ts
interface VisualPrivacySettings {
  saveImages: boolean;
  saveVideos: boolean;
  saveMeshes: boolean;
  uploadForAI: boolean;
}
```

This allows product-level control over visual retention.

---

## Data Deletion

Deleting personalization data should remove:

```text
personalization_signals
personalization_profile
coach_memories
```

Deleting visual data can remove:

```text
visual_assets
visual_landmarks
visual_meshes
```

---

## AI Privacy Boundary

The AI layer should receive only the minimum data needed to complete the task.

```text
MOBILE
  ↓
DATA SELECTION
  ↓
SANITIZATION
  ↓
AI REQUEST
```

---

# 16. Offline-First Architecture

FitScan should remain useful with intermittent connectivity.

```text
USER ACTION
     ↓
LOCAL STORE
     ↓
LOCAL UI UPDATE
     ↓
SYNC QUEUE
     ↓
NETWORK AVAILABLE
     ↓
SERVER
```

Examples:

```text
Save workout
    ↓
Local DB

Record feedback
    ↓
Local DB

Change language
    ↓
Local preference

Scan checkpoint
    ↓
Local recovery state
```

When network access returns:

```text
LOCAL QUEUE
     ↓
SYNC ENGINE
     ↓
SERVER
     ↓
ACK
     ↓
MARK COMPLETE
```

---

# 17. API Architecture

A possible backend API structure:

```text
/api/v1
│
├── auth
│   ├── login
│   ├── register
│   └── refresh
│
├── users
│   └── me
│
├── scans
│   ├── create
│   ├── upload
│   ├── process
│   ├── history
│   └── compare
│
├── workouts
│   ├── generate
│   ├── start
│   ├── complete
│   ├── feedback
│   └── history
│
├── coach
│   ├── session
│   ├── message
│   └── feedback
│
├── personalization
│   ├── profile
│   ├── signals
│   ├── recommendations
│   └── feedback
│
├── progress
│   ├── summary
│   ├── timeline
│   └── insights
│
└── preferences
    ├── language
    ├── units
    └── privacy
```

---

# 18. AI Orchestration

FitScan should not depend on one monolithic AI request.

Instead:

```text
                    AI ORCHESTRATOR
                           │
          ┌────────────────┼─────────────────┐
          ▼                ▼                 ▼
       VISION             COACH          WORKOUT
          │                │                 │
          ▼                ▼                 ▼
     VISUAL MODEL      LANGUAGE MODEL     PLANNER
          │                │                 │
          └────────────────┼─────────────────┘
                           ▼
                       VALIDATOR
                           │
                           ▼
                       RESPONSE
```

---

## Model Routing

Different tasks can be routed independently:

```text
IMAGE QUALITY
     ↓
VISION MODEL

LANDMARK ANALYSIS
     ↓
VISION MODEL

COACH QUESTION
     ↓
LANGUAGE MODEL

WORKOUT PLAN
     ↓
PLANNING MODEL

RECOMMENDATION
     ↓
PERSONALIZATION ENGINE
```

---

## AI Fallbacks

A production AI gateway can support:

```text
PRIMARY PROVIDER
       ↓
FAILURE
       ↓
SECONDARY PROVIDER
       ↓
FAILURE
       ↓
SAFE FALLBACK
```

The app should never leave the user staring at a broken AI request with no explanation.

---

# 19. Observability

Every important AI or scan request should generate telemetry.

## Useful Events

```text
scan_started
scan_frame_captured
scan_quality_warning
scan_completed
scan_failed

workout_generated
workout_started
workout_completed
workout_feedback

coach_message_sent
coach_response_received
coach_feedback

recommendation_shown
recommendation_accepted
recommendation_dismissed

language_changed
subscription_opened
```

---

## Scan Performance

Useful metrics:

```text
capture duration
processing duration
frame count
accepted frames
average frame quality
coverage
failure rate
retry rate
```

---

## Coach Performance

Useful metrics:

```text
response latency
tool latency
model latency
confidence
feedback rate
action acceptance
```

---

# 20. Testing

FitScan should use multiple levels of testing.

```text
UNIT TESTS
   ↓
DOMAIN TESTS
   ↓
SERVICE TESTS
   ↓
AI VALIDATION TESTS
   ↓
INTEGRATION TESTS
   ↓
DEVICE TESTS
   ↓
END-TO-END TESTS
```

## Scan Tests

Examples:

```text
angle normalization
coverage calculation
frame deduplication
quality scoring
landmark filtering
measurement validation
retry decisions
scan recovery
```

## Workout Tests

```text
equipment matching
difficulty matching
exercise ranking
workout generation
set completion
session state
feedback adaptation
personalization updates
```

## Coach Tests

```text
intent detection
mode detection
memory retrieval
tool selection
safety filtering
confidence calculation
response validation
```

---

# 21. Performance

The visual pipeline should be optimized aggressively.

## Performance Strategy

```text
CAMERA
  ↓
LOW-COST LOCAL FILTERS
  ↓
ONLY HIGH-VALUE FRAMES
  ↓
REPRESENTATIVE FRAME SET
  ↓
AI
```

Instead of sending every frame:

```text
30 FPS × 60 seconds
=
1,800 frames
```

the pipeline can select a much smaller representative set for expensive processing.

```text
1,800 RAW FRAMES
      ↓
QUALITY FILTER
      ↓
DEDUPLICATION
      ↓
ANGLE COVERAGE
      ↓
BEST REPRESENTATIVE FRAMES
      ↓
AI
```

This reduces:

* bandwidth
* AI cost
* processing time
* storage
* unnecessary inference

---

# 22. Project Structure

Recommended production structure:

```text
fitscan-ai/
│
├── app/
│   ├── _layout.tsx
│   ├── (tabs)/
│   ├── scan/
│   ├── workouts/
│   ├── coach/
│   ├── progress/
│   ├── goals/
│   ├── settings/
│   └── notifications/
│
├── src/
│
│   ├── ui/
│   │   ├── theme/
│   │   ├── components/
│   │   ├── forms/
│   │   ├── motion/
│   │   ├── accessibility/
│   │   └── layout/
│   │
│   ├── scan/
│   │   ├── v4/
│   │   ├── camera/
│   │   ├── processing/
│   │   └── visualization/
│   │
│   ├── workouts/
│   │   └── v6/
│   │
│   ├── coach/
│   │   └── v5/
│   │
│   ├── personalization/
│   │   └── v7/
│   │
│   ├── multimodal/
│   │   └── v8/
│   │
│   ├── i18n/
│   │
│   ├── repositories/
│   │
│   ├── analytics/
│   │
│   ├── auth/
│   │
│   └── services/
│
├── server/
│   ├── routes/
│   ├── services/
│   ├── repositories/
│   ├── AI/
│   └── workers/
│
├── migrations/
│
├── tests/
│
├── assets/
│
└── package.json
```

---

# 23. Installation

## Requirements

Recommended environment:

```text
Node.js
npm / pnpm / yarn
Expo CLI
React Native development environment
iOS Simulator or physical iPhone
Android Emulator or physical Android device
PostgreSQL
Redis
Object storage
AI provider credentials
```

## Clone

```bash
git clone https://github.com/YOUR_USERNAME/fitscan-ai.git

cd fitscan-ai
```

## Install

```bash
npm install
```

or:

```bash
pnpm install
```

## Start Expo

```bash
npx expo start
```

---

# 24. Environment Configuration

Create:

```text
.env
```

Example:

```env
APP_ENV=development

API_BASE_URL=http://localhost:3000

DATABASE_URL=postgresql://user:password@localhost:5432/fitscan

REDIS_URL=redis://localhost:6379

AI_API_KEY=replace_me

VISION_API_KEY=replace_me

OBJECT_STORAGE_BUCKET=fitscan-assets

ANALYTICS_KEY=replace_me
```

Do not commit secrets.

```gitignore
.env
.env.local
.env.production
```

---

# 25. Development Workflow

## Run Mobile App

```bash
npx expo start
```

## Run Backend

```bash
npm run server
```

## Run Tests

```bash
npm test
```

## Type Check

```bash
npm run typecheck
```

## Lint

```bash
npm run lint
```

## Build

```bash
npx expo prebuild
```

Production builds should use the application's configured EAS or native build pipeline.

---

# 26. Example User Journeys

## Journey A — First Scan

```text
INSTALL
  ↓
ONBOARDING
  ↓
CHOOSE LANGUAGE
  ↓
CHOOSE PREFERENCES
  ↓
CREATE PROFILE
  ↓
START SCAN
  ↓
CAMERA GUIDANCE
  ↓
BODY DETECTION
  ↓
ROTATE
  ↓
SCAN COMPLETE
  ↓
RESULT
  ↓
CREATE BASELINE
```

---

## Journey B — Personalized Workout

```text
OPEN APP
   ↓
PERSONALIZED HOME
   ↓
"Your next best step"
   ↓
START WORKOUT
   ↓
AI-GENERATED SESSION
   ↓
LIVE EXERCISES
   ↓
COMPLETE
   ↓
FEEDBACK
   ↓
PERSONALIZATION UPDATE
```

---

## Journey C — Ask Coach

```text
USER:

"What should I do today?"

        ↓

COACH CONTEXT

PROFILE
+
GOAL
+
WORKOUT HISTORY
+
PREFERENCES

        ↓

RECOMMENDATION

        ↓

"Try a short session today."

        ↓

[Start workout]
```

---

## Journey D — Visual Progress

```text
OPEN PROGRESS
      ↓
SELECT SCAN A
      ↓
SELECT SCAN B
      ↓
QUALITY CHECK
      ↓
VISUAL COMPARISON
      ↓
TIMELINE
      ↓
AI EXPLANATION
```

---

# 27. Monetization Architecture

FitScan can support a freemium model.

## Free Tier

Potential functionality:

```text
basic profile
limited scans
basic workouts
basic progress
basic Coach AI
basic personalization
```

## Premium Tier

Potential functionality:

```text
advanced AI Coach
expanded scan history
advanced visualizations
3D visualization
deeper personalization
adaptive plans
advanced progress analysis
extended AI usage
premium insights
```

---

## Entitlement Architecture

```text
USER
 ↓
SUBSCRIPTION
 ↓
ENTITLEMENTS
 ↓
FEATURE GATE
```

Example:

```ts
interface Entitlements {
  advancedCoach: boolean;
  advancedVisualization: boolean;
  extendedHistory: boolean;
  premiumPlans: boolean;
}
```

The UI should clearly explain what is included rather than interrupting the user unexpectedly.

---

# 28. Roadmap

## Phase 1 — Foundation

```text
✓ React Native app
✓ Authentication
✓ Core navigation
✓ Design system
✓ Database
✓ Basic workouts
✓ Basic Coach
✓ Basic scanning flow
```

## Phase 2 — Computer Vision

```text
□ Production pose model
□ Production segmentation
□ Better frame-quality model
□ Device-specific calibration
□ Improved camera pipeline
□ Multi-view reconstruction
□ 3D representation
```

## Phase 3 — AI Intelligence

```text
□ Production Coach orchestration
□ Better recommendation ranking
□ Retrieval-augmented fitness knowledge
□ Personalization model
□ Tool-calling
□ Feedback learning
```

## Phase 4 — Advanced Visuals

```text
□ Interactive 3D viewer
□ Motion replay
□ Visual timeline
□ Exercise overlays
□ Advanced progress visualization
```

## Phase 5 — Globalization

```text
□ English
□ French
□ Spanish
□ Portuguese
□ Arabic
□ Wolof
□ German
□ Italian
□ Japanese
□ Korean
```

## Phase 6 — Production

```text
□ App Store release
□ Google Play release
□ Observability
□ Automated CI/CD
□ Security audit
□ Privacy review
□ AI evaluation suite
□ Performance optimization
```

---

# 29. Contributing

Contributions should focus on modular improvements.

Suggested workflow:

```bash
git checkout -b feature/better-scan-guidance
```

Make changes, test them, then:

```bash
npm test
npm run lint
npm run typecheck
```

Commit:

```bash
git commit -m "Improve scan guidance"
```

Push:

```bash
git push origin feature/better-scan-guidance
```

Open a pull request.

---

# 30. License

Choose the license appropriate for the repository.

Example:

```text
MIT License
```

or a commercial proprietary license if FitScan AI is intended to remain closed-source.

---

# Technical Architecture Summary

FitScan AI ultimately operates as a connected intelligence system:

```mermaid
flowchart TB

    USER[User]

    MOBILE[React Native Mobile App]

    SCAN[Suitless Scan Engine]
    VISUAL[Multimodal Visual Engine]
    WORKOUT[Adaptive Workout Engine]
    COACH[AI Coach]
    PERSONAL[Personalization AI]
    I18N[Internationalization]
    PROGRESS[Progress Intelligence]

    API[API Gateway]

    DB[(PostgreSQL)]
    CACHE[(Redis)]
    STORAGE[(Object Storage)]

    VISION[Vision AI]
    LLM[Language AI]
    ANALYTICS[Analytics]

    USER --> MOBILE

    MOBILE --> SCAN
    MOBILE --> WORKOUT
    MOBILE --> COACH
    MOBILE --> PROGRESS
    MOBILE --> I18N

    SCAN --> VISUAL
    VISUAL --> VISION

    COACH --> PERSONAL
    WORKOUT --> PERSONAL
    PROGRESS --> PERSONAL
    SCAN --> PERSONAL

    MOBILE --> API

    API --> DB
    API --> CACHE
    API --> STORAGE

    API --> COACH
    API --> WORKOUT
    API --> SCAN
    API --> PERSONAL

    COACH --> LLM
    PERSONAL --> LLM

    API --> ANALYTICS
```

---

# The FitScan Intelligence Loop

The defining architecture is:

```text
                     ┌──────────────┐
                     │    USER      │
                     └──────┬───────┘
                            │
                            ▼
                   ┌────────────────┐
                   │     SCAN       │
                   └───────┬────────┘
                           │
                           ▼
                   ┌────────────────┐
                   │ VISUAL ENGINE  │
                   └───────┬────────┘
                           │
                           ▼
                    ┌──────────────┐
                    │ FITNESS DATA │
                    └──────┬───────┘
                           │
               ┌───────────┼───────────┐
               ▼           ▼           ▼
           WORKOUT       GOALS       HABITS
               │           │           │
               └───────────┼───────────┘
                           ▼
                  ┌─────────────────┐
                  │ PERSONALIZATION │
                  │       AI        │
                  └────────┬────────┘
                           │
                           ▼
                     ┌────────────┐
                     │  AI COACH  │
                     └─────┬──────┘
                           │
                           ▼
                 ┌────────────────────┐
                 │ NEXT BEST ACTION   │
                 └─────────┬──────────┘
                           │
                           ▼
                         USER
                           │
                           ▼
                       FEEDBACK
                           │
                           └───────────────► LEARNING
```

---

# Why FitScan AI Is Different

The long-term opportunity is not simply:

> "Use AI to make a fitness app."

It is to create a connected fitness intelligence platform:

```text
CAMERA
  +
COMPUTER VISION
  +
MULTIMODAL AI
  +
WORKOUT ENGINE
  +
PERSONALIZATION
  +
AI COACH
  +
PROGRESS HISTORY
  +
USER FEEDBACK
```

into:

```text
                    FITSCAN AI
                        │
                        ▼
               PERSONAL FITNESS OS
```

The product becomes progressively more useful because every meaningful interaction can feed the next decision:

```text
SCAN
  ↓
CONTEXT
  ↓
RECOMMENDATION
  ↓
WORKOUT
  ↓
FEEDBACK
  ↓
PERSONALIZATION
  ↓
COACH
  ↓
NEXT RECOMMENDATION
```

---

# Engineering Philosophy

FitScan AI should always prioritize:

```text
REAL DATA
over
MOCK DATA

USER CONTROL
over
HIDDEN PERSONALIZATION

QUALITY SIGNALS
over
BLIND AI CONFIDENCE

MODULAR AI
over
MONOLITHIC AI

ACCESSIBLE UX
over
DECORATIVE COMPLEXITY

CONSISTENT PROGRESS
over
EXTREME SHORTCUTS
```

The result is a React Native fitness platform where **scanning, visualization, workouts, AI coaching, personalization, multilingual UX, and progress intelligence operate as one integrated product rather than a collection of disconnected features.**

---

# Final Architecture Snapshot

```text
┌─────────────────────────────────────────────────────────┐
│                     FITSCAN AI                          │
│                                                         │
│  ┌────────┐ ┌──────────┐ ┌────────┐ ┌──────────────┐  │
│  │ Scan AI│ │ Workout  │ │ Coach  │ │ Personalize  │  │
│  └───┬────┘ └────┬─────┘ └───┬────┘ └──────┬───────┘  │
│      │             │          │              │          │
│      └─────────────┴──────────┴──────────────┘          │
│                         │                               │
│                         ▼                               │
│                ┌─────────────────┐                      │
│                │ Intelligence Hub│                      │
│                └────────┬────────┘                      │
│                         │                               │
│            ┌────────────┼─────────────┐                 │
│            ▼            ▼             ▼                 │
│         Progress     Feedback      Recommendations      │
│            │            │             │                 │
│            └────────────┼─────────────┘                 │
│                         ▼                               │
│                       USER                              │
└─────────────────────────────────────────────────────────┘
```

**FitScan AI — Scan. Understand. Train. Adapt.**

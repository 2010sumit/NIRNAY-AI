# Architecture and Database Contract

## 1. System Overview
NIRNAY AI is a Decision & Commitment Intelligence platform designed to extract, track, and monitor decisions made during meetings, tracking drift over time. 

## 2. Frontend Architecture
- **Framework**: Next.js (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **State Management**: React Context / Hooks
- **Error Handling**: React Error Boundaries

## 3. Backend Architecture
- **Environment**: Next.js API Routes (Serverless) / Node.js
- **Validation**: Zod
- **Error Handling**: Centralized error middleware

## 4. AI Pipeline
- Abstraction layer for AI Provider (e.g., OpenAI, Gemini, or Mock/Demo Provider)
- Transcription, Extraction, and Semantic Matching workflows.

## 5. Database Architecture
- **Database**: PostgreSQL
- **ORM**: Prisma
- **Core Entities**:
  - `User`, `Workspace`, `WorkspaceMember`
  - `Meeting`, `Transcript`, `TranscriptSegment`
  - `Decision`, `DecisionVersion`
  - `Commitment`, `Person`, `Dependency`
  - `DriftEvent`, `DriftImpact`, `Alert`, `ProcessingJob`

## 6. Authentication & 7. Authorization
- NextAuth / Iron Session / JWT-based depending on implementation, scoped by `Workspace`.

## 8. Storage
- Secure cloud storage for meeting artifacts (audio/video).

## 9. Background Processing
- Async queues for transcription and AI extraction.

## 10. Decision Model
- Decisions are versioned. An update creates a new `DecisionVersion` linked to a `DriftEvent`.

## 11. Commitment Model
- Tracks actionable items tied to Decisions, with `Owner` and `Deadline`.

## 12. Dependency Model
- Represents blocking tasks or requirements between deliverables.

## 13. Drift Model
- Semantic comparison detects changes in meaning, deadlines, or scope. Types: DEADLINE_SHIFT, OWNER_CHANGE, SCOPE_CHANGE, DECISION_REVERSAL, PRIORITY_CHANGE, etc.

## 14. API Boundaries
- RESTful JSON APIs structured under `/api/*`.

## 15. Security Boundaries
- Strict server-side validation. API keys and secrets never exposed. Workspace isolation for all queries.

## 16. Error Handling
- Normalization of API errors. Graceful degradation in UI.

## 17. External Services
- Transcription API, LLM API, Storage Provider.

## 18. Environment Variables
- Listed in `.env.example`. Required for application startup.

## 19. Deployment Architecture
- Vercel or standard Node.js deployment container.

## 20. Important Architectural Decisions
- Use of deterministic demo mode when AI API keys are unavailable.
- Decisions are immutable history; changes create new versions.

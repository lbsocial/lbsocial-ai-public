# LBSocial AI Study Mode Overview

LBSocial AI Study Mode is a beta learning workspace for asking questions about LBSocial course content and turning those questions into grounded learning paths.

It is designed for learners who want a practical answer with course context: what to study, which video or timestamp supports the answer, and what to practice next.

## What Study Mode Does

Study Mode combines a chat tutor with a course knowledge graph. A learner can ask questions such as:

- Where does LBSocial teach OpenClaw with n8n webhooks?
- How should I learn Neo4j GraphRAG from zero?
- Python 有什么课程推荐？
- Which videos help with Cloud Run and Firebase?

The system decides whether the question should use course retrieval. For specific course, tool, video, or tutorial questions, it searches the LBSocial knowledge graph. For generic greetings or broad learning questions, it can answer without forcing unrelated video evidence.

## Current Content Graph

The current learning content analytics snapshot shows:

| Content type | Count |
| --- | ---: |
| Courses | 12 |
| Videos | 340 |
| Chapters | 1,004 |
| Transcript segments | 7,000 |

The content graph includes course-video relationships, chapter structure, timestamped transcript segments, topics, tools, skills, and view metadata. This lets Study Mode search at a more useful level than a simple document lookup: it can connect a user question to a course, a video, and a timestamped learning segment.

Common high-frequency topics in the current graph include Python, AWS, knowledge graphs, MongoDB, GitHub, OpenAI, credentials/security topics, multi-agent systems, OpenClaw, and Gemini.

## How It Works

At a high level:

1. The learner enters through the LBSocial AI app.
2. Study Mode receives a text question.
3. The backend checks safety, quota, and whether the question should use course retrieval.
4. Course-related questions are sent to the LBSocial knowledge graph retrieval service.
5. The retrieval service searches course/video/chapter/transcript metadata and returns ranked sources plus optional learning-path steps.
6. The AI tutor writes a concise answer using the retrieved context as the source of truth for course, video, and timestamp claims.
7. The app shows the answer, Study Path, source cards, and feedback/report controls.

The production implementation uses a private app backend and a private knowledge graph service. This public repository intentionally does not expose private source code, service URLs, deployment settings, credentials, user records, or internal logs.

## Direct, Related, and No-Source Answers

Study Mode is built to avoid overclaiming.

- **Direct match**: the graph finds content that directly supports the user's question. The app can show source cards and timestamps.
- **Related match**: the graph finds useful nearby material, but not a dedicated source for the exact request. The tutor should describe it as related material.
- **No source**: the graph does not find a specific LBSocial source. The tutor should avoid inventing a course, video, or timestamp.

This distinction is important during beta testing because it helps reviewers separate retrieval failures from true content gaps.

## Study Workspace

The Study Workspace turns a single answer into a learning surface:

- **Study Path**: ordered steps for what to learn next.
- **Sources**: direct video evidence when available.
- **Practice actions**: follow-up prompts such as longer path, project plan, tool focus, or skill drills.
- **Metadata chips**: tools, topics, and skills discovered from the retrieved sources.

Voice Tutor remains a lighter spoken-answer path, while Study Mode is the deeper structured learning path for text-based study.

## Feedback During Beta

Each AI answer includes lightweight feedback:

- Helpful
- Not helpful
- Report a problem

The public report link opens the GitHub issue template chooser for this repository. The app does not automatically attach chat history, account IDs, email addresses, tokens, logs, internal errors, or private course-access data to public issues.

Good feedback examples:

- The answer linked to an unrelated video.
- The tutor said there was no source, but I know this topic exists in a LBSocial course.
- The Chinese question was understood incorrectly.
- The Study Path was too generic.
- The mobile layout overlapped.

Please avoid posting private account details or sensitive screenshots in public issues.

## Public Repo Boundary

This repository is public so testers, reviewers, and collaborators can understand the product direction and report beta issues.

Private production repositories remain private. A future public/demo version may be added here only after it is sanitized and stripped of private source code, secrets, deployment settings, internal service names, real user data, and operational logs.

# LBSocial AI Public Beta

LBSocial AI is a beta learning assistant for LBSocial courses. It helps learners ask questions, find relevant course videos, open timestamped YouTube evidence, and turn a topic into a practical Study Mode learning path.

This public repository is for beta feedback, issue reports, public-facing project notes, and future sanitized demo materials.

## Study Mode at a Glance

Study Mode connects the LBSocial AI app to a course knowledge graph built from LBSocial learning content. The current content analytics snapshot includes:

- **12 courses**
- **340 videos**
- **1,004 chapters**
- **7,000 transcript segments**

The knowledge graph organizes course, video, chapter, transcript, topic, tool, and skill metadata so the AI tutor can ground answers in actual LBSocial learning material instead of relying only on generic model knowledge.

When a learner asks a course or tool question, Study Mode can:

- Retrieve relevant LBSocial course/video evidence.
- Show YouTube source cards with timestamps when direct evidence is available.
- Build a step-by-step Study Path from retrieved course material.
- Distinguish direct source matches from related or no-source answers.
- Support English, Chinese, and common speech-like variants such as OpenCloud/OpenClaw, Neo four j/Neo4j, and n eight n/n8n.
- Collect Helpful / Not helpful feedback and public issue reports during beta testing.

Read the detailed overview: [Study Mode Overview](docs/study-mode-overview.md)

## What This Repo Is For

- Report problems with LBSocial AI Study Mode or Voice Tutor.
- Share wrong or missing video/source matches.
- Suggest improvements to the learning experience.
- Track public-facing beta notes and known issues.
- Hold future sanitized public demo materials when they are ready.

## What This Repo Is Not

This repository does not contain the private production source code for LBSocial AI. The production application, Wix integration, knowledge graph pipeline, deployment configuration, user data, logs, credentials, and internal operations remain private.

Please do not post passwords, API keys, private account information, personal data, screenshots containing sensitive information, or private course-access details in public issues.

## Report a Problem

Open a new issue from the template chooser:

https://github.com/lbsocial/lbsocial-ai-public/issues/new/choose

Choose the template that best matches what happened:

- **Bug report** for app, login, voice, UI, or reliability issues.
- **AI answer or source problem** for wrong answers, bad video matches, missing sources, or weak study paths.
- **Feature request** for ideas and improvements.

## Future Public Version

A future public/demo version may be added here after it has been sanitized. It will not include private production code, secrets, real deployment settings, private service URLs, user records, or internal admin data.

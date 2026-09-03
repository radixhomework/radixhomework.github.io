---
title: "Transtooling"
order: 3
status: "Tools"
short_description: "A self-hosted tool for local audio transcription and FR↔EN translation."
image: "/assets/images/transtooling-logo.png"
image_alt: "Transtooling logo"
---

## About

Transtooling is a self-hosted workbench for transcription and translation,
built so that no data ever leaves your machine: everything is processed
locally, with no third-party service involved.

Audio transcription runs on
[faster-whisper](https://github.com/SYSTRAN/faster-whisper) and produces
timestamped `.vtt` subtitles. Translation between French and English works
on typed text or on ZIP archives of technical files (JSON, HTML…),
translated fully offline with CTranslate2 and OPUS-MT models — file names
and folder structure are preserved, and results come with a processing
report.

An administration interface manages users, roles and passwords, and lets
you download faster-whisper models on demand (tiny through large-v3),
choose the default model, and configure file size and duration limits.
Source audio is systematically deleted after processing: only the
transcription is kept.

## What is here?

- Local audio → text transcription (timestamped `.vtt`)
- Offline FR↔EN translation of text and technical file archives
- On-demand Whisper model management with download progress
- User management with admin interface and JWT authentication
- Job progress tracking and cancellation
- Docker-based self-hosted deployment

## Work in progress

Transtooling is under active development. Source code and documentation
live on GitHub:
[radixhomework/transtooling](https://github.com/radixhomework/transtooling).

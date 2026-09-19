# EpochView

**AI-powered historical map explorer** that turns a geographic location into an interactive historical timeline with generated narratives, visual content, audio narration, and a conversational local guide.

## Overview

EpochView combines maps, 3D visualization, and generative AI to let users explore how a place changed across historical eras.

A user selects a location, the application organizes historical information into eras, and the interface presents each era through an interactive timeline, generated narrative content, visualizations, and conversational exploration.

## Features

- Interactive map-based location exploration
- Historical timeline and era navigation
- Three-dimensional/isometric visual experiences
- AI-generated historical narratives
- Generated video and narrated audio concepts
- Context-aware conversational guide
- Responsive React interface

## Architecture

```text
Location / Map
     |
     v
Historical data + Generative AI service
     |
     +----> Narrative
     +----> Visual / 3D content
     +----> Audio / video
     |
     v
React + TypeScript application
     |
     +----> Timeline
     +----> Era details
     +----> Interactive globe/map
     +----> Chat assistant
```

## Tech stack

- React + TypeScript
- Vite
- Three.js
- @react-three/fiber and @react-three/drei
- Leaflet
- Generative AI SDK
- lucide-react

## Project structure

```text
App.tsx
components/
  CardRow.tsx
  DetailModal.tsx
  LoadingScreen.tsx
  Timeline.tsx
  ChatWidget.tsx
  GlobeBackground.tsx
services/
  geminiService.ts
assets/
index.tsx
types.ts
vite.config.ts
```

## Run locally

```bash
npm install
npm run dev
```

Configure the required generative-AI credentials according to the service layer before using AI-powered features.

## Why it is interesting

The project explores a multimodal interface rather than a conventional chatbot: geographic context becomes the entry point for structured historical exploration, while AI generates multiple forms of content around the same place and era.

# Character Prompt Builder

## Overview

This is a static single-page web application that helps users generate AI character prompts through a questionnaire-based interface. The application collects user responses to 30 guided questions about character attributes and automatically generates three types of prompts: GPT prompts, BananaAI/LLM prompts, and Midjourney/SDXL image generation prompts. All functionality is implemented in pure HTML/CSS/Vanilla JavaScript without any external dependencies or backend services.

**Current Status**: ✅ Fully Implemented and Tested (November 11, 2025)

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Single-Page Application (SPA) Pattern**
- The entire application is contained within a single `index.html` file
- No page navigation or tab switching - all interactions happen on one scrollable page
- Pure vanilla JavaScript for DOM manipulation and event handling
- Inline CSS for styling within the HTML document

**Component Structure**
- Header section with title and description
- Questionnaire section with 30 dropdown selectors
- Optional inputs for style hints, negative prompts, and image parameters
- Action buttons for generation, copying, saving, and loading
- Three separate output text areas for different prompt types
- Local storage management for saving/loading user selections

**State Management**
- Application state stored in JavaScript objects and localStorage
- No complex state management library needed due to simple data flow
- User selections tracked in memory and persisted to browser storage
- JSON export/import capability for sharing character profiles

### Data Model

**Character Profile Structure**
- 30 questions with multiple-choice answers (coded as A/B/C/D/E/F)
- Optional fields: style hints, negative prompts, image ratio/version parameters
- JSON format for export: `{ "character_profile": { "1": {"answer":"C"}, "2": {"answer":"E"}, ... } }`

**Prompt Generation Logic**
- Three distinct prompt templates for different AI platforms
- Conditional inclusion of questions (only selected answers are incorporated)
- Template string construction based on user selections
- Platform-specific formatting (GPT conversational style vs. Midjourney descriptive tags)

### User Interface Design

**Korean Language Interface**
- All labels, questions, and UI text in Korean
- Friendly, conversational question phrasing to guide users
- Dropdown options formatted as "A. 텍스트" for clarity

**Styling Approach**
- Modern gradient backgrounds (dark theme: #1a1a2e to #16213e)
- Glass-morphism effects with backdrop-filter blur
- Responsive design with max-width container (1200px)
- Consistent color scheme with purple gradient accents (#667eea to #764ba2)
- Shadow effects for depth and visual hierarchy

### Storage Strategy

**localStorage Implementation**
- Browser's localStorage API for client-side persistence
- No server-side database or authentication required
- Save/Load functionality for returning users
- JSON export/import for cross-device portability

**Data Persistence**
- Automatic or manual save triggers
- Load functionality to restore previous selections
- Export to downloadable JSON file
- Import from JSON file upload or paste

### Prompt Generation System

**Three Output Formats**
1. **GPT Prompts** - Conversational character description for ChatGPT/GPT-4
2. **BananaAI/General LLM Prompts** - Structured format for API-based LLMs
3. **Midjourney/SDXL Prompts** - Tag-based descriptive format with parameters (--ar, --v)

**Generation Algorithm**
- Parse user selections from dropdowns
- Map answer codes to descriptive text
- Construct platform-specific templates
- Include optional parameters (style, negative prompts, image settings)
- Handle partial responses (skip unanswered questions)

## External Dependencies

**None** - This is a completely self-contained application with:
- No external JavaScript libraries or frameworks
- No CSS frameworks or preprocessors
- No backend server or API calls
- No database connections
- No third-party authentication services

**Browser APIs Used**
- localStorage API for data persistence
- Clipboard API for copy functionality
- File API for JSON import/export
- DOM API for dynamic content manipulation

The application relies solely on modern browser capabilities and requires no installation, build process, or external services to function.
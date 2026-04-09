# Plato Play Draft Studio

A lightweight browser-based studio for drafting, formatting, and combining student-written script scenes for a classroom adaptation of Plato's Allegory of the Cave.

Live site:
<https://ohiomathteacher.github.io/plato-play-studio/>

## What This App Is For

This app supports a group play-writing workflow in which:

- each student group drafts in its own Google Doc
- the teacher or students can pull that draft into the studio
- the app reformats the text into a script-style preview
- all group drafts can be combined into a single working script for revision, table read, and PDF export

It is designed for classroom use with four writing teams:

- Triad A
- Triad B
- Triad C
- Pair D (narrator / cue writing)

## Core Workflow

1. Set each group's label, scene description, and Google Doc link in Group Setup.
2. Select a group in Group Drafts.
3. Use Pull Doc to bring the latest text from that group's Google Doc into the draft editor.
4. Review the formatted result in Formatted Script Preview.
5. Use Reformat if needed after manual edits.
6. Use View Combined to pull all linked Google Docs, combine them into one script, and display that combined script in both the draft editor and formatted preview.
7. Use PDF to open a print-friendly tab and save the formatted script as a PDF.

## Current Features

### Group Management

- Group Drafts sidebar for quickly switching between groups
- Saved Group Setup panel for:
  - group label
  - scene description
  - Google Doc URL
- Group setup is stored in the browser with localStorage

### Draft Editing

- Large draft editor for the currently selected group
- Copy button to copy whatever text is currently in the draft editor
- Pull Doc button to import the latest text from the active group's Google Doc
- View Combined button to:
  - pull from all linked Google Docs
  - combine all scenes and cue sections
  - place the combined script into the draft editor
  - show the formatted combined version in preview

### Script Preview

- Real-time formatted preview beside the draft editor
- Reformat button to normalize the current draft text for preview
- PDF button to open a temporary print tab for the current formatted script

### Combined Script Behavior

- Pair D cue markers are recognized and inserted into the combined script:
  - `[[OPENING]]`
  - `[[TRANSITION_2]]`
  - `[[TRANSITION_3]]`
  - `[[CLOSING]]`
- Combined mode allows the teacher to inspect and edit the full assembled script directly in the draft editor

### Project Utilities

- Export Project downloads a JSON backup of:
  - group setup
  - current drafts
  - combined script
- Import Project restores a previously exported JSON backup
- Load Starter Templates fills the draft boxes with sample Plato text for testing/demo purposes
- Clear Drafts clears current draft text and combined text while leaving setup metadata intact
- Zoom controls resize the workspace for classroom projection or teacher editing

## Supported Markup

The app supports simple script markup in the draft editor.

### Headings

- `[Setting]` -> H3 heading
- `[[Direction]]` -> H2 heading
- `[[[Scene 1]]]` -> H1 heading

### Stage Directions

- `(Lights dim.)` -> stage direction (flush left, italic) — parentheses are markup delimiters only, not displayed

### Dialogue

- `SOCRATES: Dialogue text...`
- `@Billy@ Hey, what is going on?`

### Inline Emphasis

- `*italics*`
- `**bold**`

### Pair D Cue Markers

- `[[OPENING]]`
- `[[TRANSITION_2]]`
- `[[TRANSITION_3]]`
- `[[CLOSING]]`

## Google Doc Behavior

- The app works best with standard Google Doc edit links
- The app can detect whether a pasted link looks like a Google Doc edit link
- The app cannot truly verify Google editing permissions from a static website
- If auto-load fails because of sharing or browser restrictions, the app may open the plain-text export in a new tab so the user can copy/paste manually

## PDF Behavior

- The PDF button opens a temporary browser tab with a print-friendly version of the current formatted script
- Users should choose Print -> Save as PDF in that tab
- After printing/saving, the temporary tab can be closed

## Hover Help

Version 1 includes hover explanations for:

- toolbar buttons
- draft controls
- preview controls
- Group Drafts
- Group Setup
- formatting hints and cue markers

## Important Notes

- This is a static front-end app. There is no server or database.
- Group setup and saved state live in the browser unless exported.
- The app is designed as a drafting and assembly tool, not a live collaborative editor.
- Google Docs remain the main collaborative writing space.

## Suggested Use In Class

- Students draft in their assigned Google Docs.
- Teacher uses Plato Play Draft Studio to pull drafts, preview formatting, and combine scenes.
- Whole class reviews the combined draft for transitions, stage directions, narrator cues, and scene coherence.
- Teacher exports a PDF for rehearsal, discussion, or revision.

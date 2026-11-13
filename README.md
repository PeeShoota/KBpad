# KBpad

A lightweight, minimalist, distraction-free plain-text editor built for Windows.

A strictly keyboard-driven Windows app created in Visual Studio LTSC 18.11.

## Features

- **Keyboard-Driven Workflow:** Every action, dialog, and overlay is 100% navigable using only the keyboard without needing a mouse.
- **Distraction-Free Interface:** Full-bleed text editing area with word wrap enabled, vertical scrolling, and zero toolbars, ribbon menus, or status bars.
- **Plain-Text Only (`.txt`):** Strictly plain-text editing. Rich-text formatting, fonts, colors, and hyperlinks copied from external sources are automatically stripped when pasting (`Ctrl+V`).
- **Smart Dirty-State Tracking:** Dynamically updates the titlebar (`filename.txt - KBpad 1.0.0` vs. `*filename.txt - KBpad 1.0.0`) and automatically clears the `*` indicator if edits are undone or manually deleted back to the last saved state.
- **Unsaved Changes Safeguard:** Prompts to save, discard, or cancel via keyboard-accessible confirmation before starting a new file, opening a file, or closing with unsaved changes.

## Keyboard Shortcuts

| Shortcut | Action | Behavior |
| :--- | :--- | :--- |
| **`Ctrl+N`** | New File | Prompts to save if dirty (`*`), then clears the editor and resets the title to `Untitled.txt - KBpad 1.0.0`. |
| **`Ctrl+O`** | Open File | Prompts to save if dirty (`*`), then opens the standard Windows File Open dialog (`.txt` and all files). |
| **`Ctrl+S`** | Save | Saves directly to the active file path and clears the dirty `*` prefix (triggers `Save As` if untitled). |
| **`Ctrl+Shift+S`** | Save As | Opens the Windows File Save dialog, updates the titlebar filename, and clears the dirty `*` prefix. |
| **`Ctrl+Z`** | Undo | Reverts the last text edit (clears `*` if reverted back to saved baseline). |
| **`Ctrl+Y`** | Redo | Re-applies the last undone edit. |
| **`Ctrl+X`** | Cut | Cuts selected plain text to the clipboard. |
| **`Ctrl+C`** | Copy | Copies selected plain text to the clipboard. |
| **`Ctrl+V`** | Paste (Plain Text) | Pastes clipboard content while stripping all rich-text/HTML formatting. |
| **`Ctrl+A`** | Select All | Selects all text in the active document. |
| **`Ctrl+F`** | Find | Opens the keyboard-focused inline Find bar (`Enter` jumps to next match). |
| **`Ctrl+H`** | Find & Replace | Opens the keyboard-focused inline Find & Replace bar. |
| **`Ctrl+G`** | Go to Line | Opens a minimal inline prompt to jump the caret to a specific line number. |
| **`Esc`** | Dismiss / Focus Editor | Closes any open Help Window, Find, Replace, or Go to Line bar and returns focus straight to the editor. |

## Installation

1. Download the latest release zip
2. Extract the zip anywhere and put the folder somewhere safe
3. Run `KBpad.exe`

## Prerequisites

- **Windows 10** or **Windows 11**
- **.NET 10** (`net10.0-windows`)

> **Note on Linux / Wine Support (Experimental):** While KBpad is a native Windows application, it can run on Linux via **Wine**. 
> - **Requirements:** The Windows .NET 10 Desktop Runtime must be installed inside your Wine prefix.
> - **Known Caveats:** Native file dialogs (`Ctrl+O` / `Ctrl+S`) will rely on Wine's built-in file picker interface rather than native Linux desktop file managers.
>
> **Note for Windows users:** This app has only been built and tested on my daily driver which runs **Windows 10 IoT Enterprise LTSC 21H2**. It should still work on most other modern Windows versions if you have the dependencies needed, but that hasn't been verified.

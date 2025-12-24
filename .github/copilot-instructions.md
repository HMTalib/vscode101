# Copilot Instructions for Task Manager Web App

## Project Overview
This is a vanilla JavaScript web application for task management. It uses no frameworks or build tools - just HTML, CSS, and JS with localStorage for persistence.

## Architecture
- **Single-page application** with client-side rendering
- **Separation of concerns**: HTML in `index.html`, styles in `styles.css`, logic in `app.js`
- **Data flow**: User input → DOM events → JavaScript functions → DOM updates + localStorage
- **No server-side components** - purely client-side with localStorage persistence

## Key Patterns
- **Event delegation**: Use single event listener on `taskList` for all task interactions (e.g., `taskList.addEventListener('click', (e) => { if (e.target.classList.contains('delete-btn')) ... })`)
- **Re-render on change**: `renderTasks()` function clears and rebuilds the entire task list DOM on any data change
- **CSS variables**: Define colors and common values in `:root` (e.g., `--primary-color: #4a90e2;`)
- **Semantic HTML**: Use proper elements like `<header>`, `<main>`, `<form>`, `<ul>` with ARIA attributes

## Development Workflow
- **No build process**: Edit files directly, refresh browser to test
- **Local server**: Run `python3 -m http.server 8000` from project root, open `http://localhost:8000`
- **Debugging**: Use browser dev tools; console.log for JS debugging
- **Testing**: Manual testing in browser; no automated tests exist

## Code Style Conventions
- **JavaScript**: ES6+ features (arrow functions, template literals, const/let)
- **CSS**: Mobile-first responsive design with media queries
- **HTML**: Semantic markup with accessibility in mind (labels, ARIA)
- **Naming**: CamelCase for JS variables/functions, kebab-case for CSS classes, semantic IDs

## Common Tasks
- **Adding features**: Modify `renderTasks()` to include new elements, add event handlers in the main event listener
- **Styling**: Add classes to `styles.css`, use CSS variables for consistency
- **Persistence**: Any data change calls `saveTasks()` to update localStorage
- **Accessibility**: Always include `aria-label` for interactive elements, test with screen readers

## File Structure
- `index.html`: Main HTML structure and script inclusion
- `styles.css`: All styling with CSS variables and responsive rules
- `app.js`: Core logic - task CRUD operations, event handling, localStorage
- `README.md`: Project documentation (may be outdated)

## Important Notes
- Tasks stored as array of objects: `{text: string, completed: boolean}`
- Always trim input: `taskInput.value.trim()`
- Prevent default on form submit: `e.preventDefault()`
- Use data attributes for element identification: `data-index="${index}"`
# Feature Research Discovery: Task Movement (Up/Down) Feasibility

## Research Question
Is task moving up/down already implemented? What is the feasibility of adding up/down buttons to move tasks in the list?

---

## Current State

### UI Layer
- No up/down/move/reorder buttons are present in the UI.
- Only task creation and deletion are implemented ([codebase/src/App.js](codebase/src/App.js)).
- No UI elements or handlers for moving tasks up or down exist ([codebase/src/App.js](codebase/src/App.js)).

### Logic Layer
- No backend or state logic for task ordering or reordering is present.
- State management in [codebase/src/App.js](codebase/src/App.js) only supports add, delete, and save operations.
- No functions or reducers for moving or reordering tasks are implemented ([codebase/src/App.js](codebase/src/App.js)).

### Data Model
- No explicit task data models, types, or ordering fields (e.g., `order`, `position`, `index`) exist in the codebase.
- Tasks are not assigned any order-related property ([codebase/src/App.js](codebase/src/App.js)).

---

## Feasibility Assessment
- **UI**: Adding up/down buttons is feasible; would require new button components and event handlers in [codebase/src/App.js](codebase/src/App.js).
- **Logic**: Would require new logic to update task order in state; currently absent in [codebase/src/App.js](codebase/src/App.js).
- **Data Model**: Would require introducing an ordering field (e.g., `index`) to each task object; currently not present.
- **Unknowns**: No evidence of existing support for task reordering in any other files. Unknown if any external dependencies or constraints exist outside [codebase/src/App.js](codebase/src/App.js).

---

## Evidence Summary
1. UI Layer: No up/down/move/reorder buttons exist. Only task creation and deletion are implemented ([codebase/src/App.js](codebase/src/App.js)).
2. Logic Layer: No backend logic for task ordering/reordering exists. State management in [codebase/src/App.js](codebase/src/App.js) only handles add/delete/save operations.
3. Data Model: No task data models, types, or ordering fields (order/position/index) exist in the codebase.



## Implementation Summary (2026-05-18)

### Key Changes in [codebase/src/App.js](codebase/src/App.js)

1. **Task Movement Functions:**
	- Added `moveTaskUp(index)` and `moveTaskDown(index)` functions.
	- Pattern: clone tasks array, swap elements, update state with `setTasks`, persist with `saveTasks` (mirrors `deleteTask`).

2. **UI Enhancements:**
	- Imported `ChevronUp` and `ChevronDown` icons from `tabler-icons-react`.
	- Added two `ActionIcon` buttons (up/down) per task card, placed before Trash icon.
	- Used `disabled` prop for boundary checks (first/last task cannot move further).
	- Grouped all three action icons in a `Group spacing={0}` for compact layout.

3. **Patterns Used:**
	- Followed existing state update and persistence patterns.
	- No changes to task data model; order is managed by array index.

4. **QA Results:**
	- All scenarios passed: up/down movement, boundary disabling, localStorage persistence, Trash icon compatibility.

---

## Source Links
- [codebase/src/App.js](codebase/src/App.js)

---

*All findings are based on current codebase state. Unknowns are marked explicitly. No future plans or opinions included.*

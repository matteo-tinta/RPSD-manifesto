# Implementation Plan: Task Movement (Up/Down)

## Task
- Name: Task Movement (Up/Down)
- Goal: Enable users to reorder tasks in the task list using up/down buttons
- Scope boundaries: Simple up/down movement without animations; preserve order in localStorage; disable buttons at list boundaries

## Status
`READY_FOR_EXECUTION`

## Open Points
None

## Dependencies and Blockers
None

## Constraints and Guardrails
- Backward compatibility: existing tasks in localStorage remain functional
- DRY: reuse existing patterns (deleteTask, saveTasks, ActionIcon usage)
- KISS: array splice-based reordering, no complex state management
- Components <50 lines: current App.js is monolithic; keep changes minimal
- Icons: use tabler-icons-react icons (ChevronUp/ChevronDown) consistent with existing Trash icon

---

## Task: add_move_task_logic
- Status: `READY`
- Description: Implement moveTaskUp and moveTaskDown functions in App.js. Use array index swapping to reorder tasks. Persist changes to localStorage via saveTasks.
- Files to change:
  - codebase/src/App.js (modify): Add moveTaskUp(index) and moveTaskDown(index) functions after deleteTask function
  - Pattern: Follow deleteTask pattern - clone tasks array, modify, update state, save to localStorage
- Tests to do:
  - Manual: Move first task down, verify order changes
  - Manual: Move last task up, verify order changes
  - Manual: Refresh page, verify order persists
  - Edge case: Verify first task cannot move up (index 0)
  - Edge case: Verify last task cannot move down (index tasks.length - 1)
- DOD:
  - Completion criteria:
    - moveTaskUp(index) swaps task at index with task at index-1 if index > 0
    - moveTaskDown(index) swaps task at index with task at index+1 if index < tasks.length-1
    - Both functions save updated task list to localStorage
    - State updates trigger re-render with new task order
  - QA checklist:
    - Presentation project: Task list application (codebase/src/App.js)
    - APIs to call: localStorage.setItem('tasks', JSON.stringify(tasks))
    - Scenarios:
      - Component: Task movement logic
      - Expected results: Tasks swap positions in array; changes persist after page reload
      - Extra notes: Test with 3+ tasks; verify boundary conditions (first/last task)

## Task: add_move_buttons_ui
- Status: `DEPENDS_ON task_add_move_task_logic`
- Description: Add ChevronUp and ChevronDown ActionIcon buttons to each task card. Import icons from tabler-icons-react. Disable ChevronUp for first task (index === 0) and ChevronDown for last task (index === tasks.length - 1).
- Files to change:
  - codebase/src/App.js (modify): 
    - Import ChevronUp, ChevronDown from tabler-icons-react
    - Add two ActionIcon components in task card Group (before Trash icon)
    - Wire onClick handlers to moveTaskUp(index) and moveTaskDown(index)
    - Apply disabled prop based on index position
  - Pattern: Follow existing Trash ActionIcon pattern (color, variant, onClick structure)
- Tests to do:
  - Manual: Click up arrow on second task, verify moves up
  - Manual: Click down arrow on second task, verify moves down
  - Manual: Verify first task up button is disabled/non-functional
  - Manual: Verify last task down button is disabled/non-functional
  - Manual: Verify Trash icon still functions correctly
- DOD:
  - Completion criteria:
    - ChevronUp and ChevronDown icons imported from tabler-icons-react
    - Two ActionIcon buttons added to each task card
    - Buttons positioned before Trash icon in Group
    - ChevronUp disabled when index === 0
    - ChevronDown disabled when index === tasks.length - 1
    - onClick handlers call moveTaskUp(index) and moveTaskDown(index)
  - QA checklist:
    - Presentation project: Task list application UI (codebase/src/App.js)
    - APIs to call: None (UI only)
    - Scenarios:
      - Component: Task card action buttons
      - Expected results: Up/down buttons visible; disabled states correct; clicking reorders tasks
      - Extra notes: Test with 1, 2, and 3+ tasks; verify visual consistency with Trash icon style

---

## Implementation Notes
- Total tasks: 2
- Estimated complexity: Low (simple array manipulation and UI addition)
- Risk areas: None (isolated changes to App.js)
- Rollback: Remove move functions and buttons; localStorage data remains compatible

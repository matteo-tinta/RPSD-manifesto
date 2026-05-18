# Plan Summary: Task Movement (Up/Down)

## Summary
Simple task reordering feature using up/down buttons. Two focused tasks: add movement logic and add UI buttons. No animations, localStorage persistence included. Ready for execution.

## Task Summaries
- [add_move_task_logic](task-movement-up-down-plan.md#task-add_move_task_logic): Implement moveTaskUp/moveTaskDown functions using array index swapping; persist to localStorage following existing deleteTask pattern.
- [add_move_buttons_ui](task-movement-up-down-plan.md#task-add_move_buttons_ui): Add ChevronUp/ChevronDown ActionIcon buttons to task cards; wire to move functions with boundary-aware disabled states.

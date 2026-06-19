# Enhanced Layout & Day Planner Module

This plan outlines the UI overhaul to support a 2-column layout, a month-view calendar with deadline highlights, an automated daily planner timeline, and celebratory animations upon task completion.

## User Review Required

> [!IMPORTANT]
> The Day Planner Timeline needs to assign tasks between static events like "Breakfast", "Lunch", and "Dinner". Since tasks currently only have a *Day* deadline and not specific *Times*, I will automatically distribute today's tasks evenly into the available morning/afternoon/evening time slots. The "Rescheduling" feature will allow you to quickly change the task's deadline date. 
> Does this automatic time distribution sound good, or do you want to manually assign specific hours to each task? 
> Please review and approve!

## Proposed Changes

### 1. Layout Adjustments
- **`src/App.jsx`**: 
  - Widen the main application container from `max-w-3xl` to `max-w-6xl` or `max-w-7xl` to comfortably fit two columns.
- **`src/views/HomeView.jsx`**:
  - Implement a CSS Grid layout:
    - **Left Column**: Mood Selector and Today's Focus (Task List).
    - **Right Column**: The new Month Calendar and the Day Planner timeline.
  - Remove the old `MiniCalendar`.

### 2. Month Calendar (`src/components/MonthCalendar.jsx`)
- Use `date-fns` to generate a 7x5 or 7x6 grid for the current month.
- **Highlights**:
  - Current day emphasized.
  - Dates matching any uncompleted task deadlines will have a small colored dot indicator (using the Task's `deadline` property).

### 3. Day Planner (`src/components/DayPlanner.jsx`)
- A vertical timeline mapping out a typical day.
- **Static Routine Slots**:
  - 🌄 Morning: Fresh up, Breakfast.
  - 🍛 Mid-day: Lunch.
  - 🌙 Evening: Rest, Dinner, Sleep.
- **Dynamic Task Slots**:
  - It will ingest `sortedActiveTasks` and interleave them between the static routine slots.
- **Rescheduling**:
  - Add a "Reschedule" button next to tasks in the planner. Clicking it will open a small inline date picker (or modal) to change the `deadline` of that task via an `updateTask` function.

### 4. Completion Animations & Popup
- **Dependency**: Install `canvas-confetti`.
- **Logic in `HomeView.jsx` / `App.jsx`**:
  - When `completeTask` is called, trigger `canvas-confetti` to fire from the left and right edges.
  - Display a centered, animated overlay modal that says "🎉 Successfully completed!" which auto-dismisses after 2 seconds.

### 5. State Updates (`src/hooks/useMindFlowState.js`)
- Need to add an `updateTask(taskId, updates)` method to allow editing deadlines for the rescheduling feature.

## Open Questions

> [!WARNING]
> Regarding the "rescheduling" requirement: This plan implements an inline date-picker to change the task's deadline day. If you meant something else (like drag-and-dropping to change the order in the day planner), please let me know, as that involves more complex Drag & Drop libraries.

## Verification Plan
1. **Visual**: Verify the screen real estate uses a clean two-column grid.
2. **Calendar**: Ensure adding a task with a deadline makes a dot appear on the correct date in the Month Calendar.
3. **Planner**: Verify that tasks show up in the timeline view. Test the "Reschedule" date picker.
4. **Animation**: Complete a task and ensure confetti fires from both sides with an animated success popup.

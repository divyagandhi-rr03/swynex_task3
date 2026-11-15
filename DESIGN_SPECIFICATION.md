# StudySync — UI/UX Design Specification

## 1. Product overview
**Product:** StudySync — Student Study Planner & Productivity Tracker  
**Purpose:** Help college students organize academic tasks, keep track of deadlines and understand their study consistency.  
**Primary audience:** College students, especially engineering students managing coursework, assignments, projects and personal study goals.

### Problem statement
Students often use multiple disconnected tools or memory to manage study tasks. This can make deadlines difficult to track and progress hard to understand.

### Design goal
Create a clear, calm and encouraging workspace where students can see what needs attention, take action quickly and reflect on their productivity.

## 2. Visual direction
- Modern, clean and professional dashboard.
- Purple and white palette with subtle lavender surfaces.
- Rounded cards, soft borders and restrained shadows.
- Clear type hierarchy and generous spacing.
- Desktop-first composition with responsive tablet and mobile behavior.
- Encouraging, student-friendly microcopy.

## 3. Design tokens

| Token | Value | Usage |
|---|---|---|
| Primary | `#7057DC` | Primary actions, active navigation, chart accents |
| Primary dark | `#5940C4` | Hover state |
| Primary soft | `#F0EDFF` | Selected navigation, icon backgrounds |
| Ink | `#24213A` | Main text and headings |
| Muted | `#85839A` | Secondary text |
| Background | `#F8F8FC` | Application canvas |
| Surface | `#FFFFFF` | Cards, sidebar, modal |
| Border | `#EEEFF4` | Card and input borders |
| Mint | `#E6F8F1` | Completed status accent |
| Peach | `#FFF1E8` | Priority/project accent |
| Blue | `#EAF2FF` | Focus and assignment accent |

### Typography
- Display/headings: Plus Jakarta Sans, 600–800.
- Body/UI: DM Sans, 400–700.
- Heading scale: 27 px page title, 14 px card title.
- Supporting text: 9–12 px in dense dashboard elements.
- Fallback: sans-serif.

### Spacing and shape
- Base spacing rhythm: 4 px.
- Common gaps: 8, 10, 12, 16, 18, 20, 27, 34 px.
- Card radius: 13 px.
- Input/button radius: 8–9 px.
- Sidebar width: 250 px desktop.
- Content max width: fluid; comfortable desktop side padding 42 px.

## 4. Screen specifications

### Screen 1 — Dashboard
**Purpose:** Give the student an at-a-glance view of workload and progress.

**Main content**
- Personalized greeting and primary “Add new task” action.
- Four KPI cards: total tasks, completed tasks, pending tasks and focus hours.
- Daily progress ring with completed/remaining counts.
- Weekly activity bar chart.
- Upcoming tasks list with category, priority and due date.

**Key interaction:** “Add new task” opens a modal. Task completion updates the KPI cards and daily progress ring.

### Screen 2 — My Tasks
**Purpose:** Provide a focused place to manage the task list.

**Main content**
- Page heading and add-task action.
- Search field.
- Category filter: Study, Assignment, Project, Personal.
- Status filter: All, Pending, Completed.
- Task rows with completion control, category, priority and deadline.
- Delete control for each task.

**Key interaction:** Search and filters update the visible list. Completion and deletion update the stored task data.

### Screen 3 — Progress Insights
**Purpose:** Help students reflect on consistency and workload distribution.

**Main content**
- Task completion percentage.
- Weekly focus-time summary.
- Study streak card.
- Weekly productivity bar chart.
- Category distribution donut chart.
- Daily focus-goal progress indicator.

**Key interaction:** Insights update the task completion percentage based on the current task list. Other chart values are illustrative sample data for the prototype.

## 5. Component inventory
- Brand mark and sidebar navigation.
- Active navigation state and task-count badge.
- KPI/stat card.
- Progress ring.
- Weekly activity bar chart.
- Task row, completion checkbox and category chip.
- Search input and select filters.
- Primary and secondary buttons.
- Add-task modal and toast feedback.
- Responsive mobile menu.

## 6. Interaction and user flow

```text
Open StudySync
     |
     v
 Dashboard  <------>  My Tasks
     |                   |
     | Add task          | Search / filter
     v                   | Complete / delete
 Add-task modal          |
     |                   |
     v                   v
 New task appears <--- Updated task list
     |
     v
 Progress Insights
```

### Prototype behavior
- Navigation connects all three screens.
- Add-task form validates required title and due date.
- New tasks appear in the dashboard and task list.
- Completion toggles the task state and updates summary counts.
- Delete removes a task.
- Search matches task titles.
- Category and status filters can be combined.
- `localStorage` retains task changes in the same browser.

## 7. Responsive behavior
- Desktop: fixed left sidebar and two-column dashboard panels.
- Tablet: narrower sidebar and two-column stat cards.
- Mobile: off-canvas navigation, single-column panels and full-width search.
- The layout is designed to remain usable at 390 px wide.

## 8. Accessibility considerations
- Semantic headings, buttons, labels and form controls.
- Accessible labels for icon-only actions.
- Visible text labels accompany color-coded categories.
- Inputs retain keyboard focus outlines.
- Responsive layout supports touch interaction.

## 9. Scope and assumptions
This is a high-fidelity front-end prototype, not a production service. Sample focus-hour, streak and category-chart values are illustrative. Task records are saved only in the current browser using local storage; there is no authentication, backend database or cross-device synchronization.

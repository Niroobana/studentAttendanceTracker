# React Practice Worksheet: Student Attendance Tracker

> **Objective:**
> Students are given a **static HTML attendance page**. Their task is to **convert it into a structured, routed, and interactive React application step by step**.
>
> **Principle:**
> *Structure first, logic later* (industry & beginner friendly)

---

## TASK 1: Convert HTML to React JSX

### Instructions

1. Create a new React app (Vite recommended)

   ```bash
   npm create vite@latest attendance-app -- --template react
   cd attendance-app
   npm install
   npm run dev
   ```

2. Open `src/App.jsx`

3. Copy **only the HTML inside `<body>`** from `html`

4. Paste it inside the `return()` of `App()`

### Required Changes

| HTML      | React JSX   |
| --------- | ----------- |
| `class`   | `className` |
| `<input>` | `<input />` |
| `for`     | `htmlFor`   |

### Expected Output

* Page loads without errors
* UI looks exactly like HTML version
* No functionality yet

---

## TASK 2: Split UI into Components 

### Instructions

Create the following folder structure:

```
src/
 ├─ components/
 │   ├─ Header.jsx
 │   ├─ AttendanceForm.jsx
 │   ├─ AttendanceTable.jsx
 │   └─ StudentRow.jsx
 └─ App.jsx
```

### 🔹 Component Responsibilities

#### Header.jsx

* App title
* "Add New Attendance" button

#### AttendanceForm.jsx

* Class dropdown
* Date input
* Search input
* Mark Attendance button

#### AttendanceTable.jsx

* Table layout (thead + tbody)

#### StudentRow.jsx

* Single student table row (static for now)

> Do NOT use props or state yet

### Expected Output

* App UI unchanged
* Code is clean and separated

---

## TASK 3: Add Basic Routing (React Router)

### Instructions

1. Install React Router

```bash
npm install react-router-dom
```

2. Create pages:

```
src/pages/
 ├─ Dashboard.jsx
 ├─ AttendancePage.jsx
 └─ NotFound.jsx
```

3. Setup routes in `App.jsx`

### Page Responsibilities

* **Dashboard**: Welcome message + button → Attendance
* **AttendancePage**: Contains attendance components
* **NotFound**: Page not found message

### Expected Output

* Navigation works without reload
* Attendance UI appears only on `/attendance`

---

## TASK 4: Create Static Student Data & Render with map()

### Goal

Render student list dynamically.

### Instructions

1. Create student array inside `AttendancePage.jsx`

```js
const students = [
  { id: 1, roll: '001', name: 'Alice Johnson', status: 'present', remarks: '' },
  { id: 2, roll: '002', name: 'Bob Smith', status: 'absent', remarks: 'Sick leave' },
];
```

2. Pass students to `AttendanceTable` as props
3. Use `map()` to render rows

### Hint

```jsx
{students.map(student => (
  <StudentRow key={student.id} student={student} />
))}
```

### Expected Output

* Table rows generated from array
* No hard-coded `<tr>`

---

## TASK 5: Convert Student Data to State & Add Interactivity

### Goal

Make the app **interactive using React state**.

### Instructions

1. Convert students array to state

```js
const [students, setStudents] = useState(initialStudents);
```

2. Toggle Present / Absent
3. Add search filtering
4. Show attendance stats

### Key Logic

* `useState`
* `onClick`
* `onChange`
* Conditional rendering

### Expected Output

* Status toggles on click
* Search works live
* Counts update automatically

---

## BONUS TASKS (Optional)

* Update remarks using input
* Export attendance as CSV
* Save data to `localStorage`
* Add Bootstrap modal for new attendance

---

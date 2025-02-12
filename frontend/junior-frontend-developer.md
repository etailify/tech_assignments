# Frontend Assignment - 12th February, 2025

### Role: Junior Frontend Developer

### Task

0. The task is to create a todo dashboard app.
1. Hook:
   1. Create a custom `useTodos` hook that has methods a) to lisit the todos, b) to create a todo (can you also add update todo?).
   2. Use `https://jsonplaceholder.typicode.com/` for the mock api or any other mock apis of your choice.
   3. You must use react-query and axios.
2. UI:
   1. Make sure to wrap your UI with a root layout that has a left navigation sidebar.
   2. The sidebar must have atleast two links - a) to list all the todo items, b) to create a todo items. Use nested routing. Also add the logic to update a todo.
   3. Add pagination for the lisiting view.
   4. It should look like a dashboard.
   5. You must use NextJS App Router - v14 with TypeScript and Tailwind. Use radix for Input, Button and other atomic level UI elements that you need.
   6. Make sure to seperate client and server components properly. Study about RSC before implementing this.
   7. Make sure to handle pending UIs and loading states.
   8. Make sure to properly structure the codebase.

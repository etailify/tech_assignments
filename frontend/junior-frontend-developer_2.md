# Frontend Assignment - February 24, 2025

### Role: Frontend Developer

### Task

1. **Create a dashboard** where users can create and view categories.

2. **User Interface Requirements:**

   - Create a root layout with a left navigation sidebar.
   - Build a login page and integrate the login API, implementing accessToken and refreshToken logic.
   - Implement client-side route guards.
   - Implement nested routing with at least two main category-related routes:
     - Category listing (with search and pagination).
     - Category creation form (with subcategory support).
     - Category update functionality.
   - Design the interface as a dashboard and make it as visually appealing as possible.

3. **Custom Hook Implementation:**

   - Develop a `use-categories` custom hook with functionality to:
     - Create a new category.
     - View and update existing categories.
     - List all categories.
   - Integrate with the APIs below.
   - Use React Query and Axios for API handling.

4. **Requirements:**
   - **Stack:** Next.js 14 (App Router), TypeScript, React Hook Form, Zod.
   - Style using Tailwind CSS.
   - Use Radix UI for basic components (inputs, buttons, etc.).
   - Implement loading states and handle pending UI states.
   - Maintain a clean, organized, and extensible code structure.

### APIs

Create category:

```
curl 'http://34.93.171.63:8081/store_svc/v1/stores/65b6bf12-2271-4bd9-b5b2-28a98b20c880/categories' \
  -H 'Accept: application/json, text/plain, */*' \
  -H 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \
  -H 'Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1cm4iOiJ1cm46ZVRhaWxpZnk6dG9rZW5zOmFmZGQwNmM2LWEyM2QtNDFmMC1hNWMzLTVkNDAwMDhmODMzZiIsInRva2VuX3R5cGUiOiJhY2Nlc3NfdG9rZW4iLCJtZXRhX2RhdGEiOnsidXVpZCI6ImFmZGQwNmM2LWEyM2QtNDFmMC1hNWMzLTVkNDAwMDhmODMzZiIsIm5hbWUiOiJLdW1hciBEIiwicGhvbmUiOiIrOTE3NDExMzA3NjkyIiwiZW1haWxfYWRkciI6Imt1bWFyZEBldGFpbGlmeS5vcmciLCJ1c2VyX3R5cGUiOjEsInN0b3JlX2lkIjoiNjViNmJmMTItMjI3MS00YmQ5LWI1YjItMjhhOThiMjBjODgwIn0sImV4cGlyeV90aW1lIjoiMjAyNS0wMi0yNFQwOTozNToyMi4yNjg0NDU5NTJaIiwiaXNzdWVkX2F0IjoiMjAyNS0wMi0yNFQwOTozMDoyMi4yNjg0NDY4NDFaIiwiaXNzdWVyIjoiIiwibm90X3ZhbGlkX2JlZm9yZSI6IjIwMjUtMDItMjRUMDk6MzA6MjIuMjY4NDQ2NzUxWiIsImF1ZGllbmNlIjpudWxsfQ.Vp6YoYY_dH4V6QHwLM0egQruMcFyqbXJ0-kAoNkmLNk' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'Origin: http://localhost:3000' \
  -H 'Referer: http://localhost:3000/' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36' \
  --data-raw '{"name":"Pants","description":"Best quality pants","document_id":"","media_url":"","sub_categories":[{"name":"Denim","description":"Denim pants","document_id":"","media_url":""},{"name":"Chinos","description":"Slim fit chinos","document_id":"","media_url":""}]}' \
  --insecure
```

Search category:

```
curl 'http://34.93.171.63:8081/store_svc/v1/stores/65b6bf12-2271-4bd9-b5b2-28a98b20c880/categories/search' \
  -X 'PUT' \
  -H 'Accept: application/json, text/plain, */*' \
  -H 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \
  -H 'Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1cm4iOiJ1cm46ZVRhaWxpZnk6dG9rZW5zOmFmZGQwNmM2LWEyM2QtNDFmMC1hNWMzLTVkNDAwMDhmODMzZiIsInRva2VuX3R5cGUiOiJhY2Nlc3NfdG9rZW4iLCJtZXRhX2RhdGEiOnsidXVpZCI6ImFmZGQwNmM2LWEyM2QtNDFmMC1hNWMzLTVkNDAwMDhmODMzZiIsIm5hbWUiOiJLdW1hciBEIiwicGhvbmUiOiIrOTE3NDExMzA3NjkyIiwiZW1haWxfYWRkciI6Imt1bWFyZEBldGFpbGlmeS5vcmciLCJ1c2VyX3R5cGUiOjEsInN0b3JlX2lkIjoiNjViNmJmMTItMjI3MS00YmQ5LWI1YjItMjhhOThiMjBjODgwIn0sImV4cGlyeV90aW1lIjoiMjAyNS0wMi0yNFQwOTo0MjowOS4xMTE2NTM0NDZaIiwiaXNzdWVkX2F0IjoiMjAyNS0wMi0yNFQwOTozNzowOS4xMTE2NTQwNDZaIiwiaXNzdWVyIjoiIiwibm90X3ZhbGlkX2JlZm9yZSI6IjIwMjUtMDItMjRUMDk6Mzc6MDkuMTExNjUzOTYyWiIsImF1ZGllbmNlIjpudWxsfQ.3gy45EU8ob0pyi7c8rgBaROzBstE1uh94CkoisDO_a8' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'Origin: http://localhost:3000' \
  -H 'Pragma: no-cache' \
  -H 'Referer: http://localhost:3000/' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36' \
  --data-raw '{"request":[],"pageRequest":{"page":0,"size":100}}' \
  --insecure
```

Get category by Id:

```
curl 'http://34.93.171.63:8081/store_svc/v1/stores/65b6bf12-2271-4bd9-b5b2-28a98b20c880/categories/22d572c5-6ca0-4d85-bbe4-d167ebc30709' \
  -H 'Accept: application/json, text/plain, */*' \
  -H 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \
  -H 'Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1cm4iOiJ1cm46ZVRhaWxpZnk6dG9rZW5zOmFmZGQwNmM2LWEyM2QtNDFmMC1hNWMzLTVkNDAwMDhmODMzZiIsInRva2VuX3R5cGUiOiJhY2Nlc3NfdG9rZW4iLCJtZXRhX2RhdGEiOnsidXVpZCI6ImFmZGQwNmM2LWEyM2QtNDFmMC1hNWMzLTVkNDAwMDhmODMzZiIsIm5hbWUiOiJLdW1hciBEIiwicGhvbmUiOiIrOTE3NDExMzA3NjkyIiwiZW1haWxfYWRkciI6Imt1bWFyZEBldGFpbGlmeS5vcmciLCJ1c2VyX3R5cGUiOjEsInN0b3JlX2lkIjoiNjViNmJmMTItMjI3MS00YmQ5LWI1YjItMjhhOThiMjBjODgwIn0sImV4cGlyeV90aW1lIjoiMjAyNS0wMi0yNFQwOTozNToyMi4yNjg0NDU5NTJaIiwiaXNzdWVkX2F0IjoiMjAyNS0wMi0yNFQwOTozMDoyMi4yNjg0NDY4NDFaIiwiaXNzdWVyIjoiIiwibm90X3ZhbGlkX2JlZm9yZSI6IjIwMjUtMDItMjRUMDk6MzA6MjIuMjY4NDQ2NzUxWiIsImF1ZGllbmNlIjpudWxsfQ.Vp6YoYY_dH4V6QHwLM0egQruMcFyqbXJ0-kAoNkmLNk' \
  -H 'Connection: keep-alive' \
  -H 'Origin: http://localhost:3000' \
  -H 'Referer: http://localhost:3000/' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36' \
  --insecure
```

Login:

```
curl 'http://34.93.171.63:8081/token_svc/v1/stores/login' \
  -H 'Accept: application/json, text/plain, */*' \
  -H 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'Origin: http://localhost:3000' \
  -H 'Referer: http://localhost:3000/' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36' \
  --data-raw '{"email":"kumard@etailify.org","password":"a1b309f-c660-44e0-89b3-7b2b06f510fa"}' \
  --insecure
```

Refresh API:

```
curl 'http://34.93.171.63:8081/token_svc/v1/store_users/tokens/refresh' \
  -H 'Accept: application/json, text/plain, */*' \
  -H 'Accept-Language: en-GB,en-US;q=0.9,en;q=0.8' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'Origin: http://localhost:3000' \
  -H 'Referer: http://localhost:3000/' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36' \
  --data-raw '{"request":{"refresh_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1cm4iOiJ1cm46ZVRhaWxpZnk6dG9rZW5zOmFmZGQwNmM2LWEyM2QtNDFmMC1hNWMzLTVkNDAwMDhmODMzZiIsInRva2VuX3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwibWV0YV9kYXRhIjp7InV1aWQiOiJhZmRkMDZjNi1hMjNkLTQxZjAtYTVjMy01ZDQwMDA4ZjgzM2YiLCJuYW1lIjoiS3VtYXIgRCIsInBob25lIjoiKzkxNzQxMTMwNzY5MiIsImVtYWlsX2FkZHIiOiJrdW1hcmRAZXRhaWxpZnkub3JnIiwidXNlcl90eXBlIjoxLCJzdG9yZV9pZCI6IjY1YjZiZjEyLTIyNzEtNGJkOS1iNWIyLTI4YTk4YjIwYzg4MCJ9LCJleHBpcnlfdGltZSI6IjIwMjUtMDMtMjZUMDk6Mzc6NDkuMjIwNzYwMjM2WiIsImlzc3VlZF9hdCI6IjIwMjUtMDItMjRUMDk6Mzc6NDkuMjIwODc1MDc3WiIsImlzc3VlciI6IiIsIm5vdF92YWxpZF9iZWZvcmUiOiIyMDI1LTAyLTI0VDA5OjM3OjQ5LjIyMDg3NDlaIiwiYXVkaWVuY2UiOm51bGx9.8W8Tsoi3r8FIMQRYGYEHpJJYDhtJ7wqAZ7WRuTOWKWA"}}' \
  --insecure
```

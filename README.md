# 📘 GI Product Frontend – Technical Assessment (Next.js + Tailwind + Ant Design)

This project is a reference implementation for the **GeekUp Product Frontend Technical Assessment**, built with **Next.js (App Router)**, **TailwindCSS**, and **Ant Design**.
It fulfills all required features: Albums & Users modules, pagination synchronized with URL, avatar integration, clickable email/phone links, and clean responsive UI.

---

## 🚀 Tech Stack

| Layer | Technology | Description |
|--------|-------------|-------------|
| Frontend Framework | **Next.js 15 (App Router)** | Server Components, built-in routing, image optimization |
| UI Styling | **TailwindCSS 3.4** | Utility-first CSS framework for flexible styling |
| UI Components | **Ant Design 5** | Elegant, enterprise-ready React UI components (Table, Button, Avatar) |
| Data Source | **JSONPlaceholder API** | Public REST API for Albums, Users, and Photos |
| Avatar Service | **ui-avatars.com** | Auto-generated user avatars |

---

## 🧩 Features Implemented

### 1. Albums Module
- **Albums List** (100 items)
  - Columns: ID, Title, User (name + avatar), Actions (View button)
  - Pagination synced with `?page=` in URL (state preserved on reload)
  - Clicking on a user navigates to that user's detail page.
- **Album Detail**
  - Shows user info (avatar, name, email)
  - Displays album title
  - Renders photo thumbnails (`thumbnailUrl`), clickable to open full-size `url`

### 2. Users Module
- **Users List** (10 users)
  - Columns: ID, Avatar, Name, Email, Phone, Website, Actions
  - Email (`mailto:`) and phone (`tel:`) are clickable
  - Website opens in a new tab
- **User Detail**
  - Shows avatar, name, email, phone, and website
  - Lists all user’s albums with links to album details

### 3. UI/UX Requirements
✅ Responsive layout for screens ≥ **1280px**  
✅ **Loading states** via App Router  
✅ **Pointer cursor** on clickable elements  
✅ **All images have `alt` attributes**  
✅ **Clean structure**, consistent variable names, no typos  
✅ **Modern dark theme** with slate-based colors

---

## 📂 Folder Structure

```
gi-pf-next/
├─ app/
│  ├─ albums/          # Albums list & detail pages
│  ├─ users/           # Users list & detail pages
│  ├─ layout.tsx       # Root layout (nav + theme)
│  ├─ globals.css      # Tailwind + Ant Design reset
│  └─ page.tsx         # Redirect to /albums
│
├─ components/         # Reusable UI components
│  ├─ AlbumsTable.tsx
│  ├─ UsersTable.tsx
│  ├─ Pagination.tsx
│  └─ UserBadge.tsx
│
├─ lib/                # Data & helpers
│  ├─ api.ts           # Fetch JSONPlaceholder API
│  ├─ types.ts         # TypeScript models
│  └─ helpers.ts       # Formatters (if needed)
│
├─ public/             # Static assets
├─ tailwind.config.js  # Tailwind setup
├─ next.config.mjs     # Image domain whitelist
├─ package.json
└─ README.md           # You are here 🚀
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/your-username/gi-pf-next.git
cd gi-pf-next
```

### 2️⃣ Install dependencies
```bash
npm install   # or pnpm install / yarn install
```

### 3️⃣ Run development server
```bash
npm run dev
```
➡️ App will run on: **http://localhost:3000**

### 4️⃣ Build for production
```bash
npm run build && npm start
```

---

## 🌐 API References
| Resource | Endpoint | Description |
|-----------|-----------|-------------|
| Users | `https://jsonplaceholder.typicode.com/users` | 10 mock users |
| Albums | `https://jsonplaceholder.typicode.com/albums` | 100 albums |
| Photos | `https://jsonplaceholder.typicode.com/photos` | 5000 photos |
| Avatars | `https://ui-avatars.com/api/` | Dynamic avatar generation |

---

## 🎨 Design & UI Notes
- Layout designed for **1280px container** width.
- Uses **dark mode palette** (`slate-900` → `slate-700` → `sky-400` highlights).
- Combines **Ant Design components** with Tailwind for spacing and background.
- Custom pagination synced with URL via `useSearchParams()`.

---

## 🧠 Architecture Overview

```
User (clicks) → Router (/users/:id) → fetchUser + fetchUserAlbums → Render details
Album (clicks) → Router (/albums/:id) → fetchAlbum + fetchAlbumPhotos → Render photos
Pagination → Client component → Update ?page= → Server fetch re-renders
```

- **Server Components** handle data fetching.
- **Client Components** handle pagination and interactivity.
- **Optimized images** via Next.js `Image` with whitelisted domains.

---

## 🧾 Submission Guidelines (for assessment)
✅ Include `source code`, `screenshots`, and a short `approach.txt` describing:  
> Which libraries/tools you used and why.  
✅ Zip everything except `node_modules/`, `.git/`, and build files.  
✅ Submit via the form: [https://forms.gle/mQucFQ3XMJLgtJTZ8](https://forms.gle/mQucFQ3XMJLgtJTZ8)

---

## 👨‍💻 Author
**Hà Minh Đức**  
Software Engineering Student – University of Information Technology (UIT), VNU-HCM  
📧 minhduc.uit.se@gmail.com  
🔗 [GitHub](https://github.com/minhduc-uit) • [LinkedIn](https://linkedin.com/in/minhduc-uit)

---

> "Code clean, structure clear, UI consistent — that’s how you impress a frontend reviewer." 🧑‍💻✨

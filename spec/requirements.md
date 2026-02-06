# Ticket 1: Move to Building to start your project

# Agent Instructions

• Create the initial project setup based on the project description and specifications provided below.  
• Install the necessary libraries and dependencies and make sure that the app runs smoothly with a base minimum setup.  
• Make sure the target architecture is in place but avoid adding boilerplace that it not needed for a base minimum setup.  
• Make sure the essential product components are represented in line with the specified design preferences.  
• If the bare minimum setup requires data, use dummy data from a single file that can be easily modified and removed later.  
• Do not use any external services and make sure no user actions are required, except for approving coding agent actions.  

---

## Project Description

The app is a digital tool designed to help users manage various aspects of their daily lives. It targets individuals looking for a solution to organize tasks, access information, and enhance productivity. Users can utilize the app to streamline their routines and perform specific actions tailored to their needs. By centralizing essential functions, the app helps users save time and stay organized, leading to improved efficiency in their daily activities.

- Task management capabilities
- Information access
- Customizable features
- Daily activity enhancement
- Time-saving solutions
- Centralized organization

---

## Implementation Instructions

**Core Stack**

• Frontend framework: React 18+ with Vite  
• Language: TypeScript  
• State management: Redux Toolkit  
• Styling: Tailwind CSS  
• Backend: Supabase  
    • Database: Supabase Postgres  
    • Authentication: Supabase Auth  
    • Storage: Supabase Storage  
    • Edge Functions: Supabase Edge Functions  

**Project and Folder Structure**

Follow this structure exactly. Do not invent new top•level folders.  

src/  
• assets/       static images, icons, fonts (no code)  
• components/   small, stateless, reusable UI pieces  
    • Button/  
    • Card/  
    • Modal/  
    • ... (one folder per component)  
• modules/      larger, stateful sections of the app (pages + logic)  
    • Dashboard/  
    • Projects/  
    • Settings/  
    • Auth/  
• services/     external service wrappers and configuration  
    • supabase.js  
    • stripe.js  
• store/        Redux store and slices  
    • index.ts    configureStore  
    • slices/  
        • authSlice.ts  
        • globalSlice.ts  
        • ... (one slice per feature)  
• utils/        pure functions, helpers, formatters  
    • date.ts  
    • validators.ts  
    • constants.ts  
• App.tsx  
• main.tsx  

Rules:  
• No files directly in src/ except App.tsx and main.tsx  
• Components are dumb UI with no Redux or side effects  
• Modules are smart pages or features that can use Redux, hooks, services  
• Services contain only configuration and API wrappers with no business logic  

**Naming and Coding Conventions**

• Files and folders: kebab-case for folders (project-list)  
• Components: PascalCase (ProjectCard.tsx)  
• CSS classes: Tailwind utility classes only  
• Variables: camelCase (projectTitle)  
• Constants: UPPER_SNAKE_CASE (MAX_PROJECTS_FREE)  
• Functions: camelCase (fetchProjects, createTicket)  
• Types and Interfaces: PascalCase (Project, TicketPayload)  
• No default exports – always named exports  
• Prefer named imports over default imports  

**State Management Rules**

• Global state: Redux Toolkit slices only  
• Local component state: useState or useReducer  
• Never use Context API for global state  
• Slices must be feature•based (auth, projects, ui, etc.)  

**Supabase Rules and Patterns**

• Use Supabase client v2 (modular)  
• Initialize once in services/supabase.ts  
• Use named exports for auth, database, storage, functions  
• Never expose service role keys in frontend  
• Use Row Level Security – users can only read and write their own data  
• Use Edge Functions for:  
    • Stripe webhooks  
    • Monthly usage resets  
    • Sensitive operations  

**Security and Environment**

• No API keys in frontend code  
• Use Vite environment variables (VITE_...) for public values  
• Use Edge Functions to proxy private keys and sensitive calls  
• Supabase Auth required for all authenticated routes  
• Row Level Security: lock down tables (users can only access own rows)  

**Build and Deployment**

• Development: npm run dev – Vite dev server  
• Production build: npm run build – outputs to dist/  
• Hosting: Vercel, Netlify, or Supabase Hosting  
• Ignore files: Add to .gitignore  
    • notes.md  
    • *.md  
    • .env  
    • .env.local  

**Project Goals and Non-Negotiables**

• Scalable to hundreds of users  
• Secure with no key leakage and proper authentication  
• Maintainable with strict folder structure and separation of concerns  
• Fast user experience with optimistic updates where possible  
• Use TypeScript everywhere with strict mode  
• Write clean, readable code

---

## Design Instructions

**Visual Style Preference**

• Keep interfaces extremely simple and uncluttered  
• Use generous whitespace to let content breathe  
• Limit visual elements to only what is necessary  
• Prefer subtle shadows, thin borders, and soft corners over heavy effects  
• Use a restrained color palette (mostly neutrals with one or two accent colors)  
• Favor single-weight typography with clear hierarchy  
• Avoid gradients, patterns, icons overload, or decorative flourishes  
• Make every element feel intentional and purposeful  
• Prioritize readability and calm over excitement
# ToDo

To create a full-stack PERM (PostgreSQL, Express, React/Next.js, Node.js) application that present countries list. 

We'll need to:

1. Set up the Supabase database for storing country data
2. Create the necessary database schema
3. Build the Next.js frontend with a similar layout
4. Add data fetching and display functionality

Let's start by setting up our database and creating the frontend components.

- [ ] Create initial files

- [ ] install dependencies

  - [ ] 

- [ ] Update app/page.tsx

  

  - ```
    npx prisma generate
    ```

- [ ] Create `app/api/countries/route.ts`

- [ ] Update `package.json`

  - [ ] 

- [ ] Create `supabase/migrations/20250329002037_copper_dune.sql`

- [ ] Start Application

I've created a full-stack application that clones the Worldometers countries list. Here's what I've set up:

1. A [Supabase](https://supabase.com/docs) database with a `countries` table that includes:
   - Country name
   - Capital city
   - Population
   - Area
   - Population density (automatically calculated)
   - Land borders
2. A Next.js frontend with:
   - Responsive table layout
   - Search functionality
   - Sorting capabilities
   - Loading states
   - Beautiful UI using shadcn/ui components
3. API route to fetch data from Supabase

To complete the setup:

1. Click the "Connect to Supabase" button in the top right to set up your Supabase project
2. The migration will automatically create the database schema and insert sample data
3. The application will be ready to use

The application features:

- Real-time search filtering
- Formatted numbers with proper thousand separators
- Responsive design that works on all screen sizes
- Clean and professional UI
- Type-safe database interactions

I've updated the application to use Prisma instead of Supabase. Here are the key changes:

1. Added Prisma dependencies and removed Supabase
2. Created a Prisma schema that matches our data structure
3. Set up a Prisma client singleton for database connections
4. Updated the API route to use Prisma instead of Supabase
5. Modified the frontend types to match Prisma's generated types

To complete the setup:

1. Create a `.env` file with your PostgreSQL connection string:

```bash
DATABASE_URL="postgresql://user:password@localhost:5432/worldometers"
```

1. Run the following commands to set up the database:

```
npx prisma db push
```

1. You'll need to migrate your existing data from Supabase to your PostgreSQL database.

The application functionality remains the same, but now it's using Prisma for database operations, which provides:

- Type-safe database queries
- Better development experience with auto-completion
- Simplified database schema management
- More flexible deployment options



## Auth and Session Management

 Add MongoDB for user session management and authentication while keeping the PostgreSQL database for country data. We'll use NextAuth.js for authentication with MongoDB as the session store.

- [ ] Add MongoDB Authentication 

  - [ ] Create `lib/mongodb.ts`
  - [ ] Create `app/api/auth/[...nextauth]/route.ts`
  - [ ] Create  `app/api/auth/register/route.ts`
  - [ ] Create `app/auth/signin/page.tsx`
  - [ ] Create `app/auth/register/page.tsx`
  - [ ] Create  `app/layout.tsx`
  - [ ] Create `components/AuthProvider.tsx`
  - [ ] Create `components/Navbar.tsx`
  - [ ] Create `app/page.tsx`

- [ ] Startup

  - [ ] I've added MongoDB-based authentication with NextAuth.js while keeping PostgreSQL for country data. You'll need to add these environment variables to your `.env` file: 

    

    ```bash
    MONGODB_URI=your_mongodb_connection_string
    NEXTAUTH_SECRET=your_nextauth_secret
    NEXTAUTH_URL=http://localhost:3000
    ```


### Key features added:

1. User authentication with email/password
2. MongoDB adapter for NextAuth.js
3. Session management with MongoDB
4. Registration and login pages
5. Navigation bar with auth state
6. Protected routes (can be added as needed)

### The application now has:

- A clean authentication system
- Separate databases for different concerns (PostgreSQL for country data, MongoDB for auth)
- Modern UI with shadcn/ui components
- Type-safe database operations

## Documentation and Pages

I'll add markdown-based documentation pages and new routes for Home, About, and Contact pages using MDX for content management.

- [ ] Update `package.json`
- [ ] Install dependencies 
- [ ] Update `next.config.js`
- [ ] Create `components/Navbar.tsx`
- [ ] Create `app/about/page.mdx`
- [ ] Create  `app/contact/page.tsx`
- [ ] Create `app/page.tsx`
- [ ] Create 
- [ ] Create 
- [ ] Update 

I've added:

1. MDX support for markdown pages
2. A new navigation menu with Home, About, and Contact links
3. An About page using MDX for documentation
4. A Contact page with a form and contact information
5. Updated the navigation bar with the new menu items

The changes include:

- MDX configuration in Next.js
- New dependencies for MDX support
- A beautiful contact form with validation
- Comprehensive About page documentation
- Improved navigation using shadcn/ui's NavigationMenu component

The About page is written in MDX, allowing for easy documentation updates, while the Contact page is a fully-featured form with a clean design. The navigation has been enhanced to include all the new pages while maintaining the authentication components.
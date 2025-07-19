# Supabase Setup Instructions

## 1. Create a Supabase Project

1. Go to [supabase.com](https://supabase.com) and create an account
2. Create a new project
3. Wait for the project to be set up (this may take a few minutes)

## 2. Get Your Project Credentials

1. Go to your project dashboard
2. Click on "Settings" in the sidebar
3. Click on "API" in the settings menu
4. Copy your project URL and anon public key

## 3. Set Up Environment Variables

1. Copy `.env.local.example` to `.env.local`
2. Replace the placeholder values with your actual Supabase credentials:

```bash
NEXT_PUBLIC_SUPABASE_URL=your_actual_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_actual_anon_key
```

## 4. Set Up the Database Schema

1. Go to your Supabase project dashboard
2. Click on "SQL Editor" in the sidebar
3. Copy and paste the contents of `schema.sql` into the editor
4. Click "Run" to execute the SQL commands

This will create:
- The `todos` table with proper structure
- Row Level Security (RLS) policies to ensure users can only access their own todos
- Indexes for better performance
- A trigger to automatically update the `updated_at` timestamp

## 5. Verify Setup

After running the schema, you should see:
- A `todos` table in the "Table Editor"
- RLS policies enabled on the table
- The table should be empty initially

## Files Overview

- `client.ts` - Supabase client configuration
- `database.types.ts` - TypeScript type definitions for the database
- `schema.sql` - Database schema and RLS policies
- `../utils/auth-helpers.ts` - Authentication utility functions

## Next Steps

Once this setup is complete, you can:
1. Test the authentication flow
2. Create, read, update, and delete todos
3. Verify that RLS policies work correctly (users can only see their own todos)

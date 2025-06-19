# Supabase Setup Guide

This guide will walk you through setting up a new Supabase project and connecting it to your FastAPI backend.

## 1. Create a Supabase Account

If you don't already have one, create a new account on [Supabase](https://supabase.com/).

## 2. Create a New Project

1.  Once you are logged in, you will be redirected to your dashboard. Click on the "New Project" button.

2.  Choose your organization and give your project a name. Generate a strong password for your database and save it somewhere safe. Choose the region that is closest to you and your users.

    ![Project Configuration](/screens/db-setup.png)

3.  Click "Create New Project". Supabase will take a few minutes to set up your project.

## 3. Get Your API Credentials

Once your project is ready, you need to get your API URL and anon key.

1.  In the left sidebar, click on the "Project Settings" icon (the gear).
2.  In the settings menu, click on "API Keys".
3.  You will find your database "URL" under the "Data API" section:

    ![Database URL](/screens/db-url.png)

4.  You will find your `anon` "public" key under "Project API keys":

    ![API Credentials](/screens/api-keys.png)

5.  Copy these two values and paste them into your `.env` file:

    ```
    SUPABASE_URL="YOUR_SUPABASE_URL"
    SUPABASE_KEY="YOUR_SUPABASE_KEY"
    ```

## 4. Create a Table

Now, let's create a table in your Supabase database to store some data.

1.  In the left sidebar, click on the "Table Editor" icon (a table).
2.  Click on "Create a new table".
3.  Let's create a simple `notes` table with the following columns:
    -   `id`: `int8` (this is the primary key, Supabase will configure it automatically)
    -   `created_at`: `timestamptz` (with the default value `now()`)
    -   `title`: `text`
    -   `content`: `text`

    For this beginner tutorial, we'll disable "Row Level Security (RLS)" to keep things simple. In a production application, you would want to enable RLS for security.

    ![Create Table](/screens/table-setup.png)

4.  Click "Save" to create the table.

## 5. Disable Row Level Security (RLS)

Since this is a beginner tutorial, we'll disable RLS to make the table accessible without complex security policies.

1.  After creating your table, you'll see it in the Table Editor.
2.  Click on your `notes` table to select it.
3.  In the table settings, make sure "Enable Row Level Security" is turned OFF.
4.  This allows your FastAPI application to read and write data without additional authentication policies.

**Note:** In a real-world application, you should always enable RLS and create appropriate security policies to protect your data.

Now your `notes` table is ready to be used by your FastAPI application! You can add some sample data to the table using the Table Editor to test with.
# Recipe_Finder
A website that allows users to find and create recipes. with a well structured user interface

# Django Templates Overview
---

## Table of Contents

1. [Register Page (`register.html`)](#1-register-page-registerhtml)  
2. [Login Page (`login.html`)](#2-login-page-loginhtml)  
3. [Home Page (`home.html`)](#3-home-page-homehtml)  
4. [Recipe List Page (`recipe_list.html`)](#4-recipe-list-page-recipe_listhtml)  
5. [Recipe Form Page (`recipe_form.html`)](#5-recipe-form-page-recipe_formhtml)  
6. [Profile Page (`profile.html`)](#6-profile-page-profilehtml)  
7. [Edit Profile Page (`edit_profile.html`)](#7-edit-profile-page-edit_profilehtml)  
8. [Collection List Page (`collection_list.html`)](#8-collection-list-page-collection_listhtml)  
9. [Collection Form Page (`collection_form.html`)](#9-collection-form-page-collection_formhtml)  
10. [Collection Detail Page (`collection_detail.html`)](#10-collection-detail-page-collection_detailhtml)  
11. [Category Detail Page (`category_detail.html`)](#11-category-detail-page-category_detailhtml)  
12. [Base Layout (`base.html`)](#12-base-layout-basehtml)  

---

## 1. Register Page (`register.html`)

**Status**: Not Done  
**Path**: `register.html`  
**Purpose**: Displays the user registration form for new accounts.  
**Key Features**:  
- Extends the base layout from `recipe_finder/base.html`.  
- Uses Django’s form system to display fields (username, password, email, etc.).  
- Includes validation errors alongside each field.  
- Links to the login page if the user already has an account.  
- Highlights benefits of joining (e.g., saving recipes, creating collections).  

---

## 2. Login Page (`login.html`)

**Status**: Not Done  
**Path**: `login.html`  
**Purpose**: Allows existing users to log in to their accounts.  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Displays a login form with a username and password field.  
- Handles form error messages.  
- Offers a “Remember me” checkbox.  
- Prominent link to the registration page for new users.

---

## 3. Home Page (`home.html`)

**Status**: Not Done  
**Path**: `home.html`  
**Purpose**: Serves as the landing page (root URL).  
**Key Features**:  
- Extends `recipe_finder/base.html`.  
- Highlights core site features (searching for recipes, saving favorites, etc.).  
- Offers call-to-action buttons:
  - “Find Recipe” if the user wants to browse.
  - “Join Now” if unauthenticated or “Create Recipe” if logged in.
- May display **Popular Recipes** and **Newest Recipes** if the context provides them (`popular_recipes`, `newest_recipes`).

---

## 4. Recipe List Page (`recipe_list.html`)

**Status**: Not Done  
**Path**: `recipe_list.html`  
**Purpose**: Shows a list of recipes with search and filter functionality.  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Displays a search bar and filters (category, difficulty, max cooking time).  
- Shows a grid of recipe cards, each featuring:
  - A recipe image, title, cook time, likes, comments.
  - Difficulty badge and “Chef” badge for verified chefs.
- Supports pagination.  
- Provides a “Create Recipe” button for authenticated users.  

---

## 5. Recipe Form Page (`recipe_form.html`)

**Status**: Not Done  
**Path**: `recipe_form.html`  
**Purpose**: Allows users to create or edit a recipe with a multi-step form.  
**Key Features**:
- **Step 1**: Basic info (title, description, time, servings, categories, difficulty).  
- **Step 2**: Ingredients and instructions (dynamic add/remove fields).  
- **Step 3**: Images & Media (upload, set primary image, show preview).  
- Uses JavaScript for multi-step transitions and dynamic ingredient/instruction management.  
- On edit, existing images are displayed.  

---

## 6. Profile Page (`profile.html`)

**Status**: Not Done  
**Path**: `profile.html`  
**Purpose**: Shows a user’s public profile (their recipes, collections, and stats).  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Displays the user’s avatar, username, bio, location, etc.  
- If viewing your own profile, an “Edit Profile” button appears; otherwise a “Follow/Unfollow” button.  
- Tabs for user’s **Recipes** and **Collections**.  
- Shows placeholder if there are no recipes or collections yet.

---

## 7. Edit Profile Page (`edit_profile.html`)

**Status**: Not Done  
**Path**: `edit_profile.html`  
**Purpose**: Allows the logged-in user to update their profile info.  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Fields for profile picture, bio, location, website.  
- Toggle for professional chef status (`is_chef`).  
- A “profile completeness” progress bar.  
- “Save Changes” button and “Cancel” link.

---

## 8. Collection List Page (`collection_list.html`)

**Status**: Not Done  
**Path**: `collection_list.html`  
**Purpose**: Lists all collections owned by the currently logged-in user.  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Displays each collection with:
  - A cover image (from the first recipe in the collection, if any).
  - Recipe count, creation date, description.
  - Links to “View” or “Edit” the collection.  
- “Create Collection” button to add new collections.  
- Shows a placeholder if no collections exist.

---

## 9. Collection Form Page (`collection_form.html`)

**Status**: Not Done  
**Path**: `collection_form.html`  
**Purpose**: Enables creating or editing a recipe collection.  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Fields for the collection name, description, and privacy setting (`is_public`).  
- On edit, pre-populates fields with existing data.  
- Validates input, displays errors if needed.  
- “Save” button to store changes or create new.

---

## 10. Collection Detail Page (`collection_detail.html`)

**Status**: Not Done  
**Path**: `collection_detail.html`  
**Purpose**: Displays details of a specific collection and its recipes.  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Shows the collection’s name, description, creation date, recipe count.  
- If private, indicates that only the owner can see it.  
- Lists recipes with title, image, difficulty, likes, etc.  
- Owners can remove recipes from their collection.  
- Shows a placeholder if no recipes are in the collection.

---

## 11. Category Detail Page (`category_detail.html`)

**Status**: Not Done  
**Path**: `category_detail.html`  
**Purpose**: Displays recipes for a specific category.  
**Key Features**:
- Extends `recipe_finder/base.html`.  
- Shows the category’s name (and description if provided).  
- Lists recipes belonging to that category, each with:
  - Image, difficulty badge, chef badge, cooking time, likes, comments.
- Supports pagination for large sets of recipes.  
- If no recipes are found, shows a message and prompts the user to create or log in.  
- Includes a link to return to the recipe list page.

---

## 12. Base Layout (`base.html`)

**Status**: Not Done  
**Path**: `base.html`  
**Purpose**: Provides the overarching site layout, including header, nav, footer, and global scripts/styles.  
**Key Features**:
- Loads static resources (CSS, JS, fonts).  
- Displays the main navigation menu (Home, Recipes, Profile, etc.).  
- Handles user authentication links: login/register vs. logout/profile.  
- Renders global messages (Django’s message framework).  
- Defines the container for page-specific content via `{% block content %}`.  
- Footer includes quick links, categories, social icons, contact info.  


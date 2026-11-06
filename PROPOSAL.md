# Don't Stay Hungry! — A Community Recipe-Sharing Web Application

## Problem

People who enjoy cooking and baking often struggle to discover, organize, and revisit recipes because information is scattered across different websites and social media platforms. People who want to share their own recipes may lack a dedicated platform where they can present their recipes clearly and receive feedback from others.

## Users and Roles

- **Visitor (Guest):** Can browse, search, filter, and view publicly available recipes. Registration is required to access interactive features.
- **Member (Registered User):** Can create and manage their own recipes, save recipes, rate and review recipes, and manage their profile.
- **Administrator:** Can manage user accounts and moderate recipes, reviews, and other inappropriate content.

## User Stories

1. As a visitor, I want to browse and search recipes, so that I can discover dishes that match my interests.

   **Acceptance criteria:**
   - Visitors can view publicly published recipes.
   - Visitors can search recipes by title.
   - Visitors can filter recipes by category or difficulty.

2. As a member, I want to register and log in, so that I can access personalized features and manage my account.

   **Acceptance criteria:**
   - A visitor can register using valid account information.
   - Passwords are hashed before being stored.
   - Only authenticated members can access member-only features.

3. As a member, I want to create, edit, and delete my own recipes, so that I can share and maintain my cooking instructions.

   **Acceptance criteria:**
   - A member can create a recipe with a title, description, ingredients, and cooking steps.
   - A member can edit their own recipes.
   - A member cannot edit or delete another member's recipes.

4. As a member, I want to save recipes, so that I can revisit my favorite dishes later.

5. As a member, I want to rate and review recipes, so that I can share feedback with other cooks.

6. As an administrator, I want to manage user accounts and moderate content, so that I can maintain a safe and welcoming community.

## MVP Scope

### Must-have

- User registration and login with secure password hashing.
- Role-based access control for members and administrators.
- Recipe creation, viewing, editing, and deletion.
- Structured ingredients and ordered cooking steps.
- Saved recipes and member profiles.
- Recipe ratings and optional written reviews.
- Basic administrator functions for user management and content moderation.

### Nice-to-have

- Ingredient autocomplete suggestions.
- Equipment and utensils information for recipes.
- Recipe image uploading.
- Likes and comments on recipes.
- The ability to mark a recipe as tried.
- Public or private saved recipe collections.
- Recipe browsing, searching, filtering, and pagination.

## Entities

| Entity | Main Attributes | Relations |
|---|---|---|
| User | id, username, email, passwordHash, role | Has many Recipes, SavedRecipes, and RecipeRatings |
| Recipe | id, authorId, title, description, category, difficulty, servings | Belongs to one User; has many Ingredients, RecipeSteps, and RecipeEquipment entries |
| Ingredient | id, recipeId, name, quantity, unit, quantityNote | Belongs to one Recipe |
| RecipeStep | id, recipeId, stepNumber, instruction, duration | Belongs to one Recipe |
| SavedRecipe | id, userId, recipeId, savedAt | Connects one User and one Recipe |
| RecipeRating | id, userId, recipeId, score, reviewText | Connects one User and one Recipe |
| RecipeEquipment | id, recipeId, name, note | Belongs to one Recipe |

Additional entities such as IngredientCatalog and Comment may be introduced if needed during implementation.

## Stretch Feature

**Selected feature: Search, Filter and Pagination**

The application will allow visitors and registered members to search for recipes by title, filter recipes by category or difficulty, and navigate through results using pagination. This will make it easier for users to discover recipes that match their interests.

## Repository

https://github.com/ousapheasun0605-prog/IP1_e20230369
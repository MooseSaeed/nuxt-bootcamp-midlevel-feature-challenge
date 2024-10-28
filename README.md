---
difficulty: 1
tags: codechallenge, Exercise Challenge, Nuxt 3
openFiles: pages/index.vue
---

# Tasty Meals

# Challenge Description

This challenge focuses on building a robust food recipes Nuxt app with dynamic routing, layout management, and error handling. You'll ensure smooth navigation, proper layout rendering, and state management while incorporating some SEO and user experience features.

## Requirements

1. Activate the `admin-layout` only for the `/dashboard` page.

2. Create a `/meals` route to render all meals:

   - Get the meals data from the `/api/meals` endpoint.
   - In the template, use the `<MealList />` component and pass the meals to the `meals` prop.

3. Create a `/meals/:id` route to render an indvidual meal:

   - Get the slug from the route.
   - Get the meal data from the `/api/meals` endpoint.
   - The endpoint expects a slug query string with the value of the slug. Pass the slug to get the meal data.
   - Create and throw a Nuxt error with the error status code and message.

4. Create an error page:

   - Use the `<ErrorPage />` component in the template and pass to it the error prop.
   - The `<ErrorPage />` component is emitting the `button-clicked` event. Clear the error and navigate the user to the homepage when this event is triggered.
   - The error page should use the default layout.

5. Prevent navigation to the `/forbidden` route:

   - Create a middleware that navigates the user to the homepage if they tried to visit `/forbidden`.

6. Enable users to delete meals from the `/dashboard` page:

   - Fetch all meals from the `/api/meals` endpoint.
   - Use the `<MealTable />` component in the template and pass the meals to the `meals` prop.
   - The `<MealTable />` component emits a `meal-clicked` event when the delete button is clicked on a meal. This event carries the meal's `id` as its payload. Create a `deleteMeal` function that sends a `POST` request to the `/api/meals/delete` endpoint with the `{mealId: id}` in the request body.

7. Set the following default `<title>` and `<meta name="description" content="" >` for the whole site:

   - Title: `"Tasty Meals"`
   - Description: `"A collection of the best food in the world"`

8. The page `<title>` for the `/meals/:id` route should update to display the specific meal's title.

9. Use the `savedMeals` Pinia store to set a global state for the saved meals count:

   - The div with the class `saved` in `app.vue` should accuretly render the count of meals saved.
   - The `<MealList />` component in the `/meals` page is emitting a `save-meal` event with the meal's `id` as its payload. Use that event to update the global state.

10. Apply page and layout transitions:
    - Define a page transition named `blur` and it should have the mode `out-in`.
    - Define a layout transition named `blur` and it should have the mode `out-in`.

> 💡 HINT: The blur effect CSS styles are already in place.

## Other Considerations

- If you see the `data-test` attribute in the boilerplate don't remove it. If you remove it, your code may be invalid for the certificate.

- Do not delete or modify the `/server/plugins/doNotChange.ts` file.

- TailwindCSS is preinstalled and with default config. It might be helpful for you if you want to have some styles. Or if you'd like to see a pretty result as you develop.

- It is NOT necessary to have the exact same styles as in the GIF above, or even any styles at all.

- If you're a TypeScript beginner and encounter some issues with it in the challenge, you can skip it by using `// @ts-expect-error` comment on the line above the error.

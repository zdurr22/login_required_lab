# Login Required Lab

## Objectives

We're going to make a Rails app that requires you to be logged in to see one of
its pages.

## Introduction

Our app has three pages:

1. A login page, where the user enters their username. No passwords; we'll
   just trust them. After they're logged in, users are taken to...
2. A welcome page, which says, "Hi, #{username}", and has a link to the
   secret page, which is...
3. A page with a secret on it, which users must be logged in to see.

## Instructions

1. Build out the `SessionsController` with `new`, `create`, and `destroy`
   actions. You can use `resources` or write custom routes to handle these
   controller actions.
2. Write a `current_user` method in the `ApplicationController`.
3. Write a `SecretsController` with a `show` action. This controller should also
   use a `before_action` to prevent any route from being accessed without
   logging in. You can use `resources` or write a custom route to handle this
   controller action.

Use the specs as your guide, but we'd like the following behavior. We should be
able to:

- If the user is not logged in, visiting the root of the app should redirect
  them to a login page.
  - The login page should be handled via the `SessionsController#new` action.
- If a user fails to enter their name on the login page, they should be
  redirected there until they successfully do so.
  - Submitting the login form should be handled via the
    `SessionsController#create` action.
- Once logged in, a user be able see the welcome page at the root route. This
  page should greet the user and link them to the secret page.
- The content and URL of the secret page are up to you. However, if we visit
  that URL without logging in, we should be redirected to the login page. Under
  no circumstances should we allow people who are not logged in to see the
  secrets.

Happy coding!

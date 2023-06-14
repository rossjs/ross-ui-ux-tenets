# Ross’ (HIGHLY OPINIONATED) UI/UX Tenets

## 1. Know your users, know their core goals, understand priorities

If you don’t know your users or their core goals, how can you design the right solution for them?

Sometimes you’re designing for a few specific users that all do the same thing. That’s easy.

Sometimes you’re designing for the general public as a whole. That’s also not too bad.

Other times you’re designing for multiple user groups that want competing things. This is where you need to understand what your main user group is, if there is one, and prioritize their needs.

## 2. The path forward should always be clear

A user should never be unsure of how to proceed through your app.

It should always be clear what core actions a user has available to them at any given point and those should incorporate language and symbology that reinforces what action will be taken. You should also ensure that these actions are accessible by using WCAG standards like aria tags.

Make these core actions stand out in your UI so that users’ eyes are drawn to them. If a search feature is a widely used first-step in your core user stories, make sure it’s near the top of your app and the placeholder text provides proper context.

## 3. Every action should have a clear reaction

It should always be clear to a user what action has taken place after they interact with the UI. A lot of the time, this will be evident by opening up a new UI/page or displaying some data to the user as a result of the user’s action, but other times it may not be.

A common bad pattern is not providing any feedback to a user after they’ve clicked a “save” button. Closing a modal or going back to a previous page can both feel like a bug rather than a confirmation that an action has been taken. It’s always a good idea to provide positive feedback upon success (“Changes saved!”) and helpful guidance upon failure (“Save failed. Please try again.”).

Even if they’ve triggered a background process where no UI change would be necessary, a snackbar/toast message should confirm that the process has indeed been triggered. Additional language on when they could expect that process to be finished or how they will be alerted when it does (email, in-app notification, etc) should also be provided when applicable.

## 4. Don’t lie to your users or make optimistic updates in the UI

Don’t show that a value has been changed in the UI if the request to make the change has not actually succeeded yet. If you are auto-saving form fields, show a loading spinner next to the input to indicate that something is still happening.

If implementing an auto-save feature, showing a Google Docs-esque “changes saved 5 minutes ago” / “changes saved a moment ago” indicator at the top of the page gives the user confidence their changes won’t be lost.

## 5. Provide clear feedback if there is an issue

It should never be ambiguous or unclear why a user can’t progress through your app.

If a user’s input doesn’t pass validation rules, let them know why in helper text below the field. Clearly highlight required fields and provide a helpful message on what fields need to be filled out if a user tries to progress without completing them.

If there was an error loading the data, show a snackbar/toast letting the user know that there was an issue.

## 6. Block as little of the app as possible

When loading data or performing an asynchronous action, only block specifically affected components, not the entire page, with the potential exception of the initial app load. This gives the user a feeling that the UI is loading faster and shows progress as data becomes available and components render. Show a loading overlay or [skeleton](https://mui.com/material-ui/react-skeleton/) component to indicate a placeholder for components will render and indicate that it’s still in a loading state.

## 7. Identify the main workflow of the app and remove all barriers to achieving that

The app should have a clean, clear, and intuitive UI/UX for achieving the main use case. Any advanced or lesser used options should be hidden away behind menus or alternate UI by default.

## 8. Site tours or interactive tutorials are for complex apps and failed UI/UX

If you have to create a tutorial for how to use your “simple” app, you’ve strayed from the path and need to reevaluate what the core goals/workflows are.

If the app is intentionally complex and users are expecting a lot of inputs/controls, then the user needs to be able to understand what each control does as quickly as possible. Having a “How do I…” list of searchable/filterable help menu options that trigger guided tutorials or highlight specific controls is one approach to achieving that. Having clear iconography will also reinforce this.

## 9. More steps/clicks, more pain

The more steps you add to a user’s workflow, the more irksome your app feels and the more likely a user will not realize they have to do something important. Having a user fill in a long form only to not have them remember to hit the “Save” button and lose all their changes is a horrible experience. Users shouldn’t have to remember to do something. The experience should be intuitive and provide clear value to the user, especially if the app is replacing an existing system. If the user can easily accomplish their goals faster than before (while not burdening other types of users), you’ve won the game.

For example, make sure users can use the Tab key to focus the next input if they’re doing data entry.

One of the major benefits of app development is that you can automate or cut down the steps on a cumbersome process. Let’s make sure our users feel that. If you can take something that used to take 15 minutes and make it take 1 (or even less!), you’ve got them. They’ll never want to do it the old way again.

Whenever there’s an opportunity to automate part of the core workflow or insert a sensible default value for an input, those opportunities should be taken. We want our users to feel fast and achieve their goals quickly. If it feels clunky or slow, you’ll lose those users or they’ll provide negative feedback to 


## 10. UNLESS, you’re designing a product for a wide range of users

Then it may make sense to make a more general purpose tool that can fit the use cases for many different kinds of users.

One good example I spoke with Peter about recently was the GPV app he built. A specific customer wanted a tool to automatically get the list of abutters. This was very specific to that customer and wouldn’t make sense to provide that functionality to all users.

At that point, there’s three paths:

1. Just build it and show it to all users (bad, confusing experience for many users)
2. Add a configuration property for all users for whether or not they see this UI (start the “we need to redesign the app” timer now)
3. Create a general purpose tool to select a feature, set a distance, and do an intersection on all features for that buffer

The last option lets the user still achieve what they want to but, at the price of a few extra clicks, it allows any user to use a similar functionality for whatever use case they might have.

## 11. Always get confirmation for destructive or critical actions

If a user triggers an action where the result of that action cannot be undone (for example, sending out an alert message to many users or deleting a project), ALWAYS ask for confirmation before executing it. Make sure that the UI that triggers these actions is styled differently to emphasize the importance of the action.

## 12. Stand on the shoulders of giants (and steal from them)

The best artists steal from others! It’s an inescapable fact that creative expression is, in many ways, just the process of experiencing enough to be able to take pieces of those experiences and combine them to create something new. Web designers do the exact same thing.

Before creating a design, you should find reference images for designs that you like. You may like the way the navigation is organized in one design but really liked the way the buttons looked in another. Make an idea board (Figma’s FigJam board is great for this) to store all of the images of designs you’re looking at for inspiration and make notes under each one about what you like or dislike about aspects of it. There’s plenty of great websites to gather inspiration from as well. I’ve listed a few below.

* [Dribbble](https://dribbble.com/shots/popular/web-design)
* [Figma Community](https://www.figma.com/community)
* [Muzli](https://search.muz.li/)
* [Design Resources](https://designresourc.es/)
* [Design Resources for Developers (GitHub list)](https://github.com/bradtraversy/design-resources-for-developers)

## 13. Don’t try and innovate (unless you’ve got a damned good reason to)

Don’t try and reinvent the wheel when it comes to design. A large part of UI/UX design is making something look nice but also feel familiar. You don’t want to try and break the mold too much here. You shouldn’t try to create a new kind of dropdown menu if your users aren’t going to understand how to use it. When something behaves unexpectedly or a user can’t find the information they’re looking for, it can be very disorienting. Make sure you’re following the well-established paths laid out for how different types of UI components work.

If a client/stakeholder is advocating for some sort of complex or unique component behavior, it may be time to reevaluate what that person is actually trying to achieve and see if there’s a more intuitive way to do it. One stakeholder’s “great idea” can be a 1000 users’ headache and you need to make sure that what makes sense to one person will also be easy to understand by the rest of your users.

If the client’s workflow is actually just that complex or unique that it justifies creating a new UX pattern though, make sure to add visual cues to reinforce what actions are available to your users.

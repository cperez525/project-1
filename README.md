













Home page functionality: script.js - 

Upon landing on the home page, the user's experience will differ slightly based on whether or not they have provided and submitted their name through the "Get Started" modal.

If the user has not yet submitted their name, they will be presented with the "Get Started" button. Clicking "Get Started" will cause a modal to appear prompting the user to enter their name with a short description of the app and its uses. Once the user clicks submit, the modal will clear and then render welcome text with a set animated gif. The home page will also render a greeting under the brand name in the top part of the page. The user can exit the modal simply by clicking the close icon in the top left corner of the modal, and the get started button will not render to the user again (unless they clear their username from local storage)

If the user has submitted their name, they will have a small greeting message below the brand name in the top part of the page. When the user loads the page, the app loops through the user's local storage to see if any local storage keys match the current date. If the user does not have any keys that match the current date in their local storage, the greeting will inform them that they have no scheduled workouts for that day. If the user DOES have a local storage key that matches the current date, the greeting will inform them that scheduled workouts exist, and provides a hyperlink to the scheduler page.


Scheduler page functionality: scheduler.js -

On page load, a table renders rows for each day of the week with two columns each - one that displays the weekday and date, and the other that will render buttons for workouts entered by the user. When the page is loaded, local storage is checked to see if any workouts for the currently displayed days exists, arrays are created for values of keys that do match displayed dates, and a button is rendered in the second row of the appropriate column for each item in that array.

The first column of each row is clickable- doing so will show a modal to the user displaying any workouts the user has already scheduled for the current day (the section where the workouts exist will be blank if the user has none). The modal also provides the user the ability to enter a workout and submit it. Once the user does this, the workout list in the modal is dynamically updated, and a button for that workout is also rendered in the second column of that date's row. Local storage will also store the workout list as a value with the key being the date of the date block clicked to make the modal appear. This workout list store happens regardless of whether or not a key with that respective date exists so that local storage will simply update the value of that key even if it already exists.

Users have two methods of clearing these workouts from the calendar: a time row-specific clear and a global clear. 

The time row clear is triggered by a close icon in the top right corner of the second column in each row. This clear button will clear local storage of the item whose key matches the date of the first column in that row and removes all workout buttons from that row's second column.

The global clear, labeled "Clear All Workouts", stores the username value (if one exists), clears all of local storage and deletes all displayed workout buttons in each row, and then re-enters the stored username value with the existing "username" key name.

At the bottom of the page, the user has "<" and ">" icons. 

Clicking the "<" icon will go to the previous week from where the user's scheduler currently is, and will render buttons for any workouts that exist for any of the dates in local storage. Clicking the ">" icon will go to the next week from where the user's scheduler currently is, and will render buttons for any workouts that match those new dates.

Lastly, clicking the workout buttons will trigger a youtube api response and render 3 videos from youtube in a modal with the workout button's text as the search subject.
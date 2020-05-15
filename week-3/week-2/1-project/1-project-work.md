# The React Hotel

A hotel booking application in React. Homework for the [CodeYourFuture React module](https://codeyourfuture.github.io/syllabus-master/react/)

## Lesson 3

### 1. Storing the search input in a state

**Instructions:** In the following, we will implement the functionality to search for a customer name given the text typed into the customer name field. In the `src/Search.js` file, declare a new state variable named `searchInput` with the corresponding setter function `setSearchInput` (hint: use the React function `useState`). The initial value of the `searchInput` variable can be an empty string. Add a `value` property to the `<input>` tag that is set to the new `searchInput` state variable. Create a new function `handleSearchInput` taking an `event` parameter. This function should use the `setSearchInput` function to update the state variable `searchInput` with what the user typed in the input field. Finally, add a `onChange` prop to the `<input>` tag that is set to the function `handleSearchInput`. Use `console.log()` to output the value received in the `handleSearchInput` function.

**Hint:** Use `event.target.value` to get the input value.

**Test:** In the developer console, check that everything you type in the search input is printed successively for each new character you enter.

### 2. Triggering search when submitting the form

**Instructions:** Still in the `<Search />` component, add a `onSubmit` handler to the `<form>` tag. When the form is submitted (try clicking the search button), get the value of the state `searchInput` and pass it as a parameter to the `search` prop function that has been provided for you (the `search` prop is passed from the `<Bookings />` component).

**Note:** Also your submit handler should take an `event` parameter and add the line `event.preventDefault()` to prevent the browser to implicitely submit the form).

**Test:** Look in the console, you should see the text that is typed in the search input field when submitting the form.

### 3. Implementing the search functionality

**Instructions:** Still in the `<Bookings />` component, implement the `search` method. It must use the `searchVal` variable (that you just passed from the `<Search />` component) to **filter** the search results. The filter function should return bookings where `firstName` or `surname` match `searchVal`. Once filtered, use the `setBookings` function to update the results rendered in `<SearchResults />`.

**Test:** Verify that when you enter an existing first name or surname and submit the form, the results are filtered accordingly in the customers table.

### 4. Display a customer profile - step 1

**Instructions:** Add a new column in the table of the `<SearchResults />` component and display a `<button>` for each row. The text of the button should read "Show profile". Then, create a new `<CustomerProfile />` component. This component should be rendered next to the table in the `<SearchResults />` component. This component should receive one prop `id`. When clicking on a "Show profile" button for a given row, the component `<CustomerProfile />` should display the text "Customer <ID> Profile", where <ID> is the id of the selected customer. Initially, the `<CustomerProfile />` component doesn't show anything.

**Hint:** You need to record the selected customer id after clicking on a "Show profile" button. In which component do you think this state should be defined?

**Test:** When first showing the page, no customer profile is displayed. When clicking the first "Show profile" button of the table, the text "Customer 1 profile" appears. When clickong the second "Show profile" button of the table, the text "Customer 2 profile" appears instead.

### 5. Display a customer profile - step 2

**Instructions:** When a "Show profile" button is clicked in the table, fetch the corresponding customer profile from `https://cyf-react.glitch.me/customers/<ID>` in the `<CustomerProfile />` component. A customer profile should show the customer ID, their email, if they are VIP and their phone number in a list.

**Hint:** You need to use `useEffect` and the correct dependency array. You'll need to fetch customers data from the API every time a "Show profile" button is clicked and render it accordingly.

**Test:** When you click on a "Show profile" button in the table, the corresponding customer profile is loaded and rendered on the screen.

### 6. Show a loading message

**Instructions:** Do you remember in the Homework of the Lesson 2, we fetched the bookings from a remote API. Now show a _loading state_ in `<Bookings />` while the data from the server is being fetched. To test this, try loading data from `https://cyf-react.glitch.me/delayed`, which has a 5 second delay before returning the data. You will need to use another state to record when your application is loading data (this can be a boolean) and display a loading message whenever the application is loading data.

**Hint:** Try looking at your Pokemon app that you worked on in class for an example.

**Test:** A message inviting the user to wait should be displayed on the screen until bookings data can be rendered on the screen. When bookings are rendered, the loading message should be hidden.

### 7. Show an error message

**Instructions:** Finally, display an error message in `<Bookings />` if there is an HTTP error when fetching data from the server. To test this, try loading data from `https://cyf-react.glitch.me/error`, which will return a 500 HTTP error.

**Hint:** Try looking at your Pokemon app that you worked on in class for an example.

**Test:** When loading bookings data from the `/error` endpoint, an error message should be displayed on the screen.

## Stretch Goals

### 8. Create a new booking

**Instructions:** Add a form with `<input>`s for each of the booking fields (first name, surname, title, room id, check in date, check out date) to the bottom of the page. Submitting the form adds the booking to the result table. Note that the new booking won't persist if you refresh the page.

**Test:** When adding a new booking in the form, it should be displayed in the table.

### 9. Sort table columns

**Instructions:** Add an `onClick` handler to the columns of the result table, which sorts the results ascending (A -> Z). Clicking the column again will reverse the sort order to descending (Z -> A).

**Hint:** Try using the `.sort()` method with a callback to do custom sorting.

**Test:** Each column in the table should be clickable to sort results in ascending or descending order.

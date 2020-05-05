# The React Hotel

A hotel booking application in React. Homework for the [CodeYourFuture React module](https://codeyourfuture.github.io/syllabus-master/react/)

![Bookings Search page](Bookings.png)

## Lesson 3

1. Within your `<Header />` component, render the `<Clock />` component (that is provided for you in `src/Clock.js`). Fix the problem where the `setTimeout` timer is not **cleared** if the component is **unmounted**. Hint: look at the Clock exercise you did in class.

2. Convert the `src/Search.js` component into a class component. Add a `constructor` method and initialise a new state `searchInput` to an empty string `''`. Add a `value` property to the `<input>` that you set to your new `searchInput` state. Then create a new method `handleSearchInput` taking an `event` parameter. This method should use `setState` to update the state `searchInput` with what the user typed in the input (hint: use `event.target.value` to get the input value). Finally add a `onChange` property to the `<input>` set to the method `handleSearchInput`.

3. Still in the `<Search />` component, add an `onSubmit` handler to the `<form>` element. When the form is submitted (try clicking the search button), get the value of the state `searchInput` and pass it as a parameter to the `this.props.search` prop function that has been provided for you. Look in the console, you should see the text that is typed in the search box when submitting the form (note: also your submit handler should take an `event` parameter and add the line `event.preventDefault()` to prevent the browser to implicitely submit the form).

4. In the `<Bookings />` component, use state to hold the `FakeBookings` data instead of directly passing it to `<SearchResults />`. Hint: use a `constructor` method to initialise the state with the `FakeBookings` variable.

5. Still in the `<Bookings />` component, implement the `search` method. It must use the `searchVal` (that you just passed from the `<Search />` component) to **filter** the search results. The filter function should return results where `firstName` or `surname` match `searchVal`. Once filtered, use `this.setState` to update the results rendered in `<SearchResults />`.

6. Again in the `<Bookings />` component, use the `fetch()` function to get data from `https://cyf-react.glitch.me`. Hints:

   - Replace `FakeBookings` in the state initialise with `null` (because we haven't fetched any results yet!)
   - Add a `componentDidMount()` method that calls the `fetch()` function and then use `.then()` to handle the response. Try looking at your Pokemon app that you worked on in class for an example
   - When the response comes back use `this.setState` to update the results

7. Now show a _loading state_ in `<Bookings />` while the data from the server is being fetched. To test this, try loading data from `https://cyf-react.glitch.me/delayed`, which has a 5 second delay before returning the data. Hint: try looking at your Pokemon app that you worked on in class for an example

8. Finally, display an error message in `<Bookings />` if there is an HTTP error when fetching data from the server. To test this, try loading data from `https://cyf-react.glitch.me/error`, which will return a 500 HTTP error. Hint: Try looking at your Pokemon app that you worked on in class for an example

### Stretch Goals

1. Add a form with `<input>`s for each of the booking fields (first name, surname, title, room id, check in date, check out date) to the bottom of the page. Submitting the form adds the booking to the result table. Note that the new booking won't persist if you refresh the page.

2. Add an `onClick` handler to the columns of the result table, which sorts the results ascending (A -> Z). Clicking the column again will reverse the sort order to descending (Z -> A). Hint: try using the `.sort()` method with a callback to do custom sorting

# The React Hotel

A hotel booking application in React. Homework for the [CodeYourFuture React module](https://codeyourfuture.github.io/syllabus-master/react/)

![Bookings Search page](Bookings.png)

## Lesson 2

1. Within `src/App.js`, render the `<Restaurant />` component (that is provided for you in `src/Restaurant.js`) underneath the `<Bookings />` component. Then convert the `<Restaurant />` component to a class component.

2. Add a method to the `Restaurant` class named `addOrder`. Use `console.log` to log a "Add order" message. Remember to use the `addOrder = () => {}` syntax. Add a `onClick` handler to the Add `<button>` that calls `this.addOrder`. Ensure that clicking on the button logs your "Add order" message in the console.

3. Extract the `<button>` in the `<Restaurant />` component to a new component named `RestaurantButton`. Pass the `this.addOrder` method as a prop to the `<RestaurantButton />` component and use this prop in the `onClick` handler. Ensure that clicking the button still logs the "Add order" message.

4. Within the `<Restaurant />` component, initialise state to have a key named `orders` and a value of 0 (hint: use the `constructor` method). Then replace the `orders` variable within the `render` method with `this.state.orders` that we just created.

5. Within the `addOrder` method of `<Restaurant />`, use the `this.setState` method to increment the `orders` state by 1. Hint: remember that if we are using previous state to calculate the new state, we must use a callback function with `this.setState`.

6. Extract the `<li>` containing "Pizzas" within the `<Restaurant />` component to a new component named `Order`. Move `orders` initial state set up in the `constructor` and the `addOrder` method from `<Restaurant />` to the new `<Order />` component. Make sure that clicking the "Add" button still increments the number of orders. Then replace the hard-coded string "Pizzas" in `<Order />` with a prop named `orderType`. Finally, render another `<Order />` component but this time with the prop `orderType="Salads"`.

7. Within the `<SearchResults />` component or it's child components, add an `onClick` handler to each row in the table (hint: on the `<tr>` element). When clicked, the row is "selected" and highlighted with a different colour. Hint: use state to add a class to the `className`. When clicking on the row for a second time, "unselect" the row and remove the coloured highlighting.

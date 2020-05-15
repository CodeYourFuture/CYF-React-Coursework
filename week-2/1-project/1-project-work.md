# The React Hotel

A hotel booking application in React. Homework for the [CodeYourFuture React module](https://codeyourfuture.github.io/syllabus-master/react/)

## Lesson 2

### 1. Render the Restaurant component

**Instructions:** Within the `src/App.js` file, render the `<Restaurant />` component (that is provided for you in `src/Restaurant.js`) underneath the `<Bookings />` component.

**Test:** The restaurant orders should render on the page.

### 2. Preparing to add more pizzas

**Instructions:** At the moment, the number of pizzas a guest can order is static and set to 0, even if they click on the 'Add' button. We will change that in the following to let a guest add more pizzas to their order. First, declare a new state variable `orders` along with the function to set the orders state `setOrders`. The initial value of the `orders` state should be **0**. Use the new `orders` variable instead of the `pizzas` variable (that you can now delete).

**Hint:** You need to use the React function `useState` to create a state variable. Remember to import the function at the top with `import React, {useState} from "react";`.

**Test:** Verify the number of ordered pizzas it still **0** on the screen.

### 3. Add more pizzas

**Instructions:** In the `<Restaurant />` component, create a new function named `orderOne`. The `orderOne` function doesn't take any parameters and should use the `setOrders` function to increment the `orders` state variable by 1. Then, add a `onClick` handler to the Add `<button>` that calls the `orderOne` function when it's being clicked.

**Test:** Try to click on the Add button a few times and verify that the number of pizzas increases accordingly.

### 4. Extract the Add button to its own component

**Instructions:** Extract the `<button>` currently in the `<Restaurant />` component to a new component named `RestaurantButton`. Pass the `orderOne` function as a prop to the `<RestaurantButton />` component and use this prop in the `onClick` handler.

**Test:** Clicking the button should still increment the number of pizzas.

### 5. Extract pizza order to its own Order component

**Instructions:** Extract the `<li>` containing "Pizzas" from the `<Restaurant />` component to a new component named `Order`. Also, move the declaration of the `orders` state and the `orderOne` function from the `<Restaurant />` component to the new `<Order />` component. Use the `<Order />` component in the `<ul>` list of the `<Restaurant />` component.

**Test:** Make sure the pizza order is still rendered on the page and that clicking on the "Add" button still increments the number of orders.

### 6. Render more orders

**Instructions:** Pass a new prop named `orderType` to the `<Order />` component with the value "Pizzas". Then render the `orderType` prop instead of "Pizzas" in the `<Order />` component. Make sure that "Pizzas" is still displayed on the screen. In the `<ul>` list of the `<Restaurant />` component, render 2 others `<Order />` components but this time pass different values for the `orderType` prop: "Salads" and "Chocolate cake".

**Test:** For each order, the number of items can be incremented independently. Verify that you are able to explain what is happening.

### 7. Passing bookings from a state variable

**Instructions:** In the `<Bookings />` component, declare a new state `bookings` with the corresponding setter function `setBookings` to hold the `FakeBookings` data. Instead of passing `FakeBookings` directly to the `<SearchResults />` component, pass the new `bookings` state variable.

**Hint:** The new `bookings` state should be initialised with the `FakeBookings` variable.

**Test:** Check that the bookings are still rendered correctly in the page.

### 8. Load bookings remotely

**Instructions:** Instead of getting the existing bookings from the file `data/fakeBookings.json`, we will get and load the bookings from a remote API. In the `<Bookings />` component, use the React function `useEffect` to `console.log()` some text only when the page first renders on the screen. Verify that when you refresh the page, the text appears once in the console. Then, in the `useEffect` function, use the `fetch()` function to get data from `https://cyf-react.glitch.me`.

**Hints:**

- Replace `FakeBookings` in the bookings state and initialise it with `[]` (because we haven't fetched any results yet!)
- After calling the `fetch()` function, use `.then()` to handle the response. Try looking at your Pokemon app that you worked on in class for an example
- When the response comes back, use `setBookings` to update the results

**Test:** Verify the customers data are still displayed correctly in the table.

### 9. Highlight booking row when clicked

**Instructions:** Within the `<SearchResults />` component or its child components, add an `onClick` handler to each row in the table (hint: on the `<tr>` element). When clicked, the row is "selected" and highlighted with a different colour. When clicked again, the row is unselected and the coloured highlighting is removed.

**Hint:** Use a new state variable for each row to record if the row is selected or not, and use this value to set a class to the `className` prop of the row.

**Test:** Verify that each row of your table can be highlighted (on and off) independently when being clicked.

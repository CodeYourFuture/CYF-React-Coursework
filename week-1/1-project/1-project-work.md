# The React Hotel

A hotel booking application in React. Homework for the [CodeYourFuture React module](https://codeyourfuture.github.io/syllabus-master/react/)

![Bookings Search page](Bookings.png)

# Installation

1. Follow [the instructions](https://codeyourfuture.github.io/syllabus-master/others/making-a-pull-request.html#how-to-fork-a-github-repo) to fork & clone the GitHub repo
2. Install the dependencies by running `npm install`
3. Launch the server using `npm start`
4. It should automatically open `http://localhost:3000/` in your browser

# Exercises

## Lesson 1

#### 1. Extract the search button in its own component

**Instructions:** Extract the search `<button>` from the `src/Search.js` file to be its own separate component. You can name it `SearchButton`. Import and use this new component in `src/Search.js`.

**Test:** The search button should still render on the page.

#### 2. Extract the header in its own component

**Instructions:** Extract the `<header>` from the `src/App.js` file to be its own separate component called `Heading`. Make sure that you import and render the `<Heading />` component within `src/App.js`. In the `Heading` component, render the hotel's logo in an `<img>` (you can use `https://image.flaticon.com/icons/svg/139/139899.svg` or find your own image URL). You can adjust the CSS by editing `src/App.css` to make your Heading looks better if necessary.

**Test:** The header should be displayed with a logo on the page.

#### 3. Create and use a new component to show info cards

**Instructions:** In `src/App.js`, above the `<Bookings />` component add a new component called `TouristInfoCards` which shows 3 _cards_. A card is a common user interface pattern with an image at the top and some related text underneath. The cards must link to `peoplemakeglasgow.com`, `visitmanchester.com` and `visitlondon.com`. The cards should contain the name of the city and an image of the city.

**Hint:** Use the same className as the example below to benefit from [Bootstrap](https://getbootstrap.com/docs/4.2/components/card) library which is already imported for you in the project. Use the JSX code below as an example of one card (note that in JSX, you'll need to use `className` instead of `class`):

```
<div className="card">
	<img src="..." className="card-img-top" />
	<div className="card-body">
		<a href="#" className="btn btn-primary">Go somewhere</a>
	</div>
</div>
```

**Test:** 3 info cards should be displayed on the page for each city (Glasgow, Manchester, London). Each card should link to the correct website.

#### 4. Create a Footer component

**Instructions:** Create a `<Footer />` component which should be rendered at the bottom of the page. Pass the following array as a prop to this component: `["123 Fake Street, London, E1 4UD", "hello@fakehotel.com", "0123 456789"]`. Inside the component, use the data you passed as a prop to render a `<ul>` list with each item of the array displayed as a `<li>`.

**Hint:** The `.map()` method will by useful.

**Test:** The footer should render at the bottom of the page with each address property displayed as a list item.

#### 5. Create a table to show hotel bookings

**Instructions:** Create a `<SearchResults />` component that shows hotel bookings in a `<table>` element. Each booking will have an `id`, `title`, `first name`, `surname`, `email`, `room id`, `check in date` and `check out date`. You can make up data in the `<SearchResults />` component to show in the table. Then show `<SearchResults />` component within the `<Bookings />` component that is provided. Be sure to split out your components into small well-named components, similar to the method used in exercise 1.

**Hint:** You will find some useful `<table>` examples in the [Bootstrap documentation for tables](https://getbootstrap.com/docs/4.2/content/tables/#examples).

**Test:** A table should render with a column for each booking attribute. The table can show more than one booking. The bookings that are displayed can be made up and hardcoded for now.

#### 6. Show more bookings in the table

**Instructions:** Instead of using your hard-coded data in the `<SearchResults />` component, load data from the `src/data/fakeBookings.json` file in the `<Bookings />` component and pass it as a prop to `<SearchResults />`. All the bookings in `src/data/fakeBookings.json` should now be displayed in your table.

**Hint:** Look in the `<Bookings />` component for how to import data from a JSON file.

**Test:** All the bookings in the file `src/data/fakeBookings.json` should be displayed in your table.

#### 7. Calculate and show the number of nights for each booking

**Instructions:** Add another column to your `<SearchResults />` table which shows the number of nights a guest is staying.

**Hint:** Try installing the [moment.js library](http://momentjs.com/) (you'll need to install it with `npm install moment --save`) and using the [`.diff()` method](http://momentjs.com/docs/#/displaying/difference/) to compare dates.

**Test:** Each booking in your table should show the number of nights in a separate column. For example, Mr John Doe has a booking for **2** nights.

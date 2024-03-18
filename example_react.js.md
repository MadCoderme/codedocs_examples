## TodoList Component Documentation

**Table of Contents**

* [Overview](#overview)
* [State Management](#state-management)
* [Functions](#functions)
    * `handleChange(e)`
    * `handleSubmit(e)`
    * `handleDelete(index)`
* [Render](#render)

---

## Overview

The `TodoList` component is a React component that allows users to create and manage a list of tasks. It utilizes state management and event handlers to dynamically update the list based on user interaction.

## State Management

This component utilizes the `useState` hook to manage two pieces of state:

* `todos`: An array containing the list of todo items.
* `inputValue`: The current value entered in the input field.

## Functions

### `handleChange(e)`

This function is triggered whenever the input field value changes. It updates the `inputValue` state with the current value of the input field.

### `handleSubmit(e)`

This function is triggered when the "Add Todo" button is clicked. It prevents the default form submission behavior and performs the following actions:

1. Adds the current `inputValue` to the `todos` array.
2. Resets the `inputValue` state to an empty string.

### `handleDelete(index)`

This function is triggered when the "Delete" button next to a specific todo item is clicked. It removes the corresponding todo item from the `todos` array based on the provided `index`.

## Render

The `render` function of the `TodoList` component displays the following elements:

* A heading (`h1`) with the text "Todo List".
* A form containing:
    * An input field for entering new todo items. Its value is bound to the `inputValue` state and updated via the `handleChange` function.
    * A button labeled "Add Todo" that triggers the `handleSubmit` function when clicked.
* An unordered list (`ul`) that displays each todo item from the `todos` array. Each item includes:
    * The text of the todo item.
    * A "Delete" button that triggers the `handleDelete` function with the corresponding index when clicked.

This component provides a basic but functional user interface for managing a list of tasks.

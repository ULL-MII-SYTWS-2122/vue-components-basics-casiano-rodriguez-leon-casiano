# Vue.js Components Basics

This lab corresponds to the section **Component Basics** of the VueSchool course 
[Vue.js Components Fundamentals](https://vueschool.io/courses/vuejs-components-fundamentals)

This repository contains only the example codes for 

1. The **click counter** (video *[Introduction to Components](https://vueschool.io/lessons/introduction-to-components)*) and 
2. **plan-picker** 
   
examples used inside the initial section of the tutorial **Component Basics**.

## Folder click-counter: Click Counter Task 


Watch the videos 

1. *[Introduction to Components](https://vueschool.io/lessons/introduction-to-components)* 
2. [Component's Template](https://vueschool.io/lessons/components-template) 2:20


And write your code inside the empty files `index.html` and `app.js`.

Files [click-counter/solution.html](click-counter/solution.html) and [click-counter/solution-app.js](click-counter/solution-app.js) contain the final solution. 

See the solution working at <https://crguezl.github.io/vuejs-components-basics-plan-picker-component/click-counter/solution.html>


```
├── app.js
├── index.html
├── solution-app.js
└── solution.html
```

### Check List

- [ ] Set the initial HTML and load Vue from the CDN
- [ ] Inside the app create the Vue app attached to the corresponding div element 
- [ ] Create a component `click-counter` using `Vue.component`
  - [ ] Add the ´data` function that returns the object with the data. 
  - [ ] Set the `count`
  - [ ] Set the template 
- [ ] Add in the `app` div of the HTML the component just created
- [ ] Insert new instances of the component in the HTML
- [ ] Move the template from the `app.js` to the HTML using  a `script` tag
- [ ] Add a second element, a paragraph `the count is` to the `click-counter` component 
- [ ] Wrap the two elements in a `<div>`

Use as many [emmet expressions](https://docs.emmet.io/cheat-sheet/) as you can to speed up the edition

## Folder plan-picker: Plan Picker Task

Watch the videos 

* [Reusable Components with Props](https://vueschool.io/lessons/reusable-components-with-props) 6:46
* [Nested Components](https://vueschool.io/lessons/nested-components) 1:50
* [Global vs Local Components 3:11](https://vueschool.io/lessons/global-vs-local-components)
* [Communication Between Components with Custom Events](https://vueschool.io/lessons/communication-between-components) 7:24

Leave your solution inside the files `index.html` and `app.js`.

```
├── coffee.jpg
├── index.html
├── logo.png
├── solution-app.js
├── solution.html
└── style.css
```

Files [plan-picker/solution.html](plan-picker/solution.html) and [plan-picker/solution-app.js](plan-picker/solution-app.js) contain the final solution. 

See the solution working at <https://crguezl.github.io/vuejs-components-basics-plan-picker-component/plan-picker/solution.html>

### Check List 

- [ ] Use a minimum number of emmet expressions to generate complete the initial `index.html` to have it as at the beginning of the video [Reusable Components with Props](https://vueschool.io/lessons/reusable-components-with-props). The structure to replicate three or four times has to follow this pattern:
  
  ```html
        <div class="plans">
            <div class="plan">
                <div class="description">
                    <span class="title">
                    The Single
                    </span>
                </div>
            </div>
            ...  more like the one above
        </div>
  ```
  - [ ] Here is a [solution](plan-picker/solution.emmet)
- [ ] Create the `plan` component that encapsulates the template above
- [ ] Add it the `prop` with the `name` and update the HTML accordingly for all the repetitions
- [ ] Add to the Vue app data the `plans` array of Strings with the names of the plans
- [ ] Substitute the repetitions of the `<plan>` component  inside  the HTML for a `v-for`  loop
- [ ] Specify that the `prop` `name` has to be of type `String` and is `required`
- [ ] **Nested Components Video**: Create a component <plan-picker>  to encapsulate the `.plans` div
- [ ] Create the template for the component and move the `plans`array into the component
- [ ] Make the `plan` component local to the `plan-picker` component
- [ ] Make the `plan-picker` component local to the root component
- [ ] [Communication Between Components with Custom Events](https://vueschool.io/lessons/communication-between-components): We want to add the capability to select a plan. Add a boolean variable `selected` to the `plan` component
- [ ] Add a `select` method to the  `plan` component to set the component as `selected` 
- [ ] Add the code so that when a user clicks on the corresponding `plan` component its `selected` variable is set to `true`
- [ ] Using the object syntax for `v-bind` add a class `active-plan` when a `plan` component is selected
- [ ] Verify that the solution given permits several plans to be selected
- [ ] Make the `plan` component to `$emit` an event with name `select` and payload the `name`of the plan
  - [ ] Read my notes on the api of [vm.$emit( eventName, […args] )](https://crguezl.github.io/learning-vue-geting-started-guide/#vm.emit-eventname-args)
- [ ] Check in the Vue DevTools the presence of the events 
- [ ] Inside the `plan-picker` component template set  the triggering of a method `selectPlan` to fire when the `select`  event is emitted. 
- [ ] Inside the `plan-picker` component add a data attribute `selectedPlan` to store the plan that was selected by the user
- [ ] Add also the code for the `selectPlan` method
- [ ] Go back to the `plan` component and remove the `selected` data property (it is no longer need, since the parent component now knows which plan has been selected)
- [ ] Add a property `selectedPlan` to the `plan` component (that will be passed by the parent)
- [ ] Add a computed property `isSelected` to the `plan` component that is `true` when the plan is the one selected
- [ ] In the template of the `plan` component conditionally bind the class `active-plan` if the plan has been selected

## Skills Covered

After this lab, you'll be familiar with:

- The idea behind components and how Vue.js components work
- Component's template, and couple of ways to define your template
- Communication between components with props and custom events
- What is the difference between global and local component registration

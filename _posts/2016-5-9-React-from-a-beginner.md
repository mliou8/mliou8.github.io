---
layout: post
title: Beginning React pt. 1
---

I’ve been working on learning react lately, and so I think it would help if I start outlining what I’m learning about it.
Part 1 will cover what it takes to get basic components rendered into an app, and then maybe also cover how to do routing. I want to start big picture first.

Components:

First you have to build components. They’re basically React classes with various methods, the most important one being the “render” method. 

The render method returns a HTML element that will be rendered when this particular component is called. The components are passed from one file to another by using the module.exports functionality of node. 

Components are basically Angular “factories”, or ways to organize your code into different portions. 
This is a simple example of what a component file could look like:

```
var React = require('react');

var Home = React.createClass({
  render: function(){
    return(
      <h2>
	This is a Header. 
      </h2>
    )
  }
})

module.exports = Home;

```
Now you might need a simple routes file, to render this component. 

```
var React = require('react');
var Main = require('../components/Main');
var SomeOtherComponent = require('../components/SomeOtherComponent');
var Router = require('react-router');
var Route = Router.Route;
var IndexRoute = Router.IndexRoute;

module.exports = (
  <Route path="/" component={Main}>
    <IndexRoute component={SomeOtherComponent} />
  </Route>
);

```
The <Route> element allows you to pass in paths, and then specify components that you required in to be rendered. You have to make sure to put the components into single brackets to make sure that they’re extrapolated. So here the default “/“ path will render the Main component that was built earlier. 

The IndexRoute component here allows you to “chain” off of the Home route, so that SomeOtherComponent is passed in as a child component of Main.

To get more specific routes, you can pass in dynamic paths like this one.

```
<Route path=“/” component={Main}> 
	<route path=“profile/:username” component={Profile} />
          <IndexRoute component={SomeOtherComponent} />
</Route>
```
Anything that gets passed in after profile will be considered as a “username”, and that can be accessed within components by referencing it using {this.props.params.username}.

Components can also take in other components, using the same var Component = require(‘./components/component’) syntax. This can simplify the process by combining the logic of a lot of smaller components into a main component and then passing that main component into the routing file.

## The Pillars of Frontend Architecture

> Every building needs a solid foundation, four walls, and a roof. Successful architects must provide these As FE architects, we are under a similar obligation any time we create a new web property.

Foundation of a scalable and sustainable design system. Our inch-deep, mile-wide understanding of the entire FE development space is what allows us to be champions for new technologies and methodologies. None of us are masters of all of them.

#### The Pillars

* Code
    
  How to approach the HTML, CSS, and JavaScript of a design system. Setting expectations for code written and assets created.
* Process

  Tools and processes that'll create an efficient and error-proof workflow. Gains  in productivity, efficiency, consistency v. over-engineering and unnecessary abstraction.

* Testing

  We need to ensure that any code we wrote yesterday isn't devalued by the code we write today. Creating a plan for sufficient test coverage. Different methods of testing

* Documentation

  > It seems that few see the value of spending time on documentation until a key member of the team is leaving, then it's "stop everything and document all the things."

  Documentation should be written at the same time as the process or artifact being developed. Various types of documentation, tools used for publication, types of end users for ingesting content.

### Code

> Good code never happens by accident. Left to our own devices, we are capable of producing a wide variety of solutions to the same problem. There's rarely a single best solution to any problem. We tackle problems differently because we have different experiences, opinions, and tendencies. There's nothing wrong with inconsistencies between devs. It's often our ability to look at problems differently that makes our teams stronger. But when it comes to writing solutions and committing, there's no desire or need for our code to reflect those differences.

The code pillar is here for conversations about code quality of HTML, CSS, and JavaScript. It defines how classes are written, functions are built, and how interfaces are marked up. As an architect, it's your job to continually explore and evaluate new techniques, platforms, methodologies, frameworks. No one size fits all solution. Discovering project needs and matching them up with current FE dev landscape is your responsibility.

#### HTML

>Text, images, links, forms, and submit buttons: that's all the Web really needs, and it's the foundation of anything you'll create. Bad markup, and you'll write bad CSS and bad JavaScript to compensate.

In the past, markup was generally either **procedural** or **static**.

Procedural Markup: 100% Automation, 0% Control

```html
<div id="header" class="clearfix">
  <div id="header-screen" class="clearfix">
    <div id="header-inner" class="container-12 clearfix">
      <div id="nav-header" role="navigation">
        <div class="region region-navigation">
          <div class="block block-system block-menu">
            <div class="block-inner">
              <div class="content">
                <ul class="menu">
                  <li class="first leaf">
                    <a href="/start">Get Started</a>
```

Div Soup.

Static Markup: 100% Automation, 0% Control

```html
<header>
  <section>
    <nav>
      <div>
        <ul>
          <li>
            <a href="/products">Products</a>
            <ul>
              <li>
                <a href="/socks">Socks</a>
```

- Striking a Balance Between Control and Automation

Must evaluate processes for producing your markup. How much control over order of the content, elements used, CSS classes applied to them. How difficult to change in the future? Templates easily accessible? Any need to loop in a BE person for the change? Is markup even based on a templating system? Can changes be propegated throughout the entire system?

- Modular Markup: 100% Automation, 100% Control

Utopian state is one where every line of HTML on our site is programmatically created, but with FE devs having full control over templates and processes used to create markup. A modular approach will help provide flexibility with necessary automation.

- It All Leads to a Design System

A website page is a relic of the past. We are no longer building pages. We are building design systems.

> A design system is the programmatic representation of a website's visual language. The visual language, created by our designers, is an artifact that expresses how the website visually communicates its message to users. It is a collection of colors, fonts, buttons, image styles, typographical rhythms, and UI patterns used to convey mood, meaning, and intent.

Spoken language can be broken down into nouns, verbs, adjectives. As FE devs we must deconstruct the visual language into its smallest pieces. By doing this, we can create rules about how to put it back together again.

The Many Faces of Modular CSS Methodologies

As many CSS methodologies today as there are CSS / JS frameworks. Unlike frameworks (usually all or nothing), CSS methodology is more of a philosophy about the relationship between HTML and CSS than a prebuilt codebase. Some prominent methodologies at time of writing:

* [Object-Oriented CSS (OOCSS)](http://oocss.org/)

```html
<div class="toggle simple">
  <div class="toggle-control open">
    <h1 class="toggle-title">Title 1</h1>
  </div>
  <div class="toggle-details open"> ... </div>
  ...
</div>
```

Two main principles are separating structure from skin and separating container and content.

  * _Separating structure from skin_ means defining visual features in a way that they can be reused. `toggle` element above is small and resusable. Can be displayed with various skins altering its appearence.

  * _Separating container from content_ means not using location as a style quantifier. instead of styling tags inside a container, create reusuable classes that will apply the required text treatment regardless of the element it's used on. This way you can leverage default styles if no class is applied.

This approach is useful if you want to provide developers a set of components they can mix and match to create UIs. An example of this in practice is Bootstrap. A system of objects adorned with various skins. Goal of Bootstrap is to create a complete system capable of creating any UI a developer may need to put together.
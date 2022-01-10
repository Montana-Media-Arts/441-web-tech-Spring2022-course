---
title: OOP Terminology
module: 7
jotted: false
---


# OOP Terminology
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'why')">Why</button>
  <button class="tablinks" onclick="openTab(event, 'property')">Property</button>
  <button class="tablinks" onclick="openTab(event, 'functions')">Function</button>
  <button class="tablinks" onclick="openTab(event, 'instantiation')">Instantiation</button>
  <button class="tablinks" onclick="openTab(event, 'this')">this</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">
Let me start by saying, there are a lot of terms.  Have you gathered that yet?  In programming, just like in your other classes, there are a lot of words that we have to know to be successful.  I am one hundred percent sure, you all could start talking about some graphic design terms, and I would be somewhat lost.  However, once we learn the terminology, then the subject matter becomes much less scary.

When it comes to OOP, there are two fundamental aspects.  They are Classes and Objects. 

Let's start again with **what**.  What are classes, and what are objects?

1. **Classes** - They are the blueprints or generic templates
2. **Objects** - They are the specific instances of those blueprints/templates.
</div>
</div>

<div id="why" class="tabcontent">
<div class="tabhtml" markdown="1">

**Why do we use classes and objects**

We use classes to represent something generically and specific objects to describe the actual items.

What does that mean?  Let's look at an example:

Let's take a person as an example.  What do all people have?

1. Eye Color
2. Number of Legs
3. Number of Arms
4. Hair Color
5. Height
6. Weight

That is our class.  If what I specified above is the generic template, then a specific instance or object is:

1. Blue eyes
2. Two legs
3. Two arms
4. Brown Hair
5. 5 foot 10 inches
6. 175 lbs

And we can create more people from the same class.  The beautiful part is that we don't have to create multiple classes, just numerous objects from the same class.

We will dig into Classes and Object in more detail in the next section.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/KpR0JqDM7l4" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="property" class="tabcontent">
<div class="tabhtml" markdown="1">

## Property

An object or class **property**, also known as an **attribute**, is a piece of data used to describe the resulting object.

In our previous example, the properties were Eye color, Number of Legs, Number of Arms, Hair Color, Height, Weight.  All of these things described our person.

When we created the object, they all had values like Blue eyes, two legs, etc.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/ri_LeIl5YnQ" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="functions" class="tabcontent">
<div class="tabhtml" markdown="1">

## Functions

An object or class **function** is what "does stuff."  So, any function you create, which you have done already, does stuff for you.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/AdjzvrJgjbw" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="instantiation" class="tabcontent">
<div class="tabhtml" markdown="1">

## Instantiation (aka. `new`)

When we create a new _object_ from a _class_, we are **instantiating** the _new_ object.

As we will see throughout this week's content, to create a new _instance_ of a class, we will use the JavaScript keyword `new`.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/ai-7VOugRNw" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="this" class="tabcontent">
<div class="tabhtml" markdown="1">

## this

A potentially confusing idea is the reference to "specific instances" of an object. When referring to a specific instance of an object, or when referring to an object's instance (from within the object), we will use the term **this**.

JavaScript uses the `this` keyword throughout the language. Using `this` can be very confusing (hence why it has remained anonymous until now). Before we dive deep into `this`, try and accept that `this` refers to a variable in the object itself.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/EhG17j2FmwM" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

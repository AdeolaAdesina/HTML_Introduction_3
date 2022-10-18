# HTML_Introduction_3

#Introduction to HTML forms.

Forms are a part of everyday life. When we use a physical form in real life, we write down information and give it to someone to process. Think of the times you’ve had to fill out information for various applications like a job, or a bank account, or dropped off a completed suggestion card — each instance is a form!

There’s a good chance that if you’re typing into a text field or providing an input, the field that you’re typing into is part of a ```<form>```!

In this lesson, we’ll go over the structure and syntax of a <form> and the many elements that populate it.

# How a Form Works

The ```<form>``` element is a great tool for collecting information, but then we need to send that information somewhere else for processing. 

We need to supply the <form> element with both the location of where the <form>‘s information goes and what HTTP request to make. Take a look at the sample ```<form>``` below:

```
<form action="/example.html" method="POST">
</form>
```

In the above example, we’ve created the skeleton for a ```<form>``` that will send information to example.html as a POST request:

- The action attribute determines where the information is sent.
- The method attribute is assigned a HTTP verb that is included in the HTTP request.

The ```<form>``` element can also contain child elements. For instance, it would be helpful to provide a header so that users know what this ```<form>``` is about. We could also add a paragraph to provide even more detail. Let’s see an example of this in code:

```
<form action="/example.html" method="POST">
  <h1>Creating a form</h1>
  <p>Looks like you want to learn how to create an HTML form. Well, the best way to learn is to play around with it.</p>
</form>
```

The example above doesn’t collect any user input, but we’ll do that in the next class.

# Text Input

If we want to create an input field in our ```<form>```, we’ll need the help of the ```<input>``` element.

The ```<input>``` element has a type attribute and name attribute. The type attribute determines how it renders on the web page and what kind of data it can accept.

The first value for the type attribute we’re going to explore is "text". When we create an ```<input>``` element with type="text", it renders a text field that users can type into. Note that the default value of type is "text". It’s also important that we include a name attribute for the ```<input>``` — without the name attribute, information in the ```<input>``` won’t be sent when the ```<form>``` is submitted.

For example:

```
<form action="/example.html" method="POST">
  <input type="text" name="first-text-field">
</form>
```

This form will render like this:

![Screenshot 2022-10-18 at 20 07 15](https://user-images.githubusercontent.com/29931071/196523413-30c09c0a-d00a-4ef6-b7f8-e2dbfe08ac7a.png)


When the form is submitted, the text: "first-text-field=important details" is sent to /example.html because the value of the name attribute is "first-text-field" and the value of value is "important details".

We could also assign a default value for the value attribute so that users have a pre-filled text field when they first see the rendered form like so:

```
<form action="/example.html" method="POST">
  <input type="text" name="first-text-field" value="already pre-filled">
</form>
```

![Screenshot 2022-10-18 at 20 11 13](https://user-images.githubusercontent.com/29931071/196524081-5995a481-a16f-494d-b8c3-f248ac4077ba.png)


## Class work

1 Let’s start with creating a login form for our users. Open a new folder and a new index.txt file inside it, create the html, head and body element.

Inside the body element, create a form element.

Inside the provided ```<form>``` element, add an ```<input>``` element with a type attribute of "text".

2 Even though we’re not submitting the form, let’s develop some good habits by giving the ```<input>``` a name attribute with a value of "username"

3 Add a value attribute with a value of "Polygon"

Solution: Index.txt will be:

```
<html>

<head>

</head>

<body>

<form>

<input type="text" name="username" value="Polygon"></input>

</form>

</body>

</html>
```

# Adding a Label

In the previous exercise we created an ```<input>``` element but we didn’t include anything to explain what the ```<input>``` is used for. For a user to properly identify an ```<input>``` we use the appropriately named ```<label>``` element.

The ```<label>``` element has an opening and closing tag and displays text that is written between the opening and closing tags. 

To associate a ```<label>``` and an ```<input>```, the ```<input>``` needs an id attribute. We then assign the for attribute of the ```<label>``` element with the value of the id attribute of <input>, like so:

```
<form action="/example.html" method="POST">
  <label for="meal">What do you want to eat?</label>
  <br>
  <input type="text" name="food" id="meal">
</form>
```

## Class work

Add a ```<label>``` element that is associated with the included ```<input>``` element in index.html. (use the for attribute!)

Then add text Username within the ```<label>``` element.

After clearing this checkpoint, click on the Username label in the web browser to see the corresponding ```<input>``` field selected.

Solution: Index.txt will be:

```
<html>

<head>

</head>

<body>

<form>

<label for="username">Username</label>

<input type="text" name="username" value="Polygon"></input>

</form>

</body>

</html>
```


# Password Input

Think about all those times we have to put sensitive information, like a password or PIN, into a ```<form>```. We wouldn’t want our information to be seen by anyone peeking over our shoulder! Luckily, we have the type="password" attribute for ```<input>```!

An ```<input type ="password">``` element will replace input text with another character like an asterisk (*) or a dot (•). The code below provides an example of how to create a password field:

```
<form>
  <label for="user-password">Password: </label>
  <input type="password" id="user-password" name="user-password">
</form>
```

![Screenshot 2022-10-18 at 20 30 00 copy](https://user-images.githubusercontent.com/29931071/196527687-c9ab7d42-4633-450c-a091-fc29dc9f77d6.png)


## Class work

To complete our login page in index.html we need a password field. Add an ```<input>``` element under the second ```<label>``` element.

Assign the id to the correct value to associate the second ```<label>``` with this new ```<input>```.
Set the newly created ```<input>``` element’s type attribute to "password".
Set the name attribute to "user-pw".

Solution: Index.txt will be:

```
<html>

<head>

</head>

<body>

<form>

<label for="username">Username</label>

<input type="text" name="username" value="Polygon"></input>

<label for="user-pw">Password</label>

<input type="password" name="user-pw"></input>

</form>

</body>

</html>
```

# Number Input

We’ve now gone over two type attributes for ```<input>``` related to text. But, we might want our users to type in a number — in which case we can set the type attribute to… (you guessed it)… "number"!

By setting type="number" for an ```<input>``` we can restrict what users type into the input field to just numbers (and a few special characters like -, +, and .). 

We can also provide a step attribute which creates arrows inside the input field to increase or decrease by the value of the step attribute. Below is the code needed to render an input field for numbers:

```
<form>
  <label for="years"> Years of experience: </label>
  <input id="years" name="years" type="number" step="1">
</form>
```

![Screenshot 2022-10-18 at 20 53 28](https://user-images.githubusercontent.com/29931071/196532299-b66cf5ca-135e-4c12-a418-cae6aad8951a.png)


## Class work

In index.html we started a ```<form>``` for users. Right now we have a ```<label>``` that needs an associated ```<input>``` element.

Since we want users to enter a number, create an ```<input>``` for "Years of experience"and set the attributes:

Associate the ```<input>``` to the first ```<label>``` by assigning the correct value to id.
type="number"
step="1"
name to "amount".


Solution: Index.txt will be:

```
<html>

<head>

</head>

<body>

<form>

<label for="username">Username</label>

<input type="text" name="username" value="Polygon"></input>

<label for="user-pw">Password</label>

<input type="password" name="user-pw"></input>

<label for="amount">Years of experience</label>

<input id="amount" type="number" step="1" name="amount"></input>

</form>

</body>

</html>
```

# Range Input

Using an ```<input type="number">``` is great if we want to allow users to type in any number of their choosing. 

But, if we wanted to limit what numbers our users could type we might consider using a different type value. Another option we could use is setting type to "range" which creates a slider.

To set the minimum and maximum values of the slider we assign values to the min and max attribute of the ```<input>```. We could also control how smooth and fluid the slider works by assigning the step attribute a value. 

Smaller step values will make the slider move more fluidly, whereas larger step values will make the slider move more noticeably. Take a look at the code to create a slider:

```
<form>
  <label for="volume"> Volume Control</label>
  <input id="volume" name="volume" type="range" min="0" max="100" step="1">
</form>
```


## Class work

In Index.txt, add an ```<input>``` element. Set the id and name to "doneness". Also, set the type attribute to "range".

For the newly created ```<input>``` set the:

- min attribute to "0".
- max attribute to "5".
- step attribute to "0.5".

Solution: Index.txt will look like this.

```
<html>

<head>

</head>

<body>

<form>

<label for="username">Username</label>

<input type="text" name="username" value="Polygon"></input>

<label for="user-pw">Password</label>

<input type="password" name="user-pw"></input>

<label for="amount">Years of experience</label>

<input id="amount" type="number" step="1" name=""amount></input>

<label for="doness">Range</label>

<input id="doneness" type="range" step="0.5" name="doneness" min="0" max="5"></input>

</form>

</body>

</html>
```

# Checkbox Input

So far the types of inputs we’ve allowed were all single choices. But, what if we presented multiple options to users and allow them to select any number of options? Sounds like we could use checkboxes! In a ```<form>``` we would use the ```<input>``` element and set type="checkbox". Examine the code used to create multiple checkboxes:

```<form>
  <p>Choose your pizza toppings:</p>
  <label for="cheese">Extra cheese</label>
  <input id="cheese" name="topping" type="checkbox" value="cheese">
  <br>
  <label for="pepperoni">Pepperoni</label>
  <input id="pepperoni" name="topping" type="checkbox" value="pepperoni">
  <br>
  <label for="anchovy">Anchovy</label>
  <input id="anchovy" name="topping" type="checkbox" value="anchovy">
</form>
```

![Screenshot 2022-10-18 at 21 21 01](https://user-images.githubusercontent.com/29931071/196537532-cdf21028-ba3f-41b3-addf-ce8290b0ea38.png)

Notice in the example provided:

- there are assigned values to the value attribute of the checkboxes. These values are not visible on the form itself, that’s why it is important that we   use an associated ```<label>``` to identify the checkbox.
- each ```<input>``` has the same value for the name attribute. Using the same name for each checkbox groups the <input>s together. However, each ```<input>``` has a unique id to pair with a ```<label>```.


## Class work

Add an ```<input>``` element associated with a new ```<label>```.

The label should be named "level".

The created ```<input>``` should have:

an id set to "100level".
a name attribute with a value of "level".
a type set to "checkbox"
a value of "100level".

Now do the same for 200 level and 300 level

Solution: Index.txt will be:

```
<html>

<head>

</head>

<body>

<form>

<label for="username">Username</label>

<input type="text" name="username" value="Polygon"></input>

<label for="user-pw">Password</label>

<input type="password" name="user-pw"></input>

<label for="amount">Years of experience</label>

<input id="amount" type="number" step="1" name=""amount></input>

<label for="doness">Range</label>

<input id="doneness" type="range" step="0.5" name="doneness" min="0" max="5"></input>

<p>Choose your level:</p>

<label for="100level">100 level</label>
<input id="100level" name="level" type="checkbox" value="100level">
<br>

<label for="200level">200 level</label>
<input id="200level" name="level" type="checkbox" value="200level">
<br>

<label for="300level">300 level</label>
<input id="300level" name="level" type="checkbox" value="300level">
<br>

</form>

</body>

</html>
```

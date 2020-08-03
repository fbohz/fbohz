# HTML Forms: The Action Attribute

> When building forms and asking data on your site or web application, you'll often want to do something with your data, right? Here's is where the form `action` attribute comes into play.

You should know the basics of creating a form in HTML. You basically wrap your form contents in the `<form>` tag. In the opening tag there are a couple of attributes we can use, and one of them is the `action`. The action attribute is used to specify where we want to send the form data when the form is submitted. So the value of the action is the page that will process the form.

Let's take a look at an example.

```html
<form action="process.html" method="get">
  <label for="username">User</label>
  <input type="text" id="username" name="username"><br><br>
  <label for="email">Email</label>
  <input type="email" id="email" name="email"><br><br>
  <input type="submit" value="Submit">
</form>
```
Here the action is sending the username and email data to a page named `process.html`. Here the destination might do stuff with this data, like creating an user, or just submitting a form to sign up for an event. Here the server has the data and can do as it finds suitable with it. 

Now plug in the form example above in an actual HTML file and then create another file named process.html in the same folder, with the following contents.

```html
<html>
    <head>
        <meta charset="UTF-8">
        <title>Process</title>
    </head>
    <body>This is the destination process page</body>
</html>
```

Let's now fill out the form. E.g.:

![Screen Shot 2020-08-02 at 10 18 56 PM](https://user-images.githubusercontent.com/15071636/89143137-25957900-d50f-11ea-9b41-01c6a1f539e7.png)

Now click submit. Notice we where automatically taken to process.html page! Then, did you notice the URL bar, what is all that extra data? The data after the `?` symbol are query parameters, and since we specified the request as GET, the data is being passed as query parameters.

![Screen Shot 2020-08-02 at 10 34 02 PM](https://user-images.githubusercontent.com/15071636/89143511-75287480-d510-11ea-89a6-8d3b872d73dd.png)

Now obviously, with this example you might think this is not very useful. That is true. Usually the action attribute is used to send form contents to server pages. So for example we might use a PHP file named process.php. This process.php then will do all the magic with data, like save it to a database, or register you to your favorite event, you name it. PHP is a powerful server scripting language, often used in web development. If you ever used WordPress, probably the data being processed is done via PHP.

**Am I required to use `action` attribute on HTML forms**

Back in HTML4 yes, nowadays with HTML5 you are not required. If you have a form tag without an action attribute then the data will be sent to its own page. 

Why would we do this? Because with the birth of single page applications (SPA), we might want to process our form data using JavaScript or some other framework such as React / Angular. If we use Vanilla JS we often do this by adding eventListeners to listen when the form has been submitted.
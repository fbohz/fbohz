# HTML Form Action

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

Let's now fill out the form:

![Screen Shot 2020-08-02 at 10 18 56 PM](https://user-images.githubusercontent.com/15071636/89143137-25957900-d50f-11ea-9b41-01c6a1f539e7.png)




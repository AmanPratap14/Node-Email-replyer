# Node-Email-Reply

This is the Node.js based app that is able to respond to emails sent to your Gmail mailbox while you’re out on a vacation.

1. The app check for new emails in a given Gmail ID and send them reply,
💡 I have implemented the “Login with google” API for this. 

2. The app will send replies to Emails that have no prior replies. and
💡 The app identify and isolate the email threads in which no prior email has been sent by you.
 This means that the app should only reply to first time email threads sent by others to your mailbox. The email that you send as a reply can have any content you’d like, it doesn’t matter.
 
3. The app will add a Label <VACATION> to the email and move that email to this label.
💡 After sending the reply, the email automatically tagged with a label in Gmail. 

You can name the label anything you Like.
 If the label is not created already, you’ll need to create it. Use Google’s APIs to accomplish this

4. The app repeat this sequence of steps 1-3 in random intervals of 45 to 120 seconds.

I have Google's API, Google Cloud Platform, and Oauth 
https://cloud.google.com/ -  create a new account and create a new Project and then Enable Google.gmail APis and create,  Credentials 

Install required dependencies: Install the necessary libraries and packages to work with Google APIs and manage email interactions. The main dependencies you'll need are googleapis and nodemailer.

Go to the Google Cloud Console (https://console.cloud.google.com/) and sign in with your Google account.

Create a new project:

    Click on the project dropdown at the top of the page and select "New Project".
    Enter a name for your project.
    Optionally, choose an organization or folder to associate with your project.
    Click on the "Create" button.

Enable the Gmail API:

    In the Google Cloud Console, navigate to the "APIs & Services" > "Library" section.
    Search for "Gmail API" and select it from the results.
    Click on the "Enable" button to enable the Gmail API for your project.

Create OAuth 2.0 credentials:

    In the Google Cloud Console, navigate to the "APIs & Services" > "Credentials" section.
    Click on the "Create Credentials" dropdown and select "OAuth client ID".
    Choose the application type as "Web application".
    Enter a name for your OAuth client ID.
    In the "Authorized JavaScript origins" field, add the origin(s) from which your application will be making requests. For example, if you're running your application locally, you can add http://localhost:8000.

    In the "Authorized redirect URIs" field, add the redirect URI(s) where the Google OAuth consent screen will redirect the user after authentication. For example, you can add http://localhost:8000, http://localhost:8080 if that's the route in your application where the callback will be handled.
    Click on the "Create" button.

Obtain the client ID and client secret:

    Once you've created the OAuth client ID, you will see a dialog with the client ID and client secret.
    Make note of these values as they will be needed in your application.

    Configure your application with the credentials:

    In your Node.js application, create a .env file in the root directory.
    Add the following lines to the .env file:

# Creating an extension:

This exercise is a high level overview of how to create an extension for vscode.

A detailed set of instructions can be found here:
[https://code.visualstudio.com/docs/extensions/overview](https://code.visualstudio.com/docs/extensions/overview)


#  You are going to need this:

```
npm install -g yo generator-code vsce
yo code
```

Yeoman will ask a bunch of question, so select "New Extension Pack" and answer the following questions:

> What type of extension do you want to create?  
`New Extension Pack`  
> ? Add the currently installed extensions to the extension pack  
`Yes`  
> ? What's the name of your extension?   
`jeff-extensions`  
> ? What's the identifier of your extension?   
`jeff-extensions`  
> ? What's the description of your extension?   
`Just a sample of extensions I like to use`

# Add your extension

Add this to the package.json file:

```
//change this to yourname, that you will need later
"publisher": "JeffKranenburg", 

//change this to your repo
"repository": "https://github.com/jwknz/test", 
```

Add the extensions you wish to add

# Publish your extension

There is a bit of switching between the browser and the terminal, so hopefully you won't get lost :-)

**Step 1:**
To publish an extension you will need to create an access token

Go to [https://dev.azure.com/](https://dev.azure.com/) and sign in with your microsoft account.

Next, go to the settings menu and create a personal access token.
* Go to settings in the top right under your profile picture
* Select Personal Access Token in the left column and then click on new token.

**Step 2:**

You will need to create a profile and then login using your access token.

1) `vsce create-profile name`
2) `vsce login name` // followed by typing in the access token

Go to the folder that has the package.json file in it and type in `vsce package`.

This will create the **.vsix** file that you will need to upload in the market place.

**Step 3:**

Back in the browser, go to the market place and sign in with your microsoft account (if it isn't already)

[https://marketplace.visualstudio.com/](https://marketplace.visualstudio.com/)

In the top left click on "[Publish Extension](https://marketplace.visualstudio.com/manage)"

You should see the publisher that you created earlier in the left column.

Click on New Extension and select visual studio code and upload the `.vsix` file. You will then be notified when your extension is live. At which point you can download it in visual studio code.

DONE!

My extension is `jeffkranenburg.jeff-extensions` but it was my testing one, so it includes a lot of extensions :-)
# Pug + RevealJS Presentations
This is a Fork of the RevealJS presentation framework. 

## Installing dependencies
First, you need to install the dependencies for this project:
```
npm install
```

## Workflow
In this fork I make presentations in different branches by using the pug templating language. To make a new presentation I create a new branch from my template branch. 
Then I create new files in the `sections` directory to create my presentation.

To build the presentation and view it in the browser run:
```
npm start -- --port 4000
```

The presentation will be available on `localhost:4000` in your browser.

To build the pug files you should have the `pug-cli` tool installed. Now you can run:
```
pug -w index.pug
```
This will watch the pug files for a change and build a new index.html file when a change occurs. Use it without the `-w` flag to only build the file once.

## Using iFrames
By default, your browser will block certain websites that have the x-frame-options header set to SAMEORIGIN. That will now allow the browser to display the site in an iFrame. 
I use a dedicated Google Chrome instance that disables the blocking https://chrome.google.com/webstore/detail/ignore-x-frame-headers/gleekbfjekiniecknbkamfmkohkpodhe.


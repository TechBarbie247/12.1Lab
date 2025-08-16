# The Daily Grind – Express.js Server
## Lab Overview

In this lab, we build a basic Express.js server for a local coffee shop, The Daily Grind. The server will serve two simple web pages:

A homepage (/)

A contact page (/contact)

This is the foundation of the shop’s online presence.

## Learning Objectives

By completing this lab, you will:

Set up a Node.js project and manage dependencies.

Create a basic Express.js server.

Implement routing to handle URL requests.

Serve static HTML files.

## Setup Instructions
1. Project Setup
# Create a new project directory
mkdir daily-grind-server
cd daily-grind-server

# Initialize Node.js project
npm init -y

# Install Express.js
npm install express



## Test the Routes

Visit http://localhost:3000/ → shows homepage

Visit http://localhost:3000/contact → shows contact page

## Reflection Questions

What is the difference between res.send() and res.sendFile()?

Why is the path module necessary when serving files? What could go wrong if you just used a relative path?

How would you add a third page (e.g., a menu page) to this server?

## Resources

Express.js Routing Documentation

Node.js Path Module

## Reflection Question

*What is the difference between res.send() and res.sendFile()?*

res.send() → sends plain text, JSON, or HTML as a string.

res.sendFile() → sends a whole HTML file from disk.

Use res.send() for quick responses, res.sendFile() for serving actual HTML files.

*Why is the path module necessary when serving files?*

It creates an absolute path (works on Windows, Mac, Linux).

If you just used 'public/index.html', it might fail if Node is run from a different folder.

*How would you add a third page (e.g., /menu)?*

Create public/menu.html.

Add a new route in server.js:

app.get('/menu', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'menu.html'));
});


Restart server → visit /menu.
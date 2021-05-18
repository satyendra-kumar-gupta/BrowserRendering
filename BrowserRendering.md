

# Browser Rendering
**How does a Browser render HTML, CSS, JS to DOM,
What is the mechanism behind it?**

### First Need To Understand How Web Browser Work?
The main function of a web browser is to resource from web and display them inside the browser window.
Mostly a browser will request HTML, CSS, JavaScript and image content from a server and decode them 
based on web standards and specification.They follow standards because it allows website to behave the
same way across all browsers, and creates less work for developers.

### What is the internal structure of a web browser?
Please see below image.

![structure of web](https://cutt.ly/tbIKNl9)

1. **Layout Engine** **:** This takes input from the browser (URL bar, search box, mouse clicks and key presses)
   and passes them to the rendering engine
   
2. **Rendering Engine** **:** This takes HTML code and decode into what you see visually. For instance, a tag would 
   be interpreted by the rendering engine as a set of instructions to make the text inside the element bold
   
3. **User Interface** **:** This is the visual presentation of controls in the browser, for instance the back and 
   forward buttons, bookmarks, and all chrome that appears around the main browser window where web pages display.
   
4. **JavaScript Engine** **:** This engine takes JavaScript code, parses it, executes it, and returns the results.
   
5. **Network Layer** **:** This is a function of the browser that happens behind the scenes and handles network. 
   functions such as encryption, http and ftp requests, and all network settings such as timeouts, and the handling. 
   of HTTP status codes.

6. **Storage** **:** Browser’s must store some data which can include cached files, cookies, and recently browsers have updated to be 
   able to store data and objects created with JavaScript.

7. **Operating System Interface** **:** The browser must interact with the operating system to draw out several elements of the page 
   like drop boxes, and the chrome of a window (close, maximize, and minimize buttons).
   
### Lets on Rendering Engine:
The rendering engine has a very important role its display, What you see on your screen.
It communicates with the networking layer of the browser to grab HTML code and other items passed from a remote server.
Then it follows these steps:

![rendering engine](https://www.amsivedigital.com/wp-content/uploads/2014/07/How-Web-Browswers-Work-3.png)

### How To parse HTML And Creating The Dom Tree:

![DOM](https://www.amsivedigital.com/wp-content/uploads/2014/07/How-Web-Browsers-Work-4.png)

HTML is a tree structure that begins with a <html> tag, usually contains a <head> and <body> tag, and elements can be 
nested within elements. These HTML elements are parsed and turned into a **DOM tree** by the rendering engine. 
It is a tree like structure made out of the HTML, where each tag is a branch starting at the root element.

### Render Tree Construction Of CSSOM:
CSS attributes (style attributes) are also parsed and generated **CSSOM tree** and finally combined with the 
DOM tree to create a **render tree**. This is a tree of visual elements such as height/width and color ordered 
in the tree structure, In which they are to be displayed in the browser.

![CSSOM](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/images/cssom-tree.png)

### Main flow Examples
First, The browser combines the DOM and CSSOM into a **render tree**, which captures all the visible DOM content 
on the page and all the CSSOM style information for each node.
##### Some More Point About It:

1. The DOM and CSSOM trees are combined to form the render tree.
2. Render tree contains only the nodes required to render the page.
3. Layout computes the exact position and size of each object.
4. The last step is paint, which takes in the final render tree and renders the pixels to the screen.

![main flow](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/webkitflow.png)

### JavaScript Compilation:
JavaScript is a programming language which allows things to happen inside of the browser and makes 
web pages interactive. Things like popup windows, actions that occur on a button press and elements 
that move across the page are all things done by JavaScript. This means that JavaScript code executes
after the web page has been rendered and painted onto the screen, and when it executes it triggers a 
re-render to account for changes made.

##### Here's a quick recap of the browser's steps:
1. Process HTML markup and build the DOM tree.
2. Process CSS markup and build the CSSOM tree.
3. Combine the DOM and CSSOM into a render tree.
4. Run layout on the render tree to compute geometry of each node.
5. Paint the individual nodes to the screen.

#####Reference:
[Source1](https://www.amsivedigital.com/insights/performance-creative/rendering-a-webpage-with-google-webmaster-tools/#:~:text=The%20rendering%20engine%20has%20a,passed%20from%20a%20remote%20server.)
[Source2](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction)
[Source3](https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work)
[Source4](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)

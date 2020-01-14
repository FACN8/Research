<style>
p {
  font-size: 26px;
}
</style>

---
# <center>DOM Manipulation</center>
![image alt](https://www.kmacims.com.ng/wp-content/uploads/2019/09/the-html-dom-min.png)

---

## What, exactly, is the DOM?

<br>

<p style=" font-size: 35px;">
The Document Object Model, or the “DOM”, is an interface to web pages. It is essentially an API to the page, allowing programs to read and manipulate the page’s content, structure, and styles. Let’s break this down.
</p>

---

## Create & Add  HTML elements to our Webpage
<img src="https://www.kirupa.com/html5/images/DOM_elements_p_element_added_300.png" style="height:500px" width="100%">


---

##### CreateElement method of the document object, Like this:


```javascript=
// Create new HTML element
var paragraph = document.createElement("p"); 

// Add textNode with the new value we want
var text = document.createTextNode("New Text"); 

// Add the text to the element we created
paragraph.appendChild(text);

// Add the element to the section/in the place we want
// In this example we want to add a paragrapgh to the body
documnet.body.appendChild(paragraph);

```
<p>
In between the round brackets of createElement you type the HTML element you want to create. This needs to go inside of quote marks (single or double). We want to create a new paragraph using the P tag. (The HTML element is created with lowercase letters.) We've then assigned the new tag to a variable that we've called newPara.

</P>

---

### Replacing an existing element



Replacing one element with another by use of the cross-browser safe DOM method replaceChild():

![image alt](https://ithelp.ithome.com.tw/upload/images/20171216/20065504njEtKj31Uh.png)

---

## Example
 
 | Original List | Updated List | 
| -------- | -------- |
| Coffe     | Water     |
| Coca Cola     | Coca Cola     | 
| Tea     | Tea     | 
| Milk     | Milk     | 
 
 
```javascript=
var textnode = document.createTextNode("Water");
var item =document.getElementById("myList").childNodes[0];
item.replaceChild(textnode, item.childNodes[0]);
```


---

### HTML | DOM appendChild() Method

<p>
The HTML DOM appendChild() method is used to create and add a text node at the end of the list of child nodes.<br>
 
Using appendChild() we can:<br>
* Add new values to a list.
* Add a new paragraph under another paragraph.
* Add elements to other elements.

```javascript=
NODE.appendChild(Childnode)
```

</p>

---

![node_diagram](https://ithelp.ithome.com.tw/upload/images/20171216/20065504kFU2w5lR4s.png)

---

### HTML DOM insertBefore() Method

The insertBefore() method inserts a node as a child, right before an existing child, which you specify.



```javascript=
  var newItem = document.createElement("LI");
  var textnode = document.createTextNode("Water");
  newItem.appendChild(textnode);

  var list = document.getElementById("myList");
  list.insertBefore(newItem, list.childNodes[0]);
```



---

### What is a JavaScript Event? 

<p>
JavaScript's interaction with HTML is handled through events that occur when the user or the browser manipulates a page.

When the page loads, it is called an event. When the user clicks a button, that click too is an event. Other examples include events like pressing any key, closing a window, resizing a window, etc.

Developers can use these events to execute JavaScript coded responses, which cause buttons to close windows, messages to be displayed to users, data to be validated, and virtually any other type of response imaginable.

a few types of events is : onclick ,onsubmit , onmouseover and onmouseout 
</p>

##### What does event.preventDefault() do and why might you use it?

```javascript= 
document.getElementById("myAnchor").addEventListener("click", function(event){
  event.preventDefault()
});
```

<p>
The preventDefault() method cancels the event if it is cancelable, meaning that the default action that belongs to the event will not occur.

For example, this can be useful when:

<li>
Clicking on a "Submit" button, prevent it from submitting a form
</li>
<li>
Clicking on a link, prevent the link from following the URL
</li>
</p>

---

### What is a NodeList? How is it different from an Array?

<P>
NodeList is an object consisting of a list of all nodes in a page. A NodeList may also consist of all the nodes in a particular selected set of nodes.

```javascript=
var div_nodes = document.getElementsByTagName("div");
```


If there are two div elements in the document, the NodeList (the value of the div_nodes variable here) will contain two nodes. If there are three elements, the NodeList will contain three elements, etc.

NodeLists and Arrays are two different things because NodeLists are actually not a JavaScript API, but a browser API.
NodeLists are a language-agnostic way to access DOM elements, and Arrays are a JavaScript object you can use to contain collections of stuff.
</P>

---

### What are the security concerns around Element.innerHTML?

<p>
It is not uncommon to see innerHTML used to insert text into a web page. There is potential for this to become an attack vector on a site, creating a potential security risk.
</p>

### what could you use instead?
<p>

However, there are ways to execute JavaScript without using <script> elements, so there is still a security risk whenever you use innerHTML to set strings over which you have no control. For example:

```javascript=
const name = "<img src='x' onerror='alert(1)'>";
el.innerHTML = name; // shows the alert
```

For that reason, it is recommended that you do not use innerHTML when inserting plain text; instead, use Node.textContent. This doesn't parse the passed content as HTML, but instead inserts it as raw text.
</p>

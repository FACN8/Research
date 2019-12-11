# CSS With BEM


## What is BEM?

_**BEM stands for:**_
- Block
- Element
- Modifier

_BEM is a methodology that helps us to create reusable code, since CSS is hard to maintain._

### Block

Standalone entity that is meaningful on its own.

- card 
- header 
- footer 
- section 
- container 
- menu 
- Input

### Element

A part of a block that has no standalone meaning and is semantically tied to its block.

- title 
- item 
- list 
- checkbox 
- caption

### Modifier

A flag on a block or element. Use them to change behavior or appearance.
disabled 
highlighted 
checked 
size 
color 
background-color


## Advantages of BEM

**Reusability:**
Composing independent blocks in different ways and reusing them intelligently reduces the amount of CSS code that you will have to maintain.

**Structure:**
BEM methodology gives your CSS code a solid structure that remains simple and easy to understand.

**Modularity:**
Block styles are never dependent on other elements on a page, so you will never experience problems from cascading.

## Let's start with an example, to help you learn more about BEM

If you have an Item component, which includes a Title, picture, Details, price, Order Now button
and more info button.
You're more likely to write the css as the following:
   
.item{}
.item #title {}
.item img {}
.item .detailsContainer{}
.item .detailsContainer #Content{}
.item .buyBar{}
.item .buyBar #price{}
.item .buyBar .buyButton{}
.item .buyBar .viewInfoButton{}

HTML might look something like this


    <div class="item">
            <p id="title">My Title</p>
            <img src="images/image1.jpg">
            <div class="detailsContainer">
                <p id="#Content">My Content</p>
            </div>
            <div class="buyBar">
                <p id="#price"></p>
                <button class="buyButton">Buy</button>
                <button class="viewInfoButton">More info</button>
            </div>
    </div>


BEM suggests that you choose your classes names more wisel. 

**Example:**
the css could look something like this:
.item{}
#item--Title{}
#item__image{}
.item__Details{}
.item__Details--Container{}
#item__Details__Content{}
.item__buyBar__Container{}
.item__buyBar--price{}
.item__buyBar__Button{}
.item__BuyBar__Button--buyButton{}
.item__buyBar__Button--moreInfo{}


As you might see, it's so much clearer now, and easier to modify each section.

If I wanted to change the color of the Buy Button option, I'd know I have to go
to .item__BuyBar__Button--buyButton{}. etc
 
What if the names have gotten way longer than intended?
Don't worry, with css frameworks like SASS, you can shorten the names
by using nested css. But this is another topic for another What if episode.









#HTML5 IN DEPTH

### New Elements
- article
    ```
    This can be found within a main element and tells search engines that the content 
    in this section is the most important compared to other elements in the main element. 
    You can have more than one article element on a page.We can have a blog post here
    ```
- aside
    ```
    This element can be found in the main element. It is used to hold content that are not as relevant as the 
    content in an article element. An example is a sidebar in a printed magazine.
    ```
- audio (JS API's)
    ```
    Plays sound
    ```
- bdi (bidirectional isolated element)
    ```
    Not all words read from left to write. This allows you to add languages that are bidirectional
    ```
- canvas (JS API's)
    ```
    used for drawing on a page.
    ```
- datalist
    ```
    Defines a list of elements that can be shown as options to an input field
    ```
- details
    ```
    No javascript element that adds interactivity to your webpage. Contains a summary element and adds a dropdown feature 
    ```
- embed
    ```
    A host container for external plugins.
    ```
- figcaption
    ```
    Provides semantic meaning to images and diagrams.
    ```
- figure
    ```
    Provides semantic meaning to images and diagrams.
    
    <figure>
        <figcaption>
            Screenshot of a menu
        </figcaption>
        <img src="screenshot.png">
    <figure>
    ```
- footer
    ```
    Indicates to search engines the footer section of a page. This can hold the nav element and copyright information
    ```
- header
    ```
    Indicates to search engines the head section of a page. This usually houses the nav element.
    ```
- main
    ```
    The main element wraps around the main content of a web page. This is to help search engines locate the 
    most important section of a page. Navigation, footer and copyright information should not be placed in this element
    ```
- math
    ```
    Aloows you to define equations and formulas and render them as you would expect them to look on a text book
    ```
- mark
    ```
    Used to wrap text in search results to the matched term
    ```
- meter
    ```
    Used to indicate a value within a threshold of values. Can be used for product ratings
    ```
- nav
    ```
    This element is used within a header element to indicates the navigation links (site navigation) of a page. eg contact, about us etc
    It hold links to pages within the site not external links. These links can be within the header but outside the nav element.
    ```
- output
    ```
    Contains the result of a calculation
    ```
- progress
    ```
    Indicates how far you are in a process
    ```
- section
    ```
    This element is used to logically group related content, not for visual purposes. This is how divs are used in most scenarios.
    ```
- source
- summary
    ```
    Used with a details element to provide summary information
    ```
- svg
- time
    ```
    Helps you identify a point in time. you can specify just the time, the date or a specific datetime. 
    It has an optional pubdate attribute which can be present on a single time attribute per page. It acts as the timestamp for the 
    publication of the webpage

    <time date="2019-08-12" pubdate>
        August 13, 2019
    </time>
    ```
- track
    ```
    Can be used within a video or sound element to define supported files, labels etc 
    ```
- video (JS API's)
    ```
    Plays videos
    ```
- wbr (word break element)
    ```
    If you have a really long word the wbr element can come in handy. It tells a browser where to hyphenate a word
    when wrapping is required
    ```


### Example HTML5
```
<html>
    <body>
        <header>
            <nav></nav>
        </header>
        <main>
            <article>
                <section>...</section>
                <aside>...</aside>
            </article>
        </main>
        <footer>
            <nav></nav>
        </footer>
    </body>
</html>
```

### JAVSCRIPT API's
* Graphics & Typography
    - Canvas 
        ```
        Gives you full control to draw on an html page
        ```
    - Web Animations

* Interaction, Events, Messaging
    - Battery Status
    - Clipboard Api & Events
    - Cross Document Messaging Api
    - Device & Screen Orientation (Mobile)
    - Fullscreen
    - Geolocation Api
    - Media Capture  
    - Notifications
    - Vibration

* Storage & Files
    - File Api
    - File Reader
    - Blob Url's
    - IndexedDB (For large sets of data that need to be stored on the client)
    - Local Storage (For small data sets)

* Real Time Communication
    - Push Api (Push data from server to client)
    - Server-Sent Events (One Way using http)
    - Web Sockets (Two way - custom communication)

* Web Components
    - Custom Elements
    - Shadow Dom
    - Templates

* Performance Optimization & Analysis
    - High Resolution Time (Ability to measure time accurately)
    - Navigation Timing (Measuring page load time) 
    - Page Visibility (If you want your page to behave differently when not the active tab eg pause music)
    - User Timing
    - Web Workers (Use different threads in the browser)

* Security & Privacy
    - Content Security Policy
    - Referrer Policy
    - Web Cryptography

* Miscellaneous Features
    - scripts: async & defer (alllows your scripts to run in an asynchronous manner to prevent blocking page)
    - contentEditable
    - drag and drop
    - History
    - Promises
    - Service Workers (Replaces the previous application cache Api) Helps if you need your site to work offline

### Mordinizr
A Javascript library that helps you detect browser support for HTML5 features when developing web applications.
This helps in giving the end user feedback so they know why they may be facing specific issues rendering pages

### Fallback & Polyfills
* Fallback - A third party implementation of an HTML5 api. The api's these provide are different compared to what is 
provided by HTML5 but you get the same functionality

* Polyfill - It is meant to replicate the same interface and functionality provided by an HTML5 api. You can simply 
remove a polyfill once there is browser support for a specific feature. Requires regirous testing though to switch safely


### Selection Api
* getElementByClassName - This was pretty difficult to achieve before the HTML5 selection API. 
                            Using this function, you always get a LIVE result at to the current state of the DOM

```
document.getElementsByClassName('img-responsive');

OUTPUT
HTMLCollection(3) [img.img-responsive, img.thumbnail.img-responsive.push-down-top, img.img-responsive]
```

* querySelector - If you want to use a css3 selector [.,#]. Where you element is not selectable using a class or element 
                    Returns the first item found . Results returned are static

```
document.querySelector('.img-responsive');

OUTPUT
img.img-responsive
```

* querySelectorAll - Returns all found items in the dom. It always returns an array even when there is a single match 
                    The results returned are static

```
document.querySelectorAll('.img-responsive');

OUTPUT
NodeList(3) [img.img-responsive, img.thumbnail.img-responsive.push-down-top, img.img-responsive]

document.querySelectorAll('#example-container list:first-child');

OUPUT
NodeList []
```

NB: You cant treat a NodeList array like a regular Javascript array

ITERATE USING A FOR LOOP
```
var items = document.querySelectorAll('#example-container li');

for(i=0; i < items.length; i++) {	
	console.log(items[i].innerText);
}

OUTPUT
Luxurious sized master suite
VM2181:2 Oversized walk-in closet
VM2181:2 Frameless Beech cabinetry with concealed hinges
VM2181:2 Elegant slab white quartz countertops with large backsplash
VM2181:2 Dual china sinks with Moen faucets
VM2181:2 Clear frameless shower enclosures
```

ITERATE USING THE ARRAY PROTOYPE
```
var foreach = Array.prototype.forEach;

var items = document.querySelectorAll('#example-container li');

foreach.call(items, function(item){
	console.log(item.innerText);
});

OUTPUT
Luxurious sized master suite
VM2181:2 Oversized walk-in closet
VM2181:2 Frameless Beech cabinetry with concealed hinges
VM2181:2 Elegant slab white quartz countertops with large backsplash
VM2181:2 Dual china sinks with Moen faucets
VM2181:2 Clear frameless shower enclosures
```

### GETELEMENTBYCLASSNAME DYNAMIC RESPONSE EXPERIMENT
```
var dome = document.querySelector("#example-container ul"); //Get dome item
var domeLiList = document.getElementsByClassName("feature"); // Get all li elements within dome ul element and log the length, 
console.log(domeLiList.length);
OUTPUT
7

var el = document.createElement('LI');
el.className = "feature";
el.innerText = "Do the dance";
dome.appendChild(el);

console.log(domeLiList.length);
OUTPUT
8
```
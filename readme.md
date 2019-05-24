#HTML5 IN DEPTH

## New Elements
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


## Example HTML5
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

## JAVSCRIPT API's
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

## Mordinizr
A Javascript library that helps you detect browser support for HTML5 features when developing web applications.
This helps in giving the end user feedback so they know why they may be facing specific issues rendering pages

## Fallback & Polyfills
* Fallback - A third party implementation of an HTML5 api. The api's these provide are different compared to what is 
provided by HTML5 but you get the same functionality

* Polyfill - It is meant to replicate the same interface and functionality provided by an HTML5 api. You can simply 
remove a polyfill once there is browser support for a specific feature. Requires regirous testing though to switch safely


## Selection Api
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

## GETELEMENTBYCLASSNAME DYNAMIC RESPONSE EXPERIMENT
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

## HTML5 NEW INPUT ELEMENTS
* color
    - Enables a color picker. Allows for customizations
    ```
        <input type="color" />
    ```
* datalist
    - By default it doesnt display anything on a page unless combined with an input with the list option set to the id of the datalist
    ```
        <input list="colors" />
        <datalist id="colors">
            <option value="Blue">
            <option value="Red">
            <option value="Yellow">
        </datalist>
    ``` 
* date
    - provides a datepicker for easy date selection. Rendered differently by browsers.
    ```
        <input type="date">
    ```
* datetime
    - provides a datepicker for easy date and time selection. Rendered differently by browsers.
    ```
        <input type="datetime">
    ```
* datetime-local
    - provides a datepicker for easy date and time selection using your local time. Rendered differently by browsers.
    ```
        <input type="datetime-local">
    ```
* email
    - provides an email input option. Helps display email inputs on a keyboard for mobile devices
    ```
        <input type="email" />
    ```
* month
    - provides a month date picker.
    ```
        <input type="month" />
    ```
* number 
    - provides a number selection with the help of a spinner.
        ```
            <input type="number">
        ```
* range
    - renders a slider, giving you control over start, stop and step values
        ```
            <input type="range">
        ```
* search
    - Looks like a regular text input with a x to clear the search term.
        ```
            <input type="search" />
        ```
* tel
    - provides a tel input option. Helps display phone inputs on a keyboard for mobile devices
    ```
        <input type="tel" />
    ```
* time
    - provides a time picker. It comes with a custom mobile visualization
        ```
            <input type="month" />
        ```
* url
    - provides a url input option. Helps display url inputs on a keyboard for mobile devices
    ```
        <input type="url" />
    ```
* week
    - provides a week date picker.
        ```
            <input type="week" />
        ```

## Form Validation

* Value Missing
    - If an element with the required attribute has the value attribute empty, this is set to true
    ```
        <input type="text" value="" required>
    ```
* Type Mismatch
    - If the value of an element does not match the type of the element, this is set to true
    ```
        <input type="url" value="hello" />
    ```
* Pattern Mismatch
    - If the value of an element does not match the regular expression provided in the pattern
    ```
        <input type="text" pattern="/^[A-z]+$/" value="123">
    ```
* Too Long
    - Evaluates to true when an elements length is longer than the value in the maxLength attribute
    ```
        <input type="text" maxLength="3" value="hello" />
    ```
* Range Underflow
    - Returns true when the ranges value is smaller than the minimum allowed value defined by the min attribute
    ```
        <input type="range" min="3" max="5" value="0"/>
    ```
* Range Overflow
    - Returns true when the ranges value is greater than the maximum allowed value defined by the max attribute
    ```
        <input type="range" min="3" max="5" value="9"/>
    ```
* Step Mismatch
    - Returns true when a range type input's value is impossible given the step value
    ```
        <input type="range" min="5" max="25" step="5" value="8"/>
    ```
* Valid 
    - Returns true when all other validation rules return false. This is how you know you have a valid form on the page
    ```
        <input type="range" min="5" max="20" step="5" value="10">
    ```

## Attributes
* Autofocus
    - Can be applied to a single input element on a page. Moves the cursor to that input on page reload
* Placeholer
    - Set a hint on the type of information that goes into an input. Reduces the need for labels

## Custom Attributes
* You can add custom attributes using the data-attribute_name syntax. This allows us to access the elements attribute value in javascript  


## Validation With HTML5 Inputs & CSS Pseudo Classes Demo
```
    <input type="text" id="username" name="username" pattern="[a-zA-Z ]{5,}" placeholder="username" maxlength="30" required/>
    <div class="invalid">
        The required username may only be a series of alphabetical characters
    </div>

    <input type="email" id="email" name="email" placeholder="email" required />
    <div class="invalid">
        The required email address may not include any special characters other than '.' or '@'.
    </div>

    <style>
        input:valid + .invalid { /* adjacent sibling selector: look for an element next to the input with class invalid*/ 
            visibility: hidden;
        }

        input:invalid + .invalid {
            visibility: visible;
        }

        input:required {
            border-bottom: 2px solid #c33;
        }

        input:valid {
            border-bottom: transparent;
        }

        .invalid {
            color: #999;
        }
    </style>
```

## HTML5 MEDIA
* Media Elements
    - Audio / Video tags
    - Media Types
    - Speech Api

* Audio
    - WAV, MP3, MP4, OGG

* Video
    - Theora, H.264 (MP4), HEVC (MP4), VP8 (WebM), VP9 (WebM)

NB: Serve your media with the matching content type, varies for each media format

```
    You can preload video/audio as server loads depending on your server setup [auto, meta, none]

    <video controls loop preload="auto" poster="img/kitchen.png">
        <source src="media/hello.mp4">
        <source src="media/hello.ogv">
        <source src="media/hello.webm">
        <p>The browser does not support native video</p>
    </video>

    <audio controls loop>
        <source src="media/hello.mp3">
        <source src="media/hello.ogg">
        <source src="media/hello.wav">
        <p>The browser does not support native video</p>
    </audio>
```

## HTML5 Canvas

# Welcome to my simple project

## Table of content:

[Let's create some visual buttons](#lets-create-some-visual-buttons)

[HTML base code:](#html-base-code)

[Script tag](#script-tag)

[CSS](#css)

[Useful links](#useful-links)

# Let's create some visual buttons

I will play around with HTML and CSS to create some buttons that when you hover over them they will display a video.

I made use of a simple tag: `<button>`.

Inside it I added the `<video>` tag and I added some inline style to it as well.

[Back to top](#)

# HTML base code:

### The code looks like this:

```html:
<button id="hello-everyone">
  Hello, everyone!
  <video
    id="hello"
    src="./hello.mov"
    style="border: 3px solid; width: 0; display: none"
  ></video>
</button>
```

The video has a **src** attribute with the video path as value. In the inline style, I have told the video element to display nothing on the browser.

The **button** has **id** with value of <i>hello-world</i> and the video has an **id** with the value of <i>hello</i>

[Back to top](#)

# Script tag

In my HTML file, below the `<body>` tag, I added a `<script>` tag in order to add some JavaScript magic.

I created a new constant called <i>helloPlayer</i> and made use of <b>document.querySelector('#hello')</b> and **hello** is the id from the video. This way I select the video specifically.

### The code looks like this:

```javascript:
const helloPlayer = document.querySelector('#hello');
```

Then I created another constant called <i>helloHover</i> to select the button by its <b>id</b>.

Then I made use of <b><i>addEventListener()</i></b>. The first argument I gave it was a string with the value of <b>'click'</b> so that the event happens only on click, then a function with the following body content:

| What the function receives          | What it does                                         |
| ----------------------------------- | ---------------------------------------------------- |
| helloPlayer.play()                  | To play the video                                    |
| helloPlayer.style.display = 'block' | To display the video element                         |
| helloPlayer.style.width = '550px'   | To change the width to "550px"                       |
| console.log('Hello, everyone!')     | To display message "Hello, everyone!" in the console |

The **setTimeout()** function that is also inside the event listener is receiving a function and an interval. Inside the function I sent same functions that change the value of the width and make the element dissapear and the interval differs depending on each video I used.

I tried my best to match the interval the audio finishes.

### The code looks like this:

```javascript:
const helloHover = document.querySelector('#hello-everyone');

helloHover.addEventListener('click', () => {
  helloPlayer.play();
  helloPlayer.style.display = 'block';
  helloPlayer.style.width = '550px';

  setTimeout(() => {
    helloPlayer.style.display = 'none';
    helloPlayer.style.width = '0';
  }, 1000);

  console.log('Hello, everyone!');

});
```

# CSS

I wanted to do the style in two ways:

- inline (the one I presented above)
  and
- internal

### Internal CSS

I have included as well just a little bit of style to those buttons inside a `<style>` tag.

### The code looks like this:

```html:
<style>
  button {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    padding: 0.5rem;
    gap: 1rem;
  }
</style>
```

# Useful links

I did a bit of research as well. Check out these useful links:

[setTimeout()](https://www.w3schools.com/jsref/met_win_settimeout.asp)

[prop style visibility](https://www.w3schools.com/jsref/prop_style_visibility.asp)

[video hidden property](https://www.google.com/search?q=video+hidden+property)

[javascript video play](https://www.tutorialspoint.com/how-to-use-javascript-to-play-a-video-on-mouse-hover-and-pause-on-mouseout)

[javascript video end](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ended_eventst)

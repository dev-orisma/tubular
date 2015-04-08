tubular
=======

Tubular is a jQuery plugin that lets you set a YouTube video as your page background. Just attach it to your page wrapper element, set some options, and you're on your way.

```javascript
$(page content wrapper element).tubular(options);
```

###A word of caution
Tubular does not design your website for you. It works here thanks to alpha transparency on these gray boxes and the png logo on the top left. I built tubular thinking it would help experienced web designers and developers add some subtle background elements — emphasis on subtle — to their work. I'm sure there are some tasteful ways to use tubular and many, many more not so tasteful ways to use it. With great power comes great responsibility. The kitten example above is not to be taken seriously!

##Requirements
Usage is straightforward and requires JavaScript on the client's browser to work. Tubular is a jQuery plugin and therefore relies on jQuery. You will need to know the YouTube ID of the video you want to use as well as the container DIV of your web page.

Please note, tubular must be deployed on a web server to function. The YouTube player will not work when loaded into your browser from your machine.

##Instructions

1.Load the jQuery core on your page. Something like
```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.8.0/jquery.min.js" type="text/javascript"></script>
```
  jQuery must appear BEFORE tubular in your HTML document. 

2.Load the tubular plugin. tubular must be called AFTER the previous two calls. 
```html
<script type="text/javascript" charset="utf-8" src="js/jquery.tubular.1.0.js"></script> 
```

3.Call tubular on your wrapper div, the outermost containing div below the BODY tag. This must be performed within your `$(document).ready()` function. Ideally, you will make the call in an external JavaScript file, but you may use it in a SCRIPT block or even inline
```javascript
$().ready(function() {
    $('#wrapper').tubular({videoId: 'idOfYourVideo'}); // where idOfYourVideo is the YouTube ID.
});
```

Please note that tubular will change the structure of your CSS. Your wrapper DIV will become position: relative and `z-index: 99`. The z-index value is configurable. See the docs for details. Two DIVS, tubular-container and tubular-shield will be created at z-index: 1 and 2 respectively with position: fixed for the video and an empty DIV above it to prevent accidental clickthroughs to YouTube. 

Options and defaults
======


    ratio: 16/9 // usually either 4/3 or 16/9 -- tweak as needed
    videoId: 'ZCAnLxRvNNc' // toy robot in space is a good default, no?
    mute: true
    repeat: true
    width: $(window).width() // no need to override
    wrapperZIndex: 99
    playButtonClass: 'tubular-play'
    pauseButtonClass: 'tubular-pause'
    muteButtonClass: 'tubular-mute'
    volumeUpClass: 'tubular-volume-up'
    volumeDownClass: 'tubular-volume-down'
    increaseVolumeBy: 10 // increment value; volume range is 1-100
    start: 0 // starting position in seconds


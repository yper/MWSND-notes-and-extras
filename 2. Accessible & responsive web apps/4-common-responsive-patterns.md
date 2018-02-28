# Common responsive patterns

*Walk through the most popular responsive layout patterns and learn the tools needed to implement them in your own designs.* 

4 most used patterns:
- Mostly fluid
- Layout shifter
- Column drop
- Off canvas

In some cases a page uses a combination of those patterns.

## Column drop
Probably the easiest. At the smallest size, all elements are stacked. When the viewport width expands and a breakpoint is encountered, elements are positioned next to eachother. At a certain point, columns reach their maximum width. When viewport width increases, left and right margin is added.

```html
<div class="container">
    <div class="box dark_blue"></div>
    <div class="box light_blue"></div>
    <div class="box green"></div>
</div>
```

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
.box {
    width: 100%;    // stacked layout
}

@media screen and (min-width: 450px) {
    .dark_blue {
        width: 25%;
    }
    .light_blue {
        width: 75%;
    }
}

@media screen and (min-width: 550px) {
    .dark_blue, .green {
        width: 25%;
    }
    .light_blue {
        width: 50%;
    }
}

```
## Mostly fluid
This is much alike the column drop pattern, but it tends to be more grid-like, with more columns and columns fitting in different ways, depending on the viewport width.  
On the smallest view, elements are stacked. As the layout gets wider, the grid pattern start to appear. Once the maximum width of the elements is reached, side margins are added to avoid the elements from stretching any further.

```html
<div class="container">
    <div class="box dark_blue"></div>
    <div class="box light_blue"></div>
    <div class="box red"></div>
    <div class="box orange"></div>
</div>
```

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
.box {
    width: 100%;    // stacked layout
}

@media screen and (min-width: 450px) {
    .light_blue, .green {
        width: 50%;
    }
}

@media screen and (min-width: 550px) {
    .dark_blue, .light_blue {
        width: 50%;
    }
    .green, .red, .orange {
        width: 33.333333%;
    }
}

@media screen and (min-width: 700px) {
    .container {
        width: 700px;
        margin-left: auto;
        margin-right: auto;
    }
}

```

## Layout shifter
Probably the most responsive pattern with multiple breakpoints across several different screen widths, but instead of reflowing elements like in the other patters, elements positions change. The `order` CSS attribute can be used to make a page responsive in this way. It requires more planning to maintain because there are more changes to be taken care of after each breakpoint is taken.  

```html
<div class="container">
    <div class="box dark_blue"></div>
    <div class="container" id="container2">
       <div class="box light_blue"></div>
        <div class="box green"></div>
    </div>
    <div class="box red"></div>
</div>
```
```css
.container {
    width: 100%;    
    // container needs to be
    // full width as well now
    display: flex;
    flex-wrap: wrap;
}
.box {
    width: 100%;    // stacked layout
}

@media screen and (min-width: 500px) {
    .dark_blue {
        width: 50%;
    }
    #container2 {
        width: 50%
    }
}
@media screen and (min-width: 600px) {
    .dark_blue {
        width: 25px;
        order: 1;
    }
    #container {
        width: 50%;
    }
    .red {
        width: 25%;
        order: -1;
    }
}
```

The default `order` value is 0.

## Off canvas
Instead of stacking, the off canvas pattern puts less frequently used content (like a navigational menu) off screen. It is only visible when the user explicitly chooses so (eg. by tapping the hamburger icon) or when the screen is large enough.


```javascript
menu.addEventListener('click', function(e) {
  drawer.classList.toggle('open');
  e.stopPropagation();
});
```

```css
nav {
  width: 300px;
  position: absolute;
  /* This trasform moves the drawer off canvas. */
  -webkit-transform: translate(-300px, 0);
  transform: translate(-300px, 0);
  /* Optionally, we animate the drawer. */
  transition: transform 0.3s ease;
}
nav.open {
  -webkit-transform: translate(0, 0);
  transform: translate(0, 0);
}
```

Udacity's live version of the off canvas demo is on [this GitHub repository](http://udacity.github.io/RWDF-samples/Lesson4/patterns/off-canvas.html).
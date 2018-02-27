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


## Off canvas


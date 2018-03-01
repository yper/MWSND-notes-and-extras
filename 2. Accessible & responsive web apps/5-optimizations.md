# Optimizations
*Learn how to optimize images, tables, and fonts to make for the best responsive layouts.*

## Images
Image sources  
Picture element uses media queries to select which image to use.

> [Responsive images course on Udacity](https://www.udacity.com/course/responsive-images--ud882)  
> [More on responsive images with Google's Web Fundamentals](https://developers.google.com/web/fundamentals/media/images/)   

## Tables
Tables with multiple columns tend to overflow the width of the viewport. There are 3 solutions for this problem covered in this course: **hidden columns**, **no more tables** and **contained tables**.

### Hidden columns
Based on their importance, columns get hidden on smaller viewports. Biggest problem is that you're hiding content from the user, so use it with caution.

```html
<table>
    <tr>
        <td>
            <span class="shortName">TOR</span>
            <span class="longName">Toronto Blue Jays</span>
        </td>
        <td class="inning">0</td>
        <td class="inning">0</td>
        <td class="inning">0</td>
        <td class="inning">4</td>
        <td class="inning">0</td>
        <td class="inning">1</td>
        <td class="inning">0</td>
        <td class="inning">0</td>
        <td class="inning">0</td>
        <td class="final">5</td>
    </tr>
</table>
```

```css
.longName, .inning {
    display: none;
}

@media screen and (min-width: 450px) {
    .longname, .inning {
        display: block;
    }
    .shortName {
        display: none;
    }
}
```

### No more tables
Table collapses in small viewports. All columns become rows.

### Contained scrolling
Put the entire table in a `div` with 100% width. Table will be horizontally scrollable.

## Fonts
Ideal measure: 65 characters per line.  
At least 16px font size and 1.2em line height. Text heavy sites can even use 18px font size and 1.25em line height. 14px is too small.

## Minor breakpoints
Breakpoints to make some smaller changes in a layout, like changing font size.
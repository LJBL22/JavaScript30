# 05 Flex Panels Image Gallery: [DEMO](https://ljbl22.github.io/JavaScript30/05_flex_panel_gallery/)

![result](./screenshot.png)
![result](./screenshot-open.png)

### Codes

```JS
// method 2: different from Wes Bros, Open a new panel while closing the previous one
      let currentOpenPanel = null; // declare a variable to preserve the current panel

      function toggleOpen() {
        if (currentOpenPanel === this) {
          // click the one which was opened
          this.classList.remove('open'); // close that panel
          currentOpenPanel = null; // reset
        } else {
          if (currentOpenPanel) {
            // true = the other panel was opened
            currentOpenPanel.classList.remove('open'); // // close that panel
          }

          this.classList.add('open'); // open the panel
          currentOpenPanel = this; // and preserve it to variable
        }
      }
```

```css
.panel {
  /* ... */
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-around; /* difference */
}

.panel.open {
  /* ... */
  flex: 5; /*expand the panel*/
}

.panel > *:first-child {
  /* use * to choose any tag but first-child (no matter it's <p> or <div> ...*/
  transform: translateY(-100%);
}
```

## :writing_hand: Highlights

- Quote from [geeksforgeeks](https://www.geeksforgeeks.org/what-is-the-use-of-asterisk-selector-in-css/)

  > The asterisk (\*) is known as the CSS universal selectors. It can be used to select any and all types of elements in an HTML page. The asterisk can also be followed by a selector while using to select a child object. This selector is useful when we want to select all the elements on the page.

- by `console.log` it seems that safari has the same flex-grow e.propertyName as other browsers now, so I deleted Wes Bros' comments
  > ~~/_ Safari transitionend event.propertyName === flex _/
  > /_ Chrome + FF transitionend event.propertyName === flex-grow _/~~

## :page_facing_up: reference and discussion

- Universal selector [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)

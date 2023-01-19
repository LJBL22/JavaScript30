# 02 JS and CSS Clock :woman_juggling: [DEMO](https://ljbl22.github.io/JavaScript30/02_js-css-clock/)

![clock](./screenshot.png)

### Codes

```JavaScript
 const secondHand = document.querySelector(".second-hand");
      const minHand = document.querySelector(".min-hand");
      const hourHand = document.querySelector(".hour-hand");

      function setClock() {
        const now = new Date();
        const seconds = now.getSeconds();
        const secondDegrees = (seconds / 60) * 360;
        secondHand.style.transform = `rotate(${secondDegrees}deg)`;
        // console.log(seconds);

        const mins = now.getMinutes();
        const minDegrees = (mins / 60) * 360 + (seconds / 60) * 6;
        minHand.style.transform = `rotate(${minDegrees}deg)`;

        const hours = now.getHours();
        const hourDegrees = (hours / 12) * 360 + (mins / 60) * 30;
        hourHand.style.transform = `rotate(${hourDegrees}deg)`;
      }

      setInterval(setClock, 1000);

      setDate();
```

## :writing_hand: Highlights

### Process:

- **function constructor**: by using `new` (the operator) to create a inheritance function,
- `Date()` related web API, including `getSeconds`, `getMinutes`, `getHours`
- Difference between `setInterval`, `setTimeout`, `keyAnimationFrames`:
- The addition degrees:
  ![degree](./degree.png)

## :page_facing_up: reference and discussion

- [[ Alex 宅幹嘛 ] 👨‍💻 深入淺出 Javascript30 快速導覽：Day 2：CSS + JS Clock](https://www.youtube.com/watch?v=O1YsB3qxO4g)
- [HanaHina](https://codepen.io/hanahina/pen/yrPWaW)'s work: using border-width to create triangle hands, making time-pins.

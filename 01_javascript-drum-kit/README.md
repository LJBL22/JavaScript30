# 01_javascript-drum-kit

![console](./screenshot_finished.png)

Here are some of my highlights:

- listen to **window** by the action "keydown"
- use **{keyCode}** to replace `event.keyCode`
- use 2 skills here:
  ```JavaScript
    (`.key[data-key="${keyCode}"]`)
  ```
  1. attribute selector (which I never thought can be used in DOM, but yes, why not?)
  2. literal template
  - [key code](https://www.toptal.com/developers/keycode) website
- video rewind from the beginning
  ```
  HTMLMediaElement.currentTime = 0
  ```
- listen to each key when 'the event' end. And `transitionend` is the event we are looking for.

---

## ❓ A Question Regarding

`if (propertyName !== "transform") return;`

### 1. Original purpose:

```CSS
transition: all 0.07s ease;
```

- By setting up `"all"` here, when the class `"playing"` was added, transition applied to all the properties in `"playing"`, including four border-color, transform and box-shadow; which means all six properties will fire the `transitionend` event.

- In my understanding, Wes would like to prevent these six events from _lowering the performance_. (Please correct me if I am wrong.)

### 2. problems

- Yet it causes a small problem, I noticed that when you hold the key for more than the transition time (which is 0.7s in this case), the class "playing" would never be removed. But if you remove the line `if (propertyName !== "transform") return;`, problem solved.

- Here is a [discussion](https://stackoverflow.com/questions/43794891/remove-class-on-keypress-after-key-hold-transitionend-weird-behavior) about this behavior. All three answers are useful.

  - by delete this line
  - by setTimeout
  - by adding keyup listener

- However, when I tried to explain why this line makes the transition event of transform never happen, which cause the behavior of `transitionend` event vanish, it's hard for me to explain. After spending more than eight hours googling, I still cannot figure out why. Every explanation just doesn't seem right.

- I also tried to console.log to see what happen when it return.
  ![console](./screenshot_consolelog.png). You can see in the last two parts, I guess it is the key, yet hard to explain.

- I also checked MDN and see this notes, yet I think in this case, once you hold the key over .7s, the transition was not even start, so it was not related the completion behavior.

  > Note: The transitionend event doesn't fire if the transition is aborted before the transition is completed because either the element is made display: none or the animating property's value is changed.

SO... I guess I have to leave this question here, or ask the universe for further solution.

## reference and discussion

- discussion on (https://stackoverflow.com/questions/43794891/remove-class-on-keypress-after-key-hold-transitionend-weird-behavior)

- transtionend was not fired [stackoverflow](https://stackoverflow.com/questions/17939290/for-javascript-or-jquery-how-to-make-transitionend-event-not-fire)

- [event reference](https://developer.mozilla.org/en-US/docs/Web/Events)
- [[css-transitions] why doesn't transitionend event fire in some cases?](https://github.com/w3c/csswg-drafts/issues/3043)
- transition [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
- Using CSS transition [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
- it should be related useful in other cases (can not be neglected) [中文](https://medium.com/icguanyu/day5-flex-panels-d3ac7ba5b992)
- another JS30 #1 video in [Chinese](https://www.youtube.com/watch?v=f2ttaeDHzwE)

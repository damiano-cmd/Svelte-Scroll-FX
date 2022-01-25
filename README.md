# Svelte_Scroll_FX

There are element that you can import to use in you website for scroll animations.

There is only one element curently.

```
  <script>
    import {ScrollShow} from "ssfx";
  </script>
```

ScrollShow hase a few attributes:
  - animation - enter the global css keyframes animation you want to use along with other animation functions like: duration, easeing, daley, etc... 
    ```
      <ScrollShow animation="keyframename 1s ease-in" />
    ```
  - fromTopShowAtPercent - a number that determans at witch persentage from top of screen to show the animation.
    ```
      // Show the animation as soon as the animated element enter the screen.
      <ScrollShow animation="keyframename 1s ease-in" fromTopShowAtPercent={100} />

      // Show the element anim. as soon as it reaches half way on the screen 
      <ScrollShow animation="keyframename 1s ease-in" fromTopShowAtPercent={50} />
    ```
  - fromTopHideAtPercent - this is simular as fromTopShowAtPercent but it determan the persentage at witch to reset the element anim to be played again.
    ```
      // resets the element anim as soon as it exits on the bottom of the screen.
      <ScrollShow animation="keyframename 1s ease-in" fromTopShowAtPercent={50} fromTopHideAtPercent={100} />
    ```
  
  - defaultStyle - the default style attrib. value that the element return to after the anim is reset. The default is `opacity: 0;`

  - animate_just_once - if this value is set the fromTopHideAtPercent attrib. is no loger needed and the element animation wont reset after exiting the screen and it will play only once.
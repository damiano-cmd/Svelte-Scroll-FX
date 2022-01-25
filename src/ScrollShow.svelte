<script>
  export let animation = "";

  export let fromTopShowAtPercent = 100;
  export let fromTopHideAtPercent = 100;

  export let defaultStyle = "opacity: 0;";
  export let animate_just_once = false;

  export let animateFromBottom = true;
  export let animateFromTop = false;

  let element;
  let style = defaultStyle;
</script>

<svelte:window on:scroll={(e) => {
  if (element.offsetTop < window.scrollY+(window.innerHeight*(fromTopShowAtPercent/100))) {
    style = `position: relative; animation: ${animation};`;
  }
  if (
      (element.offsetTop > window.scrollY+(window.innerHeight*(fromTopHideAtPercent/100))) 
      && 
      animate_just_once == false
    ) 
  {
    style = defaultStyle;
  }
}} />

<div bind:this={element} style={style} >
  <slot></slot>
</div>
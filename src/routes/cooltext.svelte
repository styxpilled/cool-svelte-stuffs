<script>
  let show = false;

  function swipeColor(node, params) {
    const { duration, delay, easing } = params || {};
    const { color } = window.getComputedStyle(node);
    return {
      duration,
      delay,
      easing,
      css(t) {
        if (t > 0.5) {
          // transform t from range [0.5, 1] into percentage [0, 100]
          // t: 0.5 -> 1
          // u: 0 -> 0.5
          const u = t - 0.5;
          // percentage: 0 -> 100
          const percentage = u * 200;
          return `background: linear-gradient(to right, transparent 0, ${percentage}%, ${color} ${percentage}%); color: ${color}`;
        } else {
          // transform t from range [0, 0.5] into percentage [0, 100]
          // t: 0 -> 0.5
          // percentage: 0 -> 100
          const percentage = t * 200;
          return `background: linear-gradient(to right, ${color} 0, ${percentage}%, transparent ${percentage}%); color: transparent`;
        }
      },
    };
  }
</script>

<div>
  <label>
    <input bind:checked={show} type="checkbox" /> Show
  </label>
</div>

{#if show}
  <div>
    <span style="color: #ff3e00;" transition:swipeColor>Hello world</span>
  </div>
  <div>
    <span style="color: #f080ea;" transition:swipeColor={{ delay: 300 }}
      >Custom Transitions!</span
    >
  </div>
  <br />
  <div>
    <span style="color: #fff430;" transition:swipeColor={{ delay: 600 }}
      >you can make cool things with them</span
    >
  </div>
  <div>
    <span style="color: #fff;" transition:swipeColor={{ delay: 600 }}
      >like a cool flag :></span
    >
  </div>
  <div>
    <span style="color: #9c59d1;" transition:swipeColor={{ delay: 600 }}
      >that matches the text colour</span
    >
  </div>
  <div>
    <span style="color: #000;" transition:swipeColor={{ delay: 600 }}
      >black doesn't look great on this background</span
    >
  </div>
{/if}

<style lang="postcss">
  @import "variables.pcss";

  span {
    font-size: 20px;
  }
</style>

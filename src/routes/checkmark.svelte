<script>
  import { quintOut } from "svelte/easing";
  import { fade, draw, scale } from "svelte/transition";
  import { expand } from "$lib/checkmark-transition.js";

  let visible = true;
  let test = true;
</script>

<label>
  <input type="checkbox" bind:checked={visible} />
  toggle me
  <input type="checkbox" bind:checked={test} />
  dont toggle me!
</label>

{#if visible}
  <div class="wrapper">
    <svg
      out:scale={{ duration: 500 }}
      xmlns="http: //www.w3.org/2000/svg"
      id="svg5046"
      version="1.1"
      viewBox="0 0 50 50"
      height="50mm"
      width="50mm"
    >
      <defs id="defs5040" />
      <g style="display: inline;" id="background">
        <circle
          in:expand={{ duration: 1000, delay: 800, easing: quintOut }}
          r="12.111837"
          cy="272"
          cx="25"
          id="path5042"
          class="bg"
          transform="translate(0,-247)"
        />
      </g>
      <g style="display: inline;" transform="translate(0,-247)" id="draw-line">
        <path
          in:draw={{ duration: 800 }}
          d="m 18.963249,271.54142 5.11928,5.88254 16.621216,-13.3733 c -4.624996,-7.33644 -9.696966,-10.5123 -18.398843,-9.418 -9.407725,1.18306 -15.8732057,10.07183 -14.7734199,19.63013 1.0997857,9.55831 9.3987219,16.23758 19.2969299,15.20827 11.395441,-1.18501 19.680898,-12.82477 13.875333,-25.4204"
          id="path5046"
          class="drawline"
        />
      </g>

      <g style="display: inline;" id="white-fill">
        <path
          in:fade={{ delay: 800 }}
          d="m 18.963248,24.541422 5.11928,5.88254 16.621217,-13.3733 C 36.078748,9.7142223 31.006779,6.5383623 22.304901,7.6326623 12.897176,8.8157223 6.4316962,17.704492 7.5314812,27.262792 c 1.099786,9.55831 9.3987218,16.23758 19.2969298,15.20827 11.395442,-1.18501 19.6809,-12.82477 13.875334,-25.4204"
          id="path5046-1"
          class="whitefill"
        />
      </g>
    </svg>
  </div>
{/if}

<style lang="postcss">
  @import "variables.pcss";

  div {
    overflow: visible;
    overflow-y: visible;
    overflow-x: visible;
  }

  .bg {
    opacity: 1;
    fill: #008849;
    fill-opacity: 1;
    stroke: #008849;
    stroke-width: 25;
    stroke-miterlimit: 4;
    stroke-dasharray: none;
    stroke-opacity: 1;
  }

  .drawline {
    display: inline;
    opacity: 1;
    fill: none;
    stroke: #fff;
    stroke-width: 4.8416;
    stroke-linecap: round;
    stroke-linejoin: round;
    stroke-miterlimit: 4;
    stroke-dasharray: none;
    stroke-opacity: 1;
    paint-order: stroke fill markers;
    fill-opacity: 1;
  }

  .whitefill {
    display: inline;
    opacity: 1;
    fill: none;
    stroke: #fff;
    stroke-width: 4.8416;
    stroke-linecap: round;
    stroke-linejoin: round;
    stroke-miterlimit: 4;
    stroke-dasharray: none;
    stroke-opacity: 1;
    paint-order: stroke fill markers;
    fill-opacity: 1;
  }

  .wrapper {
    padding-top: 50px;
    padding-left: 50px;
    width: 30rem;
    height: 30rem;
    overflow: visible;
    overflow-y: visible;
    overflow-x: visible;
  }

  path {
    fill: white;
    opacity: 1;
  }

  label {
    margin-top: 5rem;
  }
</style>

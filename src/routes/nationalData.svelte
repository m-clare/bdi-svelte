<script>
    import { onMount } from 'svelte';
    import { geoAlbersUsa, geoPath } from 'd3-geo';
    // import data from '../utils/bridge_conditions.json';
    import stateMap from 'us-atlas/states-albers-10m.json';
    import { mesh } from 'topojson-client';


    let el; 

    onMount(() => {
      initialMap();
    })

    // hexbin helper functions
    const projection = geoAlbersUsa().scale(1300).translate([487.5, 305])

    // try to make map as a d3 function like Observable
    function initialMap() {
      const wrapper = d3.select(el)
      .append(div)
      .attr("id", "wrapper")

      const svg = wrapper.append("svg")
      .attr("viewBox", [0, 0, 975, 650])
      .attr("preserveAspectRatio", "xMidYMid meet")
      .append("path")
      .datum(mesh(stateMap, stateMap.objects.states))
      .attr("fill", "none")
      .attr("transform", "translate(0,0)")
      .attr("stroke", "#777")
      .attr("stroke-width", 0.5)
      .attr("stroke-linejoin", "round")
      .attr("d", geoPath());
    }

</script>

<main>
    <div bind:this={el} class="chart" />
</main>
<style>

</style>
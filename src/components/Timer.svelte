<script lang="ts">
	import { onMount } from 'svelte';

	let restedCircle: SVGCircleElement;
	let remainingCircle: SVGCircleElement;
	let timeValue: SVGTextElement;

	let restingTime = 120;
	let timeRemaining = restingTime;
	let interval: NodeJS.Timer;

	let remainingCircleStrokeDashArray = '100 100';
	let remainingCircleStrokeDashOffset = 0;

	let restedCircleStrokeDashArray = '0 100';
	let restedCircleStrokeDashOffset = 25;

	export let resting = true;

	function timer() {
		if (timeRemaining <= 0) {
			clearInterval(interval);
			resting = false;
		} else {
			timeRemaining--;
		}

		let timeRested = restingTime - timeRemaining;

		var percentageRested = (timeRested / restingTime) * 100;
		var percentageRemaining = (timeRemaining / restingTime) * 100;

		var offset = 25;

		restedCircleStrokeDashArray = percentageRested + ' ' + (100 - percentageRested);
		restedCircleStrokeDashOffset = offset;

		remainingCircleStrokeDashArray = percentageRemaining + ' ' + (100 - percentageRemaining);
		remainingCircleStrokeDashOffset = 100 - percentageRested + offset;
	}

	onMount(() => (interval = setInterval(timer, 1000)));
</script>

<div>
	<svg class="donut" viewBox="0 0 42 42">
		<circle class="donut-hole" cx="21" cy="21" r="15.91549430918954" fill="#fff" />

		<circle
			id="remaining-circle"
			cx="21"
			cy="21"
			r="15.91549430918954"
			fill="transparent"
			stroke="black"
			stroke-width="6"
			stroke-dasharray={remainingCircleStrokeDashArray}
			stroke-dashoffset={remainingCircleStrokeDashOffset}
			bind:this={remainingCircle}
		/>

		<circle
			id="rested-circle"
			cx="21"
			cy="21"
			r="15.91549430918954"
			fill="transparent"
			stroke="black"
			stroke-width="1"
			stroke-dasharray={restedCircleStrokeDashArray}
			stroke-dashoffset={restedCircleStrokeDashOffset}
			bind:this={restedCircle}
		/>

		<g class="chart-text">
			<text x="50%" y="50%" class="chart-number" id="time-value" bind:this={timeValue}>
				{new Date(timeRemaining * 1000).toISOString().substring(14, 19)}
			</text>
		</g>
	</svg>
</div>

<style>
	.chart-text {
		fill: #000;
	}

	.chart-number {
		font-size: 0.5em;
		line-height: 1;
		text-anchor: middle;
		dominant-baseline: middle;
	}
</style>

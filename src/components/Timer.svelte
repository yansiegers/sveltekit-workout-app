<script lang="ts">
	let restedCircle: SVGCircleElement;
	let remainingCircle: SVGCircleElement;
	let timeValue: SVGTextElement;

	let restingTime = 120;
	let timeRemaining = restingTime;
	let interval: NodeJS.Timer;

	let remainingCircleStrokeDashArray: string = '100 100';
	let remainingCircleStrokeDashOffset: string = '0';

	let restedCircleStrokeDashArray: string = '0 100';
	let restedCircleStrokeDashOffset: string = '25';

	function start() {
		console.log('start');
		interval = setInterval(timer, 1000);
	}

	function timer() {
		if (timeRemaining <= 0) {
			clearInterval(interval);
			console.log('interval cleared');
		} else {
			timeRemaining--;
		}

		console.log(timeRemaining);

		let timeRested = restingTime - timeRemaining;

		var percentageRested = (timeRested / restingTime) * 100;
		var percentageRemaining = (timeRemaining / restingTime) * 100;

		var offset = 25;

		restedCircleStrokeDashArray = percentageRested + ' ' + (100 - percentageRested);
		restedCircleStrokeDashOffset = offset.toString();

		remainingCircleStrokeDashArray = percentageRemaining + ' ' + (100 - percentageRemaining);
		remainingCircleStrokeDashOffset = (100 - percentageRested + offset).toString();
	}
</script>

<div>
	<button on:click={start}>Start</button>

	<svg class="donut" width="300" height="100%" viewBox="0 0 42 42">
		<circle class="donut-hole" cx="21" cy="21" r="15.91549430918954" fill="#fff" />

		<!--  GREEN  -->
		<circle
			id="remaining-cicle"
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

		<!--  PURPLE  -->
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
	/* @import url(https://fonts.googleapis.com/css?family=Montserrat:400); */

	/* body {
		font: 16px/1.4em 'Montserrat', Arial, sans-serif;
	} */
	/* * {
		-webkit-box-sizing: border-box;
		-moz-box-sizing: border-box;
		box-sizing: border-box;
	} */
	.chart-text {
		/*font: 16px/1.4em "Montserrat", Arial, sans-serif;*/
		fill: #000;
		/* -moz-transform: translateY(0.25em);
		-ms-transform: translateY(0.25em);
		-webkit-transform: translateY(0.25em); */
		transform: translateY(0.25em);
	}

	.chart-number {
		font-size: 0.5em;
		line-height: 1;
		text-anchor: middle;
		/* -moz-transform: translateY(-0.25em);
		-ms-transform: translateY(-0.25em);
		-webkit-transform: translateY(-0.25em); */
		transform: translateY(-0.25em);
	}

	/* .chart-label {
		font-size: 0.2em;
		text-transform: uppercase;
		text-anchor: middle; */
	/* -moz-transform: translateY(0.7em);
		-ms-transform: translateY(0.7em);
		-webkit-transform: translateY(0.7em); */
	/* transform: translateY(0.7em);
	} */
</style>

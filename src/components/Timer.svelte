<script lang="ts">
	let val1D: SVGCircleElement;
	let val2D: SVGCircleElement;
	let totalValue: SVGTextElement;

	let restingTime = 120;
	let timeLeft = restingTime;
	let interval: NodeJS.Timer;

	function start() {
		console.log('start');
		interval = setInterval(timer, 1000);
	}

	function timer() {
		if (timeLeft <= 0) {
			clearInterval(interval);
			console.log('interval cleared');
		} else {
			timeLeft--;
		}

		console.log(timeLeft);

		let val1 = restingTime - timeLeft;
		let val2 = timeLeft;

		var per1 = (val1 / restingTime) * 100;
		var per2 = (val2 / restingTime) * 100;

		var offset = 25;

		// totalValue.textContent = new Date(timeLeft * 1000).toISOString().substring(14, 19);

		val1D.style.strokeDasharray = per1 + ' ' + (100 - per1);
		val1D.style.strokeDashoffset = offset.toString();

		val2D.style.strokeDasharray = per2 + ' ' + (100 - per2);
		val2D.style.strokeDashoffset = (100 - per1 + offset).toString();
	}
</script>

<div>
	<button on:click={start}>Start</button>

	<svg class="donut" width="300" height="100%" viewBox="0 0 42 42">
		<circle class="donut-hole" cx="21" cy="21" r="15.91549430918954" fill="#fff" />

		<!--  GREEN  -->
		<circle
			id="donut-segment2"
			cx="21"
			cy="21"
			r="15.91549430918954"
			fill="transparent"
			stroke="black"
			stroke-width="6"
			stroke-dasharray="100 100"
			stroke-dashoffset="0"
			bind:this={val2D}
		/>

		<!--  PURPLE  -->
		<circle
			id="donut-segment1"
			cx="21"
			cy="21"
			r="15.91549430918954"
			fill="transparent"
			stroke="black"
			stroke-width="1"
			stroke-dasharray="0 100"
			stroke-dashoffset="25"
			bind:this={val1D}
		/>

		<g class="chart-text">
			<text x="50%" y="50%" class="chart-number" id="totalValue" bind:this={totalValue}>
				{new Date(timeLeft * 1000).toISOString().substring(14, 19)}
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

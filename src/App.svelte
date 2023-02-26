<script>
	import data from './data.json';
	import AttributeList from './components/AttributeList.svelte';
	
	const totalScore = data.reduce((total, num) => {
		return num.score + total
	}, 0)
	const totalAvg = parseInt(totalScore / data.length);
</script>

<main>
	<div class="results-component">
		<div class="resultContainer">
			<h2>Your Result</h2>
			<div class="circle">
				<h1>{totalAvg}</h1>
				of 100
			</div>
			<div>
				<h3>Great</h3>
				<p>Your scored higher than 65% of the people who have taken these tests.</p>
			</div>
		</div>
		<div class="summaryContainer">
			<p class="summary__title">Summary</p>
			<AttributeList attributes={data} />
			<button>Continue</button>
		</div>
	</div>
</main>

<style>
	.resultContainer {
		display: flex;
		flex-direction: column;
		gap: 1.25rem;
		background: rgb(46,43,233);
		background: linear-gradient(0deg, rgba(46,43,233,1) 0%, rgba(120,87,255,1) 100%);
		text-align: center;
		padding: 1.25rem 2rem 2rem 2rem;
		border-bottom-left-radius: 25px;
		border-bottom-right-radius: 25px;
	}
	.resultContainer h2 {
		font-size: .95rem;
		color: var(--lightLavender);
	}
	.resultContainer h3 {
		font-size: 1rem;
		margin-bottom: .5rem;
		color: var(--white);
	}
	.resultContainer p {
		font-size: .85rem;
		color: var(--lightLavender);
		max-width: 250px;
		margin: 0 auto;
	}
	.circle {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 100px;
		aspect-ratio: 1/1;
		border-radius: 50%;
		background: rgb(78,33,202);
		background: linear-gradient(0deg, rgba(78,33,202,1) 0%, rgba(36,33,202,1) 20%);
		margin: 0 auto;
		font-size: .75rem;
		color: var(--lightLavender);
	}
	.circle h1 {
		font-size: 2.5rem;
		color: var(--white);
	}
	.summaryContainer {
		padding: 1.25rem;
	}
	.summary__title {
		font-weight: 600;
		color: var(--darkGrayBlue);
		margin-bottom: 1.15rem;
	}
	button {
		background-color: var(--darkGrayBlue);
		color: var(--white);
		border: 0;
		border-radius: 25px;
		width: 100%;
		font-size: 1rem;
		font-weight: 600;
		font-family: "Hanken Grotesk";
		padding: .9rem;
		margin-top: 1.25rem;
		cursor: pointer;
	}
	button:hover {
		background: linear-gradient(0deg, rgba(46,43,233,1) 0%, rgba(120,87,255,1) 100%);
	}
	
	@media (min-width: 650px) {
		main {
			min-height: 100vh;
			display: flex;
			align-items: center;
			justify-content: center;
		}
		.results-component {
			display: flex;
			border-radius: 25px;
			overflow: hidden;
			max-width: 600px;
			width: 600px;
			box-shadow: var(--paleBlue) 0px 7px 29px 0px;
		}
		.resultContainer {
			flex: 1.5;
			border-radius: 25px;
			padding: 1.25rem 2rem 0rem 2rem;
		}
		.summaryContainer {
			flex: 2;
		}
		.circle {
			width: 150px;
		}
		.circle h1 {
			font-size: 3.5rem;
		}
		.resultContainer h2 {
			font-size: 1.25rem;
		}
		.resultContainer h3 {
			font-size: 1.5rem;
		}
		.resultContainer p {
			max-width: 200px;
		}
		button {
			padding: .65rem;
		}
	}
</style>
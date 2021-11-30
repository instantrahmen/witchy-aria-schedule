<script>
	// import Nested from './Nested.svelte';
	import schedule from '../data/schedule.ts';

	console.log({ schedule });
</script>

<div class="content">
	<h1>
		Aria's Weekly Schedule

		<img
			src="https://media.discordapp.net/stickers/910290937056473168.png?size=320"
			alt="Fynaria Sticker"
			class="fynaria-sticker"
		/>
	</h1>
	<div class="schedule">
		{#each schedule as scheduleDay}
			<div class="day">
				<div class="dayofweek">{scheduleDay.day}</div>
				<ul class="todo-list">
					{#each scheduleDay.todo as todoItem}
						<li class="todo">{todoItem}</li>
					{/each}
				</ul>
			</div>
		{/each}
	</div>
</div>

<style lang="scss">
	:global(body) {
		margin: 0;
		padding: 0;
		background: url('https://cdn.discordapp.com/attachments/862794834800410657/915020614547415080/k6bBkopO0_38SlXB7kcrZZPiInvNqi_o0UE9kupwveohHgsTaLvUvyW67je0cCHDH_osr3nzyxq5GgYbkqh4TIJz29q-hmHD-TfFnd1F_0Yo_CU9SiW6PS1Fp_IQ8JpzB2C9PSb-9zwbe81GffzNPZlUL2XlOwb_uMTYaMWjXQouz7vmuRB5KmXXOuUfoARog5Bjlrubl5LnzsHKErOeB2jJcWaB-p_Ugr3dlu6NVuY2WEKfr748TfCmlu5HRb-4BXd9kdkd1T2BV63h3X5Xners09w7-BPeRfSLQC97QTAap8NHeo5FvzkTnGwTP8mGtPUd7Tfq8m5-6I5ZfQpF4khbd85WvfgBNbYS-7nvVKOhjoyJhc_AD5ChRCH07w5I8vLCVsL5wB6-lxCvy0MHwnQC7i1iMhaFdGHX-4jH-rOnuYHjX8YEWW5tptio6grPjonzdEL2vH6WjEsqk0o6Wt9yZI_iMNQxRUY81hdMD3smJYJOcCiSIjya4etW..png');
		font-family: sans-serif;
		color: #efefef;
	}

	.content {
		display: flex;
		flex-direction: column;
		/* justify-content: center; */
		width: 100vw;
		height: 100vh;
		min-height: 100%;

		text-align: center;
		background: #000a;

		box-sizing: border-box;
	}

	ul,
	li {
		margin: 0;
		padding: 0;
		list-style: none;
		box-sizing: border-box;
	}

	h1 {
		margin-top: 200px;
		width: 100vw;
		max-width: 100%;
		background: #111a;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
		text-align: center;
		padding: 0.5em;
		border-top: 3px solid #34fafa;
		border-bottom: 3px solid #34fafa;
		box-sizing: border-box;
		position: relative;

		.fynaria-sticker {
			position: absolute;
			height: 100px;
			top: -25px;
			border-radius: 50vh;
			margin: 0 1rem 0 1rem;
		}
	}

	.schedule {
		display: grid;
		width: 100vw;
		max-width: 100%;
		justify-content: space-between;
		grid-gap: 0.36vw;
		box-sizing: border-box;

		@media (min-width: 501px) {
			grid-template-columns: repeat(7, 1fr);
		}
		@media (max-width: 700px) {
			grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
		}

		.day {
			background: #111a;
			border: 2px solid #34fafa;

			box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
			overflow: hidden;
			min-height: 240px;

			.dayofweek {
				background: #34fafa;
				color: black;
				padding: 0.5rem;
				box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
			}
		}

		.todo-list {
			transition: 200ms ease-in;
			.todo {
				padding: 0.5rem;
				background: #444a;
				box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
				margin: 8px;
				&:hover {
					background: #666a;
					box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);
				}
			}
		}
	}
</style>

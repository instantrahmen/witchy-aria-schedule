<script>
	// import Nested from './Nested.svelte';
	import schedule from '../data/schedule.ts';

	console.log({ schedule });
</script>

<h1>Aria's Weekly Schedule</h1>

<div class="schedule">
	{#each schedule as scheduleDay}
		<div class="day">
			<div class="dayofweek">{scheduleDay.day}</div>
			<ul>
				{#each scheduleDay.todo as todoItem}
					<li class="todo">{todoItem}</li>
				{/each}
			</ul>
		</div>
	{/each}
</div>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		background: url('https://cdn.discordapp.com/attachments/862794834800410657/915020614547415080/k6bBkopO0_38SlXB7kcrZZPiInvNqi_o0UE9kupwveohHgsTaLvUvyW67je0cCHDH_osr3nzyxq5GgYbkqh4TIJz29q-hmHD-TfFnd1F_0Yo_CU9SiW6PS1Fp_IQ8JpzB2C9PSb-9zwbe81GffzNPZlUL2XlOwb_uMTYaMWjXQouz7vmuRB5KmXXOuUfoARog5Bjlrubl5LnzsHKErOeB2jJcWaB-p_Ugr3dlu6NVuY2WEKfr748TfCmlu5HRb-4BXd9kdkd1T2BV63h3X5Xners09w7-BPeRfSLQC97QTAap8NHeo5FvzkTnGwTP8mGtPUd7Tfq8m5-6I5ZfQpF4khbd85WvfgBNbYS-7nvVKOhjoyJhc_AD5ChRCH07w5I8vLCVsL5wB6-lxCvy0MHwnQC7i1iMhaFdGHX-4jH-rOnuYHjX8YEWW5tptio6grPjonzdEL2vH6WjEsqk0o6Wt9yZI_iMNQxRUY81hdMD3smJYJOcCiSIjya4etW..png');
	}
</style>

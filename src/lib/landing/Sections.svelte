<script lang="ts">
	import gif from '../../assets/aggressive_ai.gif';
	import { goto } from '$app/navigation';
	let isClicked = false;
</script>

<main id="landing-content" class="w-full bg-white">
	<section class="flex flex-col gap-20 mt-36 items-center">
		<span>
			<span class="text-3xl font-bold text-sky-700">&emsp AI (Artificial Intelligence)</span> can deal
			with many complex issues and help programmers to complete more tasks in less time and become more
			productive. It helps us to code more accurately by reducing common mistakes and cutting down repetitive
			coding by suggesting the next code that you might type.
		</span>
		<img src={gif} alt="ai-talking" width="100%" />
		<span>
			&emsp Besides reducing the number of <span class="text-sky-700">errors</span>, it also ensures
			that programmers will spend less time searching for reference codes. It is a tool that will
			end up boosting human productivity and help programmers do their everyday work a lot faster by
			finding the basic building blocks they need or pointing them toward new ideas. It is useful
			not only for an experienced programmer but could also help novices learn to code.
		</span>
		<button
			id="survey-button"
			on:click={() => {
				isClicked = true;
				setTimeout(() => {
					goto('/survey');
				}, 1500);
			}}
			class="border-2 flex justify-center items-center hover:bg-sky-700 hover:text-white p-5 mb-10 transition-colors rounded-lg {isClicked
				? 'button'
				: ''}"
		>
			Read more about survey
		</button>
	</section>
</main>

<style>
	.button {
		width: 250px;
		height: 60px;
		animation: tranform 1.5s ease-in-out;
	}
	@keyframes tranform {
		0% {
			color: transparent;
			background-color: rgb(3 105 161);
		}
		30% {
			height: 50px;
			width: 50px;
			border-radius: 50%;
			color: transparent;
			background-color: rgb(3 105 161);
			transform: translateX(0);
		}
		100% {
			transform: translateX(50vw);
			height: 50px;
			width: 50px;
			border-radius: 50%;
			color: transparent;
			background-color: rgb(3 105 161);
		}
	}
</style>

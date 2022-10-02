<script lang="ts">
	import { onDestroy } from 'svelte';
	import FullBg from '../../assets/bg/full.png';
	import ParticleEffect from './ParticleEffect.svelte';
	import Sections from './Sections.svelte';
	import IoIosArrowDown from 'svelte-icons/io/IoIosArrowDown.svelte';
	import IoIosArrowForward from 'svelte-icons/io/IoIosArrowForward.svelte';
	import Automate from './Automate.svelte';
	import BigBrain from '../../assets/big-brain.png';
	import { onMount } from 'svelte';
	import Container from '$lib/components/Container.svelte';
	import { goto } from '$app/navigation';

	let isHovered = false;
	let isReady = false;
	let isChangedTheme = false;
	let allDone = false;

	let x = 0;
	let y = 0;
	let prevX = 0;
	let prevY = 0;
	let width = 250;

	let dx = 0;
	let dy = 0;
	let scale = 1;
	let speed = 0;

	let debouncer: any;

	const debounce = (v: number) => {
		clearTimeout(debouncer);
		debouncer = setTimeout(() => {
			scale = v;
		}, 300);
	};

	setTimeout(() => {
		isReady = true;
	}, 3500);

	setTimeout(() => {
		isChangedTheme = true;
	}, 3750);

	setTimeout(() => {
		allDone = true;
	}, 4500);

	// setTimeout(() => {
	// 	allDone = true;
	// }, 2500);

	let count = 0;

	const timer = setInterval(() => {
		if (isHovered) {
			scale = 1;
			return;
		}
		dx = x - prevX;
		dy = y - prevY;
		prevX = x;
		prevY = y;

		speed = Math.sqrt(dx * dx + dy * dy);
		if (speed > 2) {
			scale = 1;
			debounce(0);
		}
	}, 100);

	function onMouseMove(e: MouseEvent) {
		prevX = x;
		prevY = y;
		x = e.clientX;
		y = e.clientY;
	}

	onMount(async () => {
		// window.addEventListener('mousemove', onMouseMove);
	});

	onDestroy(async () => {
		clearInterval(timer);
		// window.removeEventListener('mousemove', onMouseMove);
	});
</script>

<!-- {#if allDone} -->
<ParticleEffect className="fixed {allDone ? 'opacity-[.4]' : 'opacity-0 '} transition-all" />
<!-- {/if} -->

<main class="relative flex justify-center">
	<div class="fadeIn showbg {isReady && 'bg-ready'}" />
	<div class="z-50 flex flex-col justify-center gap-4 px-10">
		<h1
			class="opacity-zero slideIn font-extrabold text-8xl {!isChangedTheme
				? 'text-white'
				: 'text-ready1'}"
			on:mouseenter={() => (isHovered = true)}
			on:mouseleave={() => (isHovered = false)}
			style="letter-spacing: .25rem; animation-delay: 0s"
		>
			Artificial
		</h1>
		<h1
			class="opacity-zero slideIn font-thin text-7xl {!isChangedTheme
				? 'text-white'
				: 'text-ready2'}"
			style=" animation-delay: 0.12s"
		>
			Intelligence
		</h1>
		<h2
			class="opacity-zero slideIn mt-8 text-6xl font-bold {!isChangedTheme
				? 'text-white'
				: 'text-ready3'}"
			style=" animation-delay: 4.5s"
		>
			<span
				class="px-3 text-white bg-black {!isChangedTheme ? 'bg-white text-black' : 'text-ready4'} "
				>affects</span
			>
			us?
		</h2>
		<div class="flex pl-20">
			<a
				href="#about"
				class="opacity-zero rounded p-4 px-10 hover:px-[5rem] slideIn mt-20 hover:backdrop-blur-sm hover:bg-black hover:bg-opacity-5 text-black hover:border-solid hover:border-gray-300 hover:border-[1px]  border-transparent border-[1px] ml-20 flex gap-2 items-center"
				style=" animation-delay: 2s"
			>
				<b>GET STARTED</b>
				<div class="icon">
					<IoIosArrowForward />
				</div>
			</a>
		</div>
	</div>
	<div
		class="relative flex items-center justify-center w-full h-full section-actions-hero animate-actions-hero"
	>
		<div
			class="w-full relative h-full z-10 {allDone
				? 'opacity-1'
				: 'opacity-0 '} transition-all duration-700 flex justify-center items-center "
		>
			<img src={BigBrain} alt="logo" />
			<!-- <div
				class="absolute"
				style="transform-origin: 50% 50%; width: 300px; aspect-ratio: 1; left: 50%; top: 50%; backdrop-filter: blur(4px); transform: scale(2) translate(-50%,0); background: rgba(0,0,0,.1);  border-radius: 50%; transition: transform .25s ease-in-out;"
			/> -->
		</div>
		<Automate show={!allDone} />
	</div>
	<!-- <div
		class="absolute "
		style="transform-origin: 50% 50%; left: {x - width / 2}px; top: {y -
			width /
				2}px; backdrop-filter: blur(8px); transform: scale({scale}); background: rgba(0,0,0,.1); width: {width}px; height: {width}px; border-radius: 50%; transition: transform .25s ease-in-out;"
	/> -->

	<div class="absolute bottom-0 left-0 right-0 flex justify-center align-center">
		<a
			href="#about"
			style="transition: background .25s ease-in-out, border .25s ease-in-out;"
			class="flex flex-col items-center justify-center p-2 px-6 pt-4 mb-2 text-sm rounded "
		>
			<a href="#landing-content" class="font-bold z-50">CLICK TO SCROLLING DOWN</a>
			<div class="icon">
				<IoIosArrowDown />
			</div>
		</a>
	</div>
</main>

<Container>
	<Sections />
</Container>

<style>
	.text-ready1 {
		margin-left: 9rem;
	}
	.text-ready2 {
		margin-left: 16rem;
	}
	.text-ready3 {
		margin-left: 12rem;
	}
	.text-ready4 {
		margin-left: 0%;
	}

	.bg-ready {
		right: 100% !important;
	}

	.opacity-zero {
		opacity: 0;
	}
	.slideIn {
		animation: slideIn 0.5s forwards;
		-webkit-transition: -webkit-all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: -webkit-all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		-o-transition: all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99),
			-webkit-all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
	}

	@keyframes slideIn {
		0% {
			transform: translateY(100%);
			opacity: 0;
		}
		100% {
			transform: translateY(0);
			opacity: 1;
		}
	}

	.fadeIn {
		animation: fadeIn 0.5s forwards;
		-webkit-transition: -webkit-transform 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: -webkit-transform 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		-o-transition: transform 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: transform 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: transform 1s cubic-bezier(0.14, 0.15, 0.13, 0.99),
			-webkit-transform 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
	}
	@keyframes fadeIn {
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}

	.showbg {
		position: absolute;
		top: 0px;
		left: 0px;
		right: 0px;
		bottom: 0px;
		background: black;
		-webkit-transition: -webkit-all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: -webkit-all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		-o-transition: all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
		transition: all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99),
			-webkit-all 1s cubic-bezier(0.14, 0.15, 0.13, 0.99);
	}
</style>

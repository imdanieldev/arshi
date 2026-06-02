<template>
	<div>
		<div class="w-full h-svh bg-black fixed top-0 left-0 z-0">
			<FloatingLines :enabled-waves="['middle']" :line-count="[2]" :line-distance="[10]" :bend-radius="5.0"
				:bend-strength="-0.5" :interactive="true" :parallax="false" />
		</div>
		<div class="w-full min-h-svh relative z-10 text-white flex items-center justify-center flex-col">
			<div class="arshi w-64 rounded-full border-2 border-solid border-white overflow-hidden relative">
				<img src="/arshi.jpg">
			</div>
			<div class="w-full flex justify-center items-center gap-x-1 mt-5">
				<h1 class="text-3xl split">Arshia Kadkhodaei</h1>
				<div class="bg-black/5 backdrop-blur-xs px-4 py-4 rounded-xl logo">
					<img src="/logo.png" class="h-22">
				</div>
			</div>
			<div class="grid">
				<div class="mt-5 flex flex-wrap gap-x-2 justify-center items-center w-full links">
					<a href="//instagram.com/z1arshia"
						class="shadow-md shadow-white/10 text-lg flex justify-center items-center gap-x-1 bg-white/5 backdrop-blur-sm rounded-lg px-3 py-2 transition-colors duration-300 hover:bg-white/10">
						<svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8"
							viewBox="0 0 24 24"><!-- Icon from Huge Icons by Hugeicons - undefined -->
							<g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
								stroke-width="1.5">
								<path
									d="M3 12c0-4.243 0-6.364 1.318-7.682S7.758 3 12 3s6.364 0 7.682 1.318S21 7.758 21 12s0 6.364-1.318 7.682S16.242 21 12 21s-6.364 0-7.682-1.318S3 16.242 3 12" />
								<path
									d="M16 12a4 4 0 1 1-8 0a4 4 0 0 1 8 0m1.375-5.25h-.125m.25 0a.25.25 0 1 1-.5 0a.25.25 0 0 1 .5 0" />
							</g>
						</svg>
						Instagram
					</a>
					<a href="//t.me/z1Arshia"
						class="shadow-md shadow-white/10 text-lg flex justify-center items-center gap-x-1 bg-white/5 backdrop-blur-sm rounded-lg px-3 py-2 transition-colors duration-300 hover:bg-white/10">
						<svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8"
							viewBox="0 0 24 24"><!-- Icon from Huge Icons by Hugeicons - undefined -->
							<path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
								stroke-width="1.5"
								d="m11.985 15.408l3.242 3.686c1.2 1.365 1.801 2.048 2.43 1.881c.628-.166.844-1.064 1.275-2.861l2.39-9.968c.665-2.768.997-4.151.259-4.834s-2.017-.175-4.575.84L5.14 8.865c-2.046.813-3.069 1.219-3.134 1.917a1 1 0 0 0 0 .214c.063.699 1.084 1.108 3.128 1.927c.925.371 1.388.557 1.72.912q.056.06.108.124c.306.38.436.88.697 1.876l.489 1.867c.253.97.38 1.456.713 1.522s.622-.336 1.201-1.141zm0 0l-.317-.33c-.362-.378-.543-.566-.543-.8s.18-.423.543-.8l3.573-3.724" />
						</svg>
						Telegram
					</a>
				</div>
				<a href="tel:+989909949604"
					class="phone shadow-lg shadow-white/10 w-full mt-3 text-2xl flex justify-center items-center gap-x-1 bg-white/5 backdrop-blur-sm rounded-lg px-3 py-2 transition-colors duration-300 hover:bg-white/10">
					<svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8"
						viewBox="0 0 24 24"><!-- Icon from Huge Icons by Hugeicons - undefined -->
						<g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
							stroke-width="1.5">
							<path
								d="M13.5 2h-3c-2.357 0-3.536 0-4.268.732S5.5 4.643 5.5 7v10c0 2.357 0 3.535.732 4.268S8.143 22 10.5 22h3c2.357 0 3.535 0 4.268-.732c.732-.733.732-1.911.732-4.268V7c0-2.357 0-3.536-.732-4.268C17.035 2 15.857 2 13.5 2" />
							<path d="M12.125 19H12m.25 0a.25.25 0 1 1-.5 0a.25.25 0 0 1 .5 0" />
						</g>
					</svg>
					+98 990 994 9604
				</a>
			</div>
		</div>
	</div>
</template>
<script setup>
import { gsap } from "gsap";
import { SplitText } from "gsap/SplitText";

gsap.registerPlugin(SplitText);

onMounted(() => {
	let split = SplitText.create(".split", { type: "chars" });

	gsap.from(split.chars, {
		duration: 1.5,
		x: 100,
		y: 100,
		rotate: 180,
		autoAlpha: 0,
		stagger: 0.05,
		delay: 2,
		ease: "back.out(1.7)",
	});
	gsap.from(".arshi", {
		duration: 2,
		scale: 0,
		opacity: 0,
		autoAlpha: 0,
		ease: "back.out(1.7)",
	});
	gsap.from(".logo", {
		duration: 2,
		scale: 0,
		rotate: 180,
		autoAlpha: 0,
		ease: "back.out(1.7)",
		delay: 1.5,
	});
	gsap.from(".links a", {
		duration: 1,
		y: 50,
		autoAlpha: 0,
		stagger: 0.2,
		delay: 3.5,
		ease: "power4.out",
	});
	gsap.from(".phone", {
		duration: 1,
		y: 50,
		autoAlpha: 0,
		stagger: 0.2,
		delay: 4.5,
		ease: "power4.out",
	});
});

useHead({
	title: 'Arshia KD',
	meta: [
		{ name: 'description', content: 'Arshia personal website.' },
		{ name: 'viewport', content: 'width=device-width, initial-scale=1' },
		{ name: 'author', content: 'Danial' },
	],
	link: [
		{ rel: 'icon', type: 'image/png', href: '/logo.png' },
	],
})
</script>
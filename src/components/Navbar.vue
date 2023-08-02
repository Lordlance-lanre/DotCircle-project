<template>
<div>
	<nav class="flex justify-between md:justify-around md:pt-3">
		<img src="../../image/dotcircle2.png" class=" md:w-32 ml-4 md:ml-0" alt="">

		<button @click="handleTransition">
			<img src="../../image/hamburger2.svg" class="w-16 mt-[-10px] md:hidden" alt="">
		</button>
		<ul  class="screen text-white hidden md:flex mt-2">
			<li class="mr-6 hover:text-emerald-400 transition ease-in-out duration-500">Case Studies</li>
			<li class="mr-6 hover:text-emerald-400 transition ease-in-out duration-500">Services</li>
			<li class="mr-6 hover:text-emerald-400 transition ease-in-out duration-500">About</li>
			<li class="mr-6 hover:text-emerald-400 transition ease-in-out duration-500">Careers</li>
		</ul>

		<button class="text-black hidden md:block bg-white rounded mr-5 hover:bg-zinc-900 hover:text-gray-100 transition ease-in-out duration-500 px-3 tracking-wide">Start a Project</button>
	</nav>

	<transition name="fade">
		<ul v-if="showToggle"  class="mobile text-white md:hidden text-center">
			<li class=" hover:text-emerald-400 transition ease-in-out duration-500  hover:bg-zinc-950 py-2">Case Studies</li>
			<li class=" hover:text-emerald-400 transition ease-in-out hover:bg-zinc-950 py-2 duration-500 ">Services</li>
			<li class="hover:bg-zinc-950 py-2 hover:text-emerald-400 transition ease-in-out duration-500">About</li>
			<li class="hover:bg-zinc-950 py-2 hover:text-emerald-400 transition ease-in-out duration-500">Careers</li>
			<button class="mt-2 text-black bg-white px-3 py-2 rounded  hover:bg-zinc-900 hover:text-gray-100 transition ease-in-out duration-500">
				<li>Start a project</li>
			</button>
		</ul>
	</transition>
</div>
</template>

<script setup>
import {ref} from 'vue';

const showToggle = ref(false);

function handleTransition(){
	showToggle.value = !showToggle.value;
}

</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
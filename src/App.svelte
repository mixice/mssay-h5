<script>
	import Banner from './lib/Banner.svelte';
	import Case from './lib/Case.svelte';
	import Skill from './lib/Skill.svelte';
	import Process from './lib/Process.svelte';
	import Brand from './lib/Brand.svelte';
	import Contact from './lib/Contact.svelte';

	import { Swiper, SwiperSlide } from 'swiper/svelte';
	import 'swiper/css';
	import { Mousewheel, Pagination } from 'swiper';
	import 'swiper/css/pagination';

	import anime from 'animejs/lib/anime.min.js';

	function ani(){
		anime({targets: '.skill li',translateY: [200,0],opacity: [0,1],delay: anime.stagger(100),});
		anime({targets: '.process li',scale: [0,1],opacity: [0,1],delay: anime.stagger(100),});
		anime({targets: '.brand li',translateX: [500,0],opacity: [0,1],delay: anime.stagger(100),});
		anime({targets: '.contact .cont li',translateX: [-500,0],opacity: [0,1],delay: anime.stagger(100),});
	};

	export let logo;
</script>

<main>
	<Swiper class="subject"
		modules={[Mousewheel, Pagination]}
		direction={"vertical"}
		mousewheel={true}
		pagination={{ clickable: true }}
		on:slideChange={() => ani()}
	>
		<SwiperSlide><Banner {logo} /></SwiperSlide>
		<SwiperSlide><Skill /></SwiperSlide>
		<SwiperSlide><Case /></SwiperSlide>
		<SwiperSlide><Process /></SwiperSlide>
		<SwiperSlide><Brand /></SwiperSlide>
		<SwiperSlide><Contact /></SwiperSlide>
	</Swiper>
</main>

<style lang="less">
	main {height: 100%;overflow: hidden;}

	@media(max-width:640px) {

	}
</style>
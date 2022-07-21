<script>
	import Atropos from "atropos/svelte";
	import "atropos/css";

	import { Swiper, SwiperSlide } from "swiper/svelte";
	import "swiper/css";
	import { Navigation, Pagination } from "swiper";
	import "swiper/css/navigation";
	import "swiper/css/pagination";

	let caseBg = 'images/case.png';
	const list = [
		{number: '1',},
		{number: '2',},
		{number: '3',},
		{number: '4',},
		{number: '5',},
	];

</script>

<section class="case" style="background-image: url({caseBg})">
	<Swiper class="project"
		navigation={true}
		pagination={true}
		modules={[Navigation, Pagination]}
	>
		{#each list as { number }}
			<SwiperSlide>
				<li>
					<Atropos>
						<img src="images/case/{number}/1.png" data-atropos-offset="-2" alt="">
						<img src="images/case/{number}/2.png" data-atropos-offset="0" alt="">
						<img src="images/case/{number}/3.png" data-atropos-offset="2" alt="">
						<img src="images/case/{number}/4.png" data-atropos-offset="4" alt="">
						<img src="images/case/{number}/5.png" data-atropos-offset="6" alt="">
					</Atropos>
					<span>
						<i class="ico ico-qrcode"></i>
						<em class="anime-fade-in"><img src="images/case/{number}/0.png" alt=""></em>
					</span>
				</li>
			</SwiperSlide>
		{/each}
	</Swiper>
</section>

<style lang="less">
	@case-img-width: 480px;
	@case-img-height: 800px;
	.case {height: 100%;background-size: cover;
		li {width: @case-img-width;height: @case-img-height;position: relative;margin-top: -6%;
			img {position: relative;top: -5%;left: -5%;width: 110%;height: 110%;max-width: inherit;
				&:not(:first-child) {position: absolute;}
			}
			span {position: absolute;top: 0;left: 0;z-index: 1;
				i {color: var(--333);width: 50px;height: 50px;line-height: 50px;background-color: white;border-radius: 100%;margin: 10px 0 0 10px;position: relative;z-index: 1;}
				em {position: absolute;top: 0;left: 0;width: @case-img-width;height: @case-img-height * 1.1;background-color: var(--000-8);display: none;align-items: center;justify-content: center;
					& > img {width: 50%;height: auto;background-color: white;position: static;}
				}
				&:hover {
					i {background-color: var(--333);color: white;}
					em {display: flex;}
				}
			}
		}
	}

	@media(max-width:640px) {
		@case-img-width: 4.8rem;
		@case-img-height: 8rem;
		.case {
			li {width: @case-img-width;height: @case-img-height;
				span {
					i {width: .7rem;height: .7rem;line-height: .7rem;margin: .1rem 0 0 .1rem;}
					em {width: @case-img-width;height: @case-img-height * 1.1;}
				}
			}
		}
	}
</style>
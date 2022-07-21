<script>
	export let logo;
	let title = '专注微信H5解决方案';
	let describe = '个性化定制开发服务';
	let abbreviation = 'mssay';
	let bannerBg = 'images/banner.png';
	const banner = [
		{img: 'images/banner/1.png',},
		{img: 'images/banner/2.png',},
		{img: 'images/banner/3.png',},
		{img: 'images/banner/4.png',},
		{img: 'images/banner/5.png',},
	]
</script>

<section class="banner center" style="background-image: url({bannerBg})">
	<u>
		{#each banner as {img}}
			<i style="background-image: url({img})"></i>
		{/each}
	</u>
	<b>{abbreviation}</b>
	<a href="/" target="_blank"><h1><i style="background-image: url({logo});"></i></h1></a>
	<div class="cont">
		<i class="ico ico-wechat"></i>
		<h2>{title}</h2>
		<h4>{describe}</h4>
	</div>
</section>

<style lang="less">
	.banner {height: 100vh;background-size: cover;position: relative;overflow: hidden;
		u {width: 115vh;height: 100vh;position: absolute;left: 45%;top: 0;animation-delay: 1s;
			i {width: 100%;height: 100%;background-size: cover;position: absolute;top: 0;left: 0;transition-duration: 0s;background-position: left center;
			}
		}
		b {position: absolute;left: 5%;color: var(--fff-1);font-size: 360px;text-transform: uppercase;writing-mode: vertical-lr;white-space: nowrap;}
		h1 {position: absolute;top: 0;left: 0;margin: 30px;z-index: 3;
			i {display: block;width: 60px;height: 60px;}
			&:hover i {transform: rotateY(180deg);}
		}
		.cont {width: 100%;padding: 40px;position: relative;
			i {width: 100px;height: 100px;line-height: 100px;border-radius: 20px;background-color: white;font-size: 72px;color: var(--blue);}
			h2, h4 {color: white;margin: 20px 0;}
			h2 {font-size: 60px;}
			h4 {font-size: 24px;font-weight: normal;}
		}
	}

	@media(max-width:640px) {
		.banner {
			b {font-size: 3rem;}
			h1 {margin: .2rem;
				i {width: .7rem;height: .7rem;}
			}
			.cont {padding: .2rem;
				i {width: 1rem;height: 1rem;line-height: 1rem;border-radius: .2rem;font-size: .7rem;}
				h2, h4 {margin: .2rem 0;}
				h2 {font-size: .56rem;}
				h4 {font-size: .26rem;}
			}
		}
	}
</style>
<script>
	let brandBg = 'images/brand.png';
	const brand = [
		{href: '', img: 'images/brand/1.jpg',},
		{href: '', img: 'images/brand/2.jpg',},
		{href: '', img: 'images/brand/3.jpg',},
		{href: '', img: 'images/brand/4.jpg',},
		{href: '', img: 'images/brand/5.jpg',},
		{href: '', img: 'images/brand/6.jpg',},
		{href: '', img: 'images/brand/7.jpg',},
		{href: '', img: 'images/brand/8.jpg',},
		{href: '', img: 'images/brand/9.jpg',},
		{href: '', img: 'images/brand/10.jpg',},
		{href: '', img: 'images/brand/11.jpg',},
		{href: '', img: 'images/brand/12.jpg',},
		{href: '', img: 'images/brand/13.jpg',},
		{href: '', img: 'images/brand/14.jpg',},
		{href: '', img: 'images/brand/15.jpg',},
		{href: '', img: 'images/brand/16.jpg',},
		{href: '', img: 'images/brand/17.jpg',},
		{href: '', img: 'images/brand/18.jpg',},
		{href: '', img: 'images/brand/19.jpg',},
		{href: '', img: 'images/brand/20.jpg',},
	];
</script>

<section class="brand center" style="background-image: url({brandBg})">
	<div class="cont">
		{#each brand as { href, img }}
			<!-- svelte-ignore a11y-missing-content -->
			<li><a {href} style="background-image: url({img})" target="_blank"></a></li>
		{/each}
	</div>
</section>

<style lang="less">
	.brand {height: 100vh;background-size: cover;
		.cont {text-align: center;width: 75%;
			li {padding: 10px;display: inline-block;transition-duration: 0s;
				a {width: 160px;height: 160px;display: block;border-radius: 15px;}
				&:hover a {transform: translateY(-10px);box-shadow: 0 10px 20px var(--000-1);}
			}
		}
	}

	@media(max-width:640px) {
		.brand {
			.cont {width: 90%;
				li {padding: .05rem;
					a {width: 1.2rem;height: 1.2rem;border-radius: .1rem;}
					&:hover a {transform: translateY(-.1rem);box-shadow: 0 .1rem .2rem var(--000-1);}
				}
			}
		}
	}
</style>
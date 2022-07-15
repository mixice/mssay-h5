<script>
	let contactBg = 'images/contact.png';
	const contact = [
		{type: '联系电话', ico: 'ico-call', color: 'var(--blue)', cont: [
			{txt: '18215582510', href: 'tel:18215582510',},
			{txt: '13330430414', href: 'tel:13330430414',},
		],},
		{type: '邮件', ico: 'ico-mail', color: 'var(--red)', cont: [
			{txt: 'ms@mssay.com', href: 'mailto:ms@mssay.com',},
			{txt: 'mixice@mixice.com', href: 'mailto:mixice@mixice.com',},
			{txt: '767557453@qq.com', href: 'mailto:767557453@qq.com',},
		],},
		{type: '微信', ico: 'ico-wechat', color: 'var(--green)', cont: [
			{txt: 'py767557453', href: '',},
			{txt: 'mixicerain', href: '',},
		],},
		{type: 'QQ', ico: 'ico-qq', color: 'var(--orange)', cont: [
			{txt: '247083860', href: '',},
			{txt: '544490', href: '',},
		],},
		{type: 'telegram', ico: 'ico-telegram', color: 'var(--sapphire)', cont: [
			{txt: '@mixice', href: '',},
		],},
		{type: 'skype', ico: 'ico-skype', color: 'var(--brown)', cont: [
			{txt: 'mixice@mixice.com', href: '',},
		],},
	];
</script>

<section class="contact center" style="background-image: url({contactBg})">
	<div class="cont">
		{#each contact as { ico, color }}
			<li><span class="center" style="background-color: {color}"><i class="ico {ico}"></i></span></li>
		{/each}
	</div>
	<div class="popup">
		{#each contact as { type, cont } }
			<pop>
				<pop-main>
					<!-- svelte-ignore a11y-missing-content a11y-missing-attribute -->
					<pop-title><h3>{type}</h3><a class="close"></a></pop-title>
					<pop-cont>
						{#each cont as { txt, href } }
							<li><a {href} class="btn" target="_blank">{txt}<shadow></shadow></a></li>
						{/each}
					</pop-cont>
				</pop-main>
			</pop>
		{/each}
	</div>
</section>

<style lang="less">
	.contact {height: 100vh;background-size: cover;
		.cont {text-align: center;
			li {display: inline-block;transition-duration: 0s;
				span {width: 100px;height: 100px;border-radius: 100%;display: block;margin: 10px;cursor: pointer;
					i {color: white;font-size: 48px;}
				}
				&:hover {transform: rotate(360deg);}
			}
		}
		.popup {
			pop-cont {padding: 20px;overflow: hidden;
				li {padding: 10px;float: left;
					a {font-size: 16px;text-transform: none;}
				}
			}
		}
	}

	@media(max-width:640px) {
		.contact {
			.cont {
				li {
					span {width: 1.6rem;height: 1.6rem;margin: .3rem;
						i {font-size: .6rem;}
					}
				}
			}
			.popup {
				pop-cont {padding: .2rem;
					li {padding: .1rem;
						a {font-size: .22rem;}
					}
				}
			}
		}
	}
</style>
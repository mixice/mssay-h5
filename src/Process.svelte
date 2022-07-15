<script>
	const process = [
		{ico: 'ico-square-a', subject: '项目定制', info: '由专人对接定制项目计划',},
		{ico: 'ico-square-b', subject: '原型创意', info: '进行原型设计与客户深度沟通',},
		{ico: 'ico-square-c', subject: '设计绘制', info: '设计师对产品精细化设计绘图',},
		{ico: 'ico-square-d', subject: '前端动画', info: '由前端工程师实现代码以及动画',},
		{ico: 'ico-square-e', subject: '程序逻辑', info: '程序员完成后台及业务逻辑',},
		{ico: 'ico-square-f', subject: '流程测试', info: '对整个业务流程进行压力测试',},
		{ico: 'ico-square-g', subject: '项目部署', info: '完成相关审核部署项目',},
		{ico: 'ico-square-h', subject: '跟踪监听', info: '对项目使用进行数据跟踪分析',},
		{ico: 'ico-square-i', subject: '验收存档', info: '项目数据交付存档',},
	];
</script>

<section class="process center">
	<canvas id="canvas"></canvas>
	<div class="cont">
		{#each process as { ico, subject, info }, i}
			<li><span style="background-image: url(images/process/{i + 1}.jpg)"><i class="ico {ico}"></i><em class="full center"><h4>{subject}</h4><h5>{info}</h5></em></span></li>
		{/each}
	</div>
	<audio></audio>
</section>

<style lang="less">
	.process {height: 100vh;
		canvas {width: 100%;height: 100%;position: absolute;top: 0;left: 0;background-color: var(--blue);}
		.cont {position: relative;text-align: center;width: 80%;max-width: 1500px;
			li {width: 260px;height: 260px;cursor: pointer;margin: 5px;transition-duration: 0s;display: inline-block;
				span {width: 100%;height: 100%;display: block;border-radius: 100%;background-color: var(--blue);position: relative;overflow: hidden;border: 5px white solid;
					i {font-size: 48px;color: white;position: absolute;top: 0;left: 0;right: 0;margin: 10px;}
					em {background-color: var(--000-8);transform: translateY(75%);border-radius: 100%;text-align: center;overflow: hidden;padding-top: 15%;
						h4 {border-radius: 100%;color: white;position: absolute;top: 0;left: 0;width: 100%;height: 25%;display: flex;align-items: center;justify-content: center;}
						h5 {color: white;opacity: 0;}
					}
					&:hover {
						i {opacity: 0;}
						em {transform: translateY(0);
							h4 {background-color: var(--blue);}
							h5 {opacity: 1;transition-delay: .3s;}
						}
					}
				}
			}
		}
	}

	@media(max-width:640px) {
		.process {
			.cont {width: 85%;
				li {width: 1.6rem;height: 1.6rem;margin: .05rem;
					span {border: .03rem white solid;
						i {font-size: .5rem;margin: 0;line-height: 1.6rem;}
						em {display: none !important;}
					}
				}
			}
		}
	}
</style>
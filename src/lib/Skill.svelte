<script>
	let skillBg = 'images/skill.png';
	const skill = [
		{color: 'var(--blue)', ico: 'ico-pain-men',label: '照片换脸',summary: '用户上传照片，与预先设定的场景人物进行人脸合成，可用于朋友圈分享',},
		{color: 'var(--orange)', ico: 'ico-imagelist',label: '图像合成',summary: '将用户个人信息（比如微信头像，微信昵称）以及用户选择的内容（答题，绘画，选择），进行图像合成',},
		{color: 'var(--green)', ico: 'ico-cameraroll',label: '剧情滚动',summary: '按照剧情进行长图设计，并在各个环节设置滚动的动画效果，实现流畅的长剧情表述',},
		{color: 'var(--sapphire)', ico: 'ico-draft',label: '表单问卷',summary: '在H5中创建各种表单问题（单选，多选，问答，评分，排序等），以达到用户信息采集，数据收集的作用',},
		{color: 'var(--tomato)', ico: 'ico-paper',label: '新闻发布',summary: '预设信息图文发布等功能，主要用于宣传，公告以及政务展示等，并设置独立后台控制，数据访问监控',},
		{color: 'var(--red)', ico: 'ico-game-key',label: '互动小游戏',summary: '植入各类型小游戏（点击，滑动，竞猜等），增加用户互动性，并将得分进行统计报告',},
		{color: 'var(--sapphire)', ico: 'ico-lottery-win',label: '幸运抽奖',summary: '可使用轮盘，骰子，随机等多种抽奖方式植入到H5中，增加项目趣味性',},
		{color: 'var(--666)', ico: 'ico-bookrack',label: '知识报告',summary: '按照项目知识体系进行内容管理，期刊发布等',},
		{color: 'var(--pink)', ico: 'ico-circular-help',label: '答题创意',summary: '根据项目内容定制宣传性质问答，以达到良好的信息记忆',},
		{color: 'var(--orange)', ico: 'ico-thumb-up',label: '拉票集赞',summary: '用户上传作品（绘画，摄影，艺术等）内容，进行范围投票评选，以达到亲友传播裂变效果',},
		{color: 'var(--green)', ico: 'ico-vr',label: '全景VR',summary: '使用全景VR等技术，展示虚拟实景，主要用于馆场，校区，景点等展示',},
		{color: 'var(--purple)', ico: 'ico-emot-children',label: '人脸识别',summary: '对用户上传的照片进行人脸识别，可用于用户认证，年龄识别，娱乐算命等',},
		{color: 'var(--brown)', ico: 'ico-squareflower',label: '推理解密',summary: '根据项目内容构划推理解密游戏，让用户沉浸其中的同时了解产品本身',},
		{color: 'var(--333)', ico: 'ico-angle-random',label: '随机推荐',summary: '使用一些生活中常常面临选择的问题，进行随机推荐，可涵盖吃喝玩乐，衣食住行等生活中的方方面面',},
		{color: 'var(--blue)', ico: 'ico-flag-aim',label: '工具信息',summary: '将一些实用小工具与产品结合设计，方便用户的同时，宣传产品本身',},
		{color: 'var(--orange)', ico: 'ico-muzak',label: '音乐语音',summary: '对用户进行语音采集，语音处理（变声，搞笑等），给其他作品（影视，卡通）等进行配音',},
		{color: 'var(--tomato)', ico: 'ico-movie',label: '视频定制',summary: '视频采集，剪辑，特效等处理，并使用在H5项目中',},
		{color: 'var(--sapphire)', ico: 'ico-player',label: '动画创意',summary: '对项目中各个环节等按照内容进行动画创意',},
		{color: 'var(--green)', ico: 'ico-rotate',label: '美术设计',summary: '我们有专业设计师和画师，设定项目美术风格，整体绘画，细节勾勒',},
		{color: 'var(--red)', ico: 'ico-wechat',label: '微信小程序',summary: '对长期使用的H5，经行小程序打包上架',},
	];
</script>

<section class="skill center" style="background-image: url({skillBg})">
	<div class="cont">
		<ul>
			{#each skill as { color, ico, label }, i}
				<li><span class="center" style="background-color: {color}"><em><i class="ico {ico}"></i><h5>{label}</h5></em></span></li>
			{/each}
		</ul>
	</div>
	<audio></audio>
	<div class="popup">
		{#each skill as { color, label, summary }}
			<pop>
				<pop-main style="background-color: {color}">
					<!-- svelte-ignore a11y-missing-attribute a11y-missing-content -->
					<pop-title><h3>{label}</h3><a class="close"></a></pop-title>
					<pop-cont>{summary}</pop-cont>
				</pop-main>
			</pop>
		{/each}
	</div>
</section>

<style lang="less">
	.skill {height: 100%;background-size: cover;
		.cont {width: 80%;
			ul {overflow: visible;text-align: center;
				li {width: 200px;height: 200px;transition-duration: 0s;padding: 10px;display: inline-block;
					span {width: 100%;height: 100%;display: block;font-size: 24px;border-radius: 20px;cursor: pointer;
						em {text-align: center;color: white;
							i {font-size: 48px;margin-bottom: 15px;}
						}
						&:hover {border-radius: 100%;
							i {transform: rotateY(180deg);}
						}
					}
				}
			}
		}
		.popup {
			pop-main {border-radius: 20px;overflow: hidden;
				pop-title, pop-title a, pop-cont {background-color: transparent;color: white;}
				pop-title {border-bottom-color: var(--fff-2);}
				pop-cont {padding: 20px;line-height: 200%;}
			}
		}
	}

	@media(max-width:640px) {
		.skill {
			.cont {width: 85%;
				ul {
					li {width: 33.33%;height: 1.5rem;padding: .05rem;float: left;
						span {width: 100%;height: 100%;font-size: .24rem;border-radius: .2rem;
							em i {font-size: .5rem;margin-bottom: .1rem;}
						}
					}
				}
			}
			.popup {
				pop-main {border-radius: .2rem;
					pop-cont {padding: .2rem;}
				}
			}
		}
	}
</style>
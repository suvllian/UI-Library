<template>
	<div class="article-list">
		<article class="article" v-for="i in 5">
			<span class="roate-date">
				<span class="month">12月</span>
				<span class="day">25</span>
			</span>

			<header class="artcile-head">
				<p class="title"><a href="" title="">2016年年终总结</a></p>
				
				<p class="article-meta">
					<i></i>
					发表于
					<time datetime="2011-01-12">January 12th, 2011</time>
					•
					<i></i>
					<span>100次围观</span>
					•
					<i></i>
					<span>100条评论</span>
				</p>

				<div class="label">
					<a href="" title="前端">前端</a>
				</div>
			</header>

			<div class="article-content">
				<div class="intro-img">
					<img src="http://www.suvllian.com/V/images/books/bookBg/4.jpg" alt="">
				</div>
				<div class="intro-p">
					<p>脱下校服穿上了西装，八年前彗星飞过，五年前你去的那个小镇，你不记得了。</p>
					<p>“醒来的时候不知道自己为什么会哭，时常会有的事。”</p>
					<p>做过的梦总是回想不起，有一种忘记了什么丧失感。<a href="" title="">继续阅读</a></p>
				</div>
			</div>

			<div class="article-content">
				<div class="more">
					<p><a href="" title="">阅读全文 >></a></p>
				</div>
			</div>
		</article>
	</div>
</template>

<script>
export default{
	data(){
		return{
			
		}
	},

	methods:{
		
	},

	created(){
		
    }
}
</script>
<style lang="scss" scoped>
	// 响应式布局
	@mixin respond-to($breakpoint) {
	    @if $breakpoint == "small" {
	        @media (max-width: 510px) {
	            @content;
	        }
	    }
	    @else if $breakpoint == "medium" {
	        @media (max-width: 800px) {
	        	@content;
	    	}
	  	} 
	    @else if $breakpoint == "large" {
	    	@media (max-width: 1200px) {
	    		@content;
	    	}
	    }
	}

	$Color:#00adb5;

	.article-list{
		width: 70%;
		margin: 0 auto;
		font-family: PingFang TC,Avenir Next,Helvetica,Arial,Hiragino Sans GB,Microsoft YaHei,sans-serif;
		clear: both;

		.article{
			padding:15px;
			margin: 50px auto;
			width: 100%;
			background-color:#fff;
			position:relative;
			border-radius:5px;

			p{
				line-height: 24px;
				margin: 10px 0;
			}

			.roate-date{
				height: 70px;
				width: 70px;
				padding:9px 12px;
				position:absolute;
				top: -30px;
				left: -25px;
				color: #fff;
				background-color: $Color;
				border-radius: 50%;
				box-shadow:0 2px 2px 0 rgba(0,0,0,0.14),0 3px 1px -2px rgba(0,0,0,0.2),0 1px 5px 0 rgba(0,0,0,0.12);

				%span{
					text-align: center;
					display: block;
				}

				.month{
					font-size: 16px;
					@extend %span;
				}

				.day{
					@extend %span;
					font-size: 28px;
					font-weight: 600;
				}

			}

			.artcile-head{
				position:relative;
				padding-bottom:48px;

				.title{
					font-size: 25px;
					font-weight: 700;
					line-height: 30px;
					text-align: center;
					max-height: 100%;

					a{
						color: #444;
					}
				}

				.article-meta{
					color: #555;
					font-size: 14px;
					text-align: center;
				}

				.label{
					padding:5px 16px 5px 32px;
					position:absolute;
					left: -29px;
					background-color:$Color;
					border-radius:0 4px 4px 0;

					&::before{
						position:absolute;
						top: 30px;
						left: 0;
						content: "";
						border-left:14px solid #efefef;
						border-top:14px solid #333;
					}


					a{
						color: #fff;
						font-size: 15px;
					}
				}
			}

			.article-content{
				clear: both;

				.intro-img{
					text-align: center;
					width: 100%;

					img{
						border-radius:5px;
						max-width: 100%;
					}
				}

				.intro-p{
					margin-top: 40px;

					p{
						line-height: 20px;
						margin: 10px 0;
						color: #444;
						font-size: 15px;
						line-height: 24px;
						overflow-wrap: break-word;
					    white-space: normal;
					    word-break: break-all;

						a{
							color: $Color;
						}
					}
				}

				.more{
					text-align: center;

					p{
						margin-top: 20px;
					}

					a{
						background-color:$Color;
						color: #fff;
						font-size: 14px;
						padding:6px 10px;
						border-radius:5px;
					}
				}
			}
		}
	}


	@include respond-to(medium){
		.article-list{
			width: 100%;

			.roate-date{
				display: none;
			}
		}
	}

</style>
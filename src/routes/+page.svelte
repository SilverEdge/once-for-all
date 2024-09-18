<script>
	import Footer from '../components/footer.svelte';
	let title = 'Once For All';
	/**
	 * @type {HTMLDivElement}
	 */
	let posts;
	let y = 0;

	import { fade } from 'svelte/transition';
	$: visible = !y;
</script>

<svelte:window bind:scrollY={y} />

<svelte:head>
	<title>{title}</title>
</svelte:head>

<div class="container"></div>
<div class="trees reflection" style="top: calc(-440px + {y * 0.5}px);"></div>
<div class="trees" style="top: calc(60px + {y * 0.5}px);"></div>
{#if visible}
	<div class="tag" in:fade out:fade style="top: calc(60px + {y * 0.5}px);padding:50px;text-align: center;">
		<h3>Proclaiming God's sacrificial love for all to all</h3>
		<button
			on:click={() => {
				posts.scrollIntoView({ behavior: 'smooth' });
			}}>Explore</button
		>
	</div>
{/if}

<div bind:this={posts} class="posts">
	<h1 class="postText">Posts Latest Series Videos</h1>
</div>

<Footer />

<style>
	.container {
		background: linear-gradient(-45deg, #f5e7cf, #46b2da, #23d5ab);
		/* background: linear-gradient(-45deg, #f5e7cf, #f5d5cf,  #4089a3); */
		background-size: 400% 400%;
		animation: gradient 20s ease infinite;
		height: 500px;
		width: 100%;
		overflow: hidden;
		position: absolute;
		top: 60px;
		right: 0px;
	}

	@keyframes gradient {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}

	.trees {
		mix-blend-mode: multiply;
		width: 100%;
		height: auto;
		background-image: url('../trees.jpg');
		height: 500px;
		width: 100%;
		position: absolute;
		right: 0px;
		background-size: cover;
		background-position: center;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.reflection {
		top: -440px;
		transform: scaleY(-1);
		-webkit-transform: scaleY(-1);
	}

	.tag {
		width: 100%;
		height: auto;
		height: 500px;
		width: 100%;
		position: absolute;
		right: 0px;
		background-size: cover;
		background-position: center;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		opacity: 90%;
		margin-top: 30px;
	}

	.tag button {
		padding-top: 10px;
		padding-right: 20px;
		padding-bottom: 10px;
		padding-left: 20px;
		margin-top: 20px;
		cursor: pointer;
	}

	.posts {
		scroll-margin-top: 60px;
		width: 100%;
		height: 1000px;
		position: absolute;
		top: 560px;
		left: 0px;
		background-color: #000;
	}

	.postText {
		position: absolute;
		top: 13px;
		left: 40px;
		cursor: pointer;
		color: #888;
	}
</style>

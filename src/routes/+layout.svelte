<script lang="ts">
	import '@picocss/pico';
	import 'iconify-icon';
	import { page } from '$app/stores';
	$: p = $page.params;
</script>

<div class="stretch">
	<header>
		<nav>
			<ul>
				<li>
					<a href="/">
						<iconify-icon icon="material-symbols:menu" />
					</a>
				</li>
			</ul>
			<ul>
				<li>
					<a href="/">
						{#if p.book}
							<kbd>{`Book ${p.book}`}</kbd>
						{:else}
							<kbd>The Iliad of Homer</kbd>
						{/if}
					</a>
				</li>
			</ul>
			<ul>
				<li>
					<a href="/info">
						<iconify-icon icon="mdi:information" />
					</a>
				</li>
			</ul>
		</nav>
	</header>
	<main class="container sticky">
		<slot />
	</main>
	<footer>
		<a href="/contact">
			<iconify-icon icon="material-symbols:mail-outline-rounded" />
		</a>
	</footer>
</div>

<style>
	.stretch {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		text-align: center;
	}
	.sticky {
		flex: 1;
	}
	iconify-icon {
		margin-left: 0.5rem;
		margin-right: 0.5rem;
		font-size: 2rem;
	}
</style>

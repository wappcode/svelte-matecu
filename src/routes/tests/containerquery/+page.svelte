<script lang="ts">
</script>

<div class="card">
	<div class="post-meta">
		<h2>Card title</h2>
		<p>My post details.</p>
	</div>
	<div class="post-excerpt">
		<div style="border: 1px solid green">
			<p>
				A preview of my <a href="https://example.com">blog post</a> about cats.
			</p>
		</div>
	</div>
</div>

<style>
	* {
		box-sizing: border-box;
		outline: none;
	}
	.post-meta {
		container-type: inline-size;
	}

	.post-excerpt {
		container-type: inline-size;
		container-name: excerpt;
		border: 1px solid red;
	}
	@container excerpt (max-width: 400px) {
		p {
			visibility: hidden;
		}
	}

	@container (max-width: 400px) {
		p {
			font-size: 2rem;
		}
	}
</style>

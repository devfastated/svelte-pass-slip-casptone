<script>
	let email = '';
	let password = '';
	let confirmpass = '';
	let error = false;
	let register = false;

	function handleAuthenticate() {
		if (!email || !password || (register && !confirmpass)) {
			error = true;
			return;
		}
	}
</script>

<div class="authContainer">
	<form action="">
		<h1>{register ? 'Register' : 'Log in'}</h1>
		{#if error}
			<p class="error">Not correct!</p>
		{/if}
		<label for="">
			<p class={email ? 'above' : 'center'}>Email</p>
			<input bind:value={email} type="email" name="" id="" placeholder="Email" />
		</label>

		<label for="">
			<p class={password ? 'above' : 'center'}>Password</p>
			<input bind:value={password} type="password" name="" id="" placeholder="Password" />
		</label>

		<label for="">
			<p class={confirmpass ? 'above' : 'center'}>Confirm password</p>
			<input
				bind:value={confirmpass}
				type="password"
				name=""
				id=""
				placeholder="Confirm password"
			/>
		</label>
		<button type="button">Submit</button>
	</form>
	<div>
		<p>or</p>
		{#if register}
			<div></div>
		{:else}
			<div></div>
		{/if}
	</div>
</div>

<style>
	.authContainer {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		flex: 1;
		padding: 24px;
	}

	form {
		display: flex;
		flex-direction: column;
		gap: 8px;
		width: 400px;
		max-width: 100%;
		margin: 0 auto;
	}
	form input {
		width: 100%;
	}

	form input {
		border: none;
		background: transparent;
		color: white;
		padding: 14px;
	}
	h1 {
		text-align: center;
		font-size: 3rem;
	}
	form Label {
		position: relative;
		border: 1px solid navy;
		border-radius: 5px;
	}
	form input:focus {
		border: none;
		outline: none;
		border: 8px 14px;
	}
	form button {
		background-color: navy;
		color: white;
		border: none;
		padding: 10px 0;
		border-radius: 5px;
		cursor: pointer;
		font-size: 1rem;
	}
	form button:hover {
		background: blue;
	}

	.above,
	.center {
		position: absolute;
		transform: translateY(-50%);
		pointer-events: none;
		color: white;
		border-radius: 4px;
		padding: 0 6px;
		font-size: 0.8rem;
	}

	.above {
		top: 0;
		left: 24px;
		background: navy;
		border: 1px solid blue;
		font-size: 0.7rem;
	}

	.center {
		top: 50%;
		left: 6px;
		border: 1px solid transparent;
		opacity: 0;
	}

	.error {
		color: coral;
		font-size: 0.9rem;
	}
</style>

<script>
	const phrases = [
		'No',
		'Are you sure? 🧐',
		'Really? 😒',
		'I will give you a bear 🐻',
		'I will give you roses 🌹',
		'Okay. Positive? 🤨',
		'Really? I mean it 🥺',
		'Pookie please? 🥺',
		'if you say no, I will cry 😭',
		'I will be sad 😢',
		'I will be very sad 😞',
		'I will be very very sad 😔',
		'I will be very very very sad 😕',
		'You are breaking my heart 💔',
		"okay fine. I'll stop asking 😞",
		"I'll just go cry in a corner 😭",
		'Kidding, did you really think I would cry? 😂',
		'I am a bear, I do not cry 😂',
		'Say yes. 🔪',
		"Don't make me angry. You won't like me when I am angry. 😡",
		'Please say yes. 🥺 👉👈',
		"Okay, I'm starting over. Will you be my valentine? 🥺"
	];

	let noCount = 0;
	let noCount__ = 0;
	let noButtonText = 'No';
	$: yesButtonSize = noCount__ * 10 + 16;

	let yesClicked = false;

	$: {
		if (noCount > phrases.length) {
			noCount = 0;
		} else {
			noButtonText = phrases[noCount];
		}
	}
</script>

<svelte:head>
	<title>Will you be my valentine?</title>
	<meta name="description" content="Will you be my valentine?" />
	<meta property="og:title" content="Will you be my valentine?" />
	<meta property="og:description" content="Will you be my valentine?" />
	<meta
		property="og:image"
		content="https://will-you-be-my-valentine.vercel.app/Love%20Bear%20Roses.gif"
	/>
	<meta property="og:url" content="https://will-you-be-my-valentine.vercel.app" />
	<meta property="og:type" content="website" />
	<meta property="og:site_name" content="Will you be my valentine?" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content="Will you be my valentine?" />
	<meta name="twitter:description" content="Will you be my valentine?" />
	<meta
		name="twitter:image"
		content="https://will-you-be-my-valentine.vercel.app/Love%20Bear%20Roses.gif"
	/>
	<meta name="twitter:url" content="https://will-you-be-my-valentine.vercel.app" />
	<meta name="twitter:site" content="@sveltejs" />
	<meta name="twitter:creator" content="@sveltejs" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="@sveltejs" />
	<meta name="twitter:creator" content="@sveltejs" />
	<meta name="twitter:image:alt" content="Will you be my valentine?" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="@sveltejs" />
	<meta name="twitter:creator" content="@sveltejs" />
	<meta name="twitter:image:alt" content="Will you be my valentine?" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="@sveltejs" />
	<meta name="twitter:creator" content="@sveltejs" />
	<meta name="twitter:image:alt" content="Will you be my valentine?" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="@sveltejs" />
</svelte:head>

<div class="h-screen flex items-center justify-center overflow-y-scroll">
	<div class="flex flex-col items-center gap-10">
		{#if !yesClicked}
			<img src="/Love Bear Roses.gif" alt="Love Bear Roses" class="size-64" />
			<h1 class="text-5xl font-bold text-center">will you be my valentine???</h1>
			<div class="flex flex-col lg:flex-row gap-10 items-center">
				<button
					style="font-size: {yesButtonSize}px;"
					class="bg-green-500 text-white px-4 py-2 rounded-md
                        active:scale-95 transition-transform duration-300 ease-in-out
                        "
					on:click={() => (yesClicked = true)}
					>Yes ❤️
				</button>
				<button
					class="bg-red-500 text-white px-4 py-2 rounded-md
                        active:scale-95 transition-transform duration-300 ease-in-out w-fit h-fit"
					on:click={() => {
						noCount++;
						noCount__++;
					}}>{noButtonText ? noButtonText : 'No?'}</button
				>
			</div>
		{:else}
			<img src="/Bear Kisses.gif" alt="Love Bear Roses" class="size-64" />
			<h1 class="text-5xl font-bold text-center">Yay! 🥳</h1>
		{/if}
	</div>
</div>

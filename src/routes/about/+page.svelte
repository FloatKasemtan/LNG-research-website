<script>
	import svg from '../../assets/undraw_online_articles_re_yrkj.svg';
	import Container from '../../lib/components/Container.svelte';
	import ParticleEffect from '$lib/landing/ParticleEffect.svelte';
</script>

<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>
<ParticleEffect className="fixed opacity-10 transition-all" />
<Container>
	<div class="px-1" data-sveltekit-prefetch="off">
		<div class="flex items-center justify-evenly">
			<div>
				<div class="text-6xl font-extrabold mb-20">
					<p>About this</p>
					<p class="text-blue-700">app</p>
				</div>
			</div>

			<img src={svg} alt="header" width="50%" />
		</div>

		<div id="content" class="py-24 text-lg">
			<span>
				<span class="text-blue-700 font-bold">This</span> is a website create for KMUTT course LNG320
				to represent data about the specific topic that interest each group.
			</span>
			<p>
				For our group we interested in Artificial Intelligence, so we set the research topic about
				Aritificial Intelligence in programming
			</p>
			<p class="mt-5">
				For data shown in the website, we collected and gather from our survey form and other
				website.
			</p>
			<p>We will not show name of surveyee for their privacy.</p>

			<p class="font-bold mt-5">References website</p>
			<ol>
				<li class="m-2">
					1.
					<a rel="external" href="https://geekflare.com/best-ai-powered-code-completion-tools"
						>Das, T. (2022, June 29). 9 Best AI-Powered Code Completion for Productive Development.
						Geekflare.
					</a>
				</li>
				<li class="m-2">
					2.
					<a
						rel="external"
						href="
				https://www.nytimes.com/2021/09/09/technology/codex-artificial-intelligence-coding.html"
						>Metz, C. (2021, September 10). A.I. Can Now Write Its Own Computer Code. That’s Good
						News for Humans. The New York Times.
					</a>
				</li>
				<li class="m-2">
					3.
					<a
						rel="external"
						href="https://blogs.microsoft.com/ai/how-ai-makes-developers-lives-easier-and-helps-everybody-learn-to-develop-software"
						>Roach, J. (2022, May 25). How AI makes developers’ lives easier, and helps everybody
						learn to develop software. The AI Blog.
					</a>
				</li>
				<li class="m-2">
					4. <a
						rel="external"
						href="https://devm.io/machine-learning/ai-software-development-174125"
						>Winkens, N. (2021, September 4). How AI Is Making Software Development Easier For
						Companies And Coders. Devmio - Expand Your Knowledge.
					</a>
				</li>
			</ol>
		</div>
	</div></Container
>

<style>
</style>

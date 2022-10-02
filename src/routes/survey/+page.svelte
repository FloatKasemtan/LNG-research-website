<script>
	import headerImage from '../../assets/big-brain.png';
</script>

<svelte:head>
	<title>Survey</title>
	<meta name="description" content="Information gather from survey" />
</svelte:head>
<div class="flex flex-col">
	<div class="flex items-center justify-center">
		<img src={headerImage} alt="undraw_svg" width="300" />
		<div>
			<div class="text-sm">LNG320</div>
			<div class="text-4xl">Data From Survey</div>
			<div>These data are mostly from KMUTT students</div>
		</div>
	</div>
	<div class="flex items-center my-10">
		<div class="flex-1 text-5xl font-extrabold">
			<p><span class="text-pink-500"> Who </span> has responeded out survey?</p>
		</div>
		<div class="flex flex-1 p-3">
			<p class="text-xl text-left">
				From the responses, most of the respondents are KMUTT students that are related with
				programming fields. We ask for their consent in order to use their personal information and
				responses on our website.
			</p>
		</div>
	</div>
	<div class="flex flex-col my-10 text-center">
		<p class="text-4xl font-extrabold">How long have they been in the programming field?</p>
		<p class="my-5 text-xl text-justify indent-10">
			Our responses show that <b>58.6%</b> of the respondents have been in the programming field for
			1-3 years. Another two groups of responses, which are the people who have been in programming
			for 3-5 years and more than 5 years, show the same result at <b>17.2%</b> of total
			respondents. The last group of respondents, which is the people who just started programming
			with less than 1 years of experience, have a total of <b>6.9%</b> of overall responses.
		</p>
	</div>
	<div class="flex flex-col text-center ">
		<p class="text-4xl font-extrabold">Have they ever used any AI software that helps coding?</p>
		<p class="my-5 text-xl text-justify indent-10">
			From our responses, <b>51.7%</b> of respondents that have used AI Software help them code. And
			for <b>48.3%</b> that haven’t used AI Software. That means almost a half of the respondents haven’t
			known or used AI Tools before. However, we believe that some of them might already know about the
			existence of AI Softwares but they’d rather use their own pure computer skills than ask AI for
			help. Some believe that their skills might be wasteful with AI compared to coding on their own
			which will make their skills become better and better.
		</p>
	</div>
	<div class="flex items-center my-20">
		<div class="flex-1 text-5xl font-extrabold">
			<p>What AI software have they used before?</p>
		</div>
		<div class="flex flex-1 p-3">
			<p class="text-xl text-left">
				Our responses showed that <b>93.3%</b> of respondents have been using
				<b><span class="text-violet-600"> Github Copilot.</span></b> We find it makes sense that most
				people are using Github Copilot because it is the most popular AI Software in comparison to others.
			</p>
		</div>
	</div>
	<div class="flex flex-col my-10 text-center">
		<p class="text-4xl font-extrabold">How long have they been using AI in coding?</p>
		<p class="my-5 text-xl text-justify indent-10">
			From our responses, <b>40%</b> of respondents have been using AI in coding for 1- 6 months, AI
			in coding began to be more and more since Github Copilot has been released, other responses,
			<b>13.3%</b> of respondents are using AI in coding for 6 - 12 months and <b>6.7%</b> of respondents
			use them more than a year. We can conclude that some respondents used AI for coding for a long
			time, but mostly people just started using it less than 6 months.
		</p>
	</div>
	<div class="flex flex-col my-10 text-center">
		<p class="text-4xl font-extrabold">How much they AI enhance your work?</p>
		<p class="my-5 text-xl text-justify indent-10">
			From the bar chart from our responses, <b>86.7%</b> of the respondents voted that AI really
			enhance their work, and enhance their productivity after they use AI with programming work So,
			we can say that AI can enhance our work and help them in programming work, and <b>13.4%</b> of
			the respondents voted that they satisfied with AI but unsure to use it seriously on their work.
		</p>
	</div>
	<div class="flex flex-col my-10 text-center">
		<p class="text-4xl font-extrabold">Reason why do they think it is helpful, or not</p>
		<p class="my-5 text-xl text-justify indent-10">
			Most people answer in positive terms, but there are some negative comments as well. This
			showed that it could not be necessarily for everyone using AI in coding. Respondent answered
			that he is working in the backend field and the AI will mostly give wrong suggestions. His
			hypothesis is that the backend field is less popular than the frontend field, making AI
			suggest at the frontend is better than the backend work. But as the percentage of positive
			answers is much higher than negative answers, we cannot disagree that it helps people to do
			their work, as some work requires a lot of boilerplate code which is not effective to write
			with coders themselves.
		</p>
	</div>
	<div class="flex flex-col my-10 text-center">
		<p class="text-4xl font-extrabold">Do they still want to continue using it?</p>
		<p class="my-5 text-xl text-justify indent-10">
			From the data that we collect, there are <b>60%</b> of people will continue using AI to help
			in coding, <b>26.7%</b> are not sure whether they will continue using it or not, and the rest are
			people who said no. According to the data, we can assume that using AI in coding helps most people
			to do their work, but in some fields of work it is not necessary to use it due to fewer data used
			for training AI making its accuracy lower.
		</p>
	</div>
</div>

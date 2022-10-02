<script>
	// @ts-nocheck
	import { Pie, Bar } from 'svelte-chartjs';
	import { data1, data2, data3, data4, data5, data6, data7, data8 } from '../../lib/graph/data';

	import {
		Chart as ChartJS,
		Title,
		Tooltip,
		Legend,
		ArcElement,
		CategoryScale,
		BarElement,
		LinearScale
	} from 'chart.js';
	import Container from '../../lib/components/Container.svelte';

	ChartJS.register(Title, Tooltip, Legend, ArcElement, CategoryScale, BarElement, LinearScale);
	import ParticleEffect from '$lib/landing/ParticleEffect.svelte';
</script>

<svelte:head>
	<title>Graph</title>
	<meta name="description" content="About this app" />
</svelte:head>

<ParticleEffect className="fixed opacity-10 transition-all" />

<Container>
	<div class="px-20 py-10 bg-white shadow ">
		<div class="flex">
			<div>
				<div class="text-sm">LNG320</div>
				<div class="text-4xl">Graph Data</div>
				<div class="mt-2">
					<p>
						The graphs below show the Percentages of the result from our survey that respondents
						have been submitted through Google Forms
					</p>
				</div>
				<div class="flex items-center pb-6 mt-6 border-b-2 border-b-gray-100">
					<div class="w-10/12">
						<Pie
							data={data1}
							options={{
								maintainAspectRatio: false
							}}
						/>
					</div>
					<div class="flex text-xl font-medium text-center">
						<p>Percentages of the respondents about time spent on programming field</p>
					</div>
				</div>
				<div class="flex items-center pb-6 mt-4 border-b-2 border-b-gray-100">
					<div class="flex text-xl font-medium text-center">
						<p>Percentages of people who have use AI software that helps them in their coding</p>
					</div>
					<div class="w-10/12">
						<Pie data={data2} options={{ maintainAspectRatio: false }} />
					</div>
				</div>
				<div class="flex justify-center mt-6">
					<p>
						-- This section shows the responses of people who have used AI software in their coding
						before --
					</p>
				</div>
				<div class="flex flex-col items-center pb-6 mt-4 border-b-2 border-b-gray-100">
					<div class="flex mt-2 mb-6 text-xl font-medium text-center">
						<p>Number of people who use different AI software in their coding</p>
					</div>
					<div class="w-10/12">
						<Bar data={data3} options={{ maintainAspectRatio: false }} height={350} />
					</div>
				</div>
				<div class="flex items-center pb-6 mt-4 border-b-2 border-b-gray-100">
					<div class="flex text-xl font-medium text-center">
						<p>Percentages of people about the time they have use AI software in coding</p>
					</div>
					<div class="w-10/12">
						<Pie data={data4} options={{ maintainAspectRatio: false }} />
					</div>
				</div>
				<div class="flex flex-col items-center pb-6 mt-4 border-b-2 border-b-gray-100">
					<div class="flex mt-2 mb-6 text-xl font-medium text-center">
						<p>Percentages of people about the rating on how AI help enhance programmer work</p>
					</div>
					<div class="w-10/12">
						<Bar data={data5} options={{ maintainAspectRatio: false }} height={350} />
					</div>
				</div>
				<div class="flex items-center pb-6 mt-4 border-b-2 border-b-gray-100">
					<div class="flex text-xl font-medium text-center">
						<p>
							Percentages of people about their opinion if they still want to continue using AI
							software in coding
						</p>
					</div>
					<div class="w-10/12">
						<Pie data={data6} options={{ maintainAspectRatio: false }} />
					</div>
				</div>
				<div class="flex justify-center mt-6">
					-- This section shows the responses of people who have not used AI software in their
					coding before --
				</div>
				<div class="flex flex-col items-center pb-6 mt-4 border-b-2 border-b-gray-100">
					<div class="flex mt-2 mb-6 text-xl font-medium text-center">
						<p>Number of people who have heard of any AI software that helps in coding</p>
					</div>
					<div class="w-10/12">
						<Bar data={data7} options={{ maintainAspectRatio: false }} height={350} />
					</div>
				</div>
				<div class="flex items-center pb-6 mt-4">
					<div class="flex text-xl font-medium text-center">
						<p>Percentages of people who would like to try using any AI software in coding</p>
					</div>
					<div class="w-10/12">
						<Pie data={data8} options={{ maintainAspectRatio: false }} />
					</div>
				</div>
			</div>
		</div>
	</div>
</Container>

<style>
</style>

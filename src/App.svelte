<script>
	import Tailwind from "./components/Tailwind.svelte";
	import IntersectionObserver from "svelte-intersection-observer";
	import AppearText from "./components/AppearText.svelte";
	import AppearBlock from "./components/AppearBlock.svelte";
	import TimeInfo from "./components/TimeInfo.svelte";
	export let name;
	let element;
	let intersecting;
</script>

<Tailwind />

<AppearText text="19.9.1991" color="text-red-200" />

<AppearText text="se stala významná událost" color="text-blue-200" />

<AppearBlock>
	<div class="flex flex-row">
		<div>1</div>
		<div class="flex-initial w-1/3">
			<img class="object-fill " src="otzi.jpeg" />
		</div>
		<div class="w-2/3">
			<p class="text-2xl text-left text-green-300 mx-8">Ötzi nalezen!</p>
			<p class="text text-left text-green-300 mx-8">
				Ötzi byl nalezen dne 19. září 1991 dvěma německými turisty v
				nadmořské výšce 3210 metrů na východním hřebeni hory
				Fineilspitze v Ötztalských Alpách na rakousko-italské hranici.
			</p>
			<p class="text text-left text-green-300 mx-8">
				Je nejstarší známou evropskou přirozenou lidskou mumií a nabízí
				nebývalý pohled na Evropany doby měděné.
			</p>
		</div>
	</div>
</AppearBlock>

<AppearText text="Ale 800 km daleko se stalo ještě něco" color="text-red-200" />

<AppearBlock>
	<iframe
		src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d960453.6444590689!2d17.028522060896698!3d48.646183395020614!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x476b548e5e16fe43%3A0xd0059dbdd49e7e58!2zOTIxIDAxIFBpZcWhxaVhbnksIFNsb3Zha2lh!5e0!3m2!1sen!2scz!4v1631867035262!5m2!1sen!2scz"
		width="400"
		height="450"
		style="border:0;"
		allowfullscreen=""
		loading="lazy"
	/>
</AppearBlock>

<AppearBlock>
	<div class="flex flex-row">
		<div>1</div>
		<div class="flex-initial w-1/3">
			<img class="object-fill " src="nemocnica_pn.jpeg" />
		</div>
		<div class="w-2/3">
			<p class="text-2xl text-left text-green-300 mx-8">
				Narodila se krásná holčička! / Narodilo sa krásne dievčatko!
			</p>
			<p class="text text-left text-green-300 mx-8">
				Dne 19.9.1991 se narodila neobvykle krásná holčička v piešťanské
				nemocnici. Ihned po porodu se rozhlédla a řekla "Jáj ?!"
			</p>
			<p class="text text-left text-green-300 mx-8">
				Dňa 19.9.1991 sa narodila neobvykle krásne dievčatko v
				piešťanskej nemocnici. Ihneď po pôrode sa rozhliadla a povedala
				"Jáj ?!"
			</p>
			<p class="text-sm text-left text-green-600 mx-8">
				<br /> (Tehdy bylo ještě ČSFR, takže se všechno psalo dvojjazyčně,
				aby se ti druzí neurazili)
			</p>
		</div>
	</div>
</AppearBlock>



<AppearBlock>
	<div class="flex flex-row">
				<img class="object-fill " src="tugendhatka.png" />
	</div>
</AppearBlock>
<AppearBlock>
	<div class="flex flex-row">
				<img class="object-fill " src="tugendhatka2.png" />
	</div>
</AppearBlock>

<AppearText text="A čas šel dál, a přidaly se úspěchy sportovní..." color="text-yellow-200" />

<AppearBlock>
	<div class="flex flex-row">
				<img class="object-fill " src="sagan.png" />
	</div>
</AppearBlock>

<AppearBlock>
	<div class="flex flex-row">
				<img class="object-fill " src="riding.png" />
	</div>
</AppearBlock>

<AppearText text="... a gastronomické!" size="text-3xl" color="text-yellow-200" />

<AppearBlock>
	<div class="flex flex-row">
				<img class="object-fill sm:scale-50 md:scale-75 " src="kolozvar.png" />
	</div>
</AppearBlock>

<AppearBlock>
	<div class="flex flex-row">
				<img class="object-fill " src="jidlo.png" />
	</div>
</AppearBlock>

<AppearText text="A kdo ví, kam to Lenka dotáhne v budoucnu!" color="text-green-400" />

<AppearBlock>
	<div class="flex flex-row">
				<img class="object-fill " src="elon.png" />
	</div>
</AppearBlock>

<AppearText text="Ale k věci. Už je čas slavit?" color="text-blue-400" />

<AppearBlock>
	<div class="flex flex-row">
			<TimeInfo/>
	</div>
</AppearBlock>

<AppearText text="A nejen k narozeninám si zazpívejme!" color="text-green-400" />

<!-- <AppearBlock>
	<p class="text text-yellow-600">Narozeninové karaoke! (in english)</p> <br/>
	<iframe width="560" height="315" src="https://www.youtube.com/embed/e9_0Gf84fa8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</AppearBlock> -->

<AppearBlock>
	<p class="text text-yellow-600">Narozeninové karaoke! (in english)</p> <br/>
	<div class="relative" style="padding-top: 56.25%">
		<!-- <div class="relative" style="padding-top: 56.25%"> -->
		<iframe src="https://www.youtube.com/embed/e9_0Gf84fa8" class="absolute inset-0 w-full h-full" frameborder="0"allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	  </div>
	
	<!-- <iframe width="560" height="315" src="https://www.youtube.com/embed/e9_0Gf84fa8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> -->
</AppearBlock>

<AppearText text="A to je vše. Díky za pozornost!"/>

<!-- <p class="text text-purple-500">Made with ♥ by @VIKMSTR</p> -->
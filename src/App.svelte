<script>
	import Tailwind from './components/Tailwind.svelte';
	import IntersectionObserver from "svelte-intersection-observer";
	import AppearText from "./components/AppearText.svelte"
	import AppearBlock from "./components/AppearBlock.svelte"

export let name
  let element;
  let intersecting;

  
  </script>
  

  <Tailwind />
<!-- <nav class="bg-blue-900 shadow-lg">
	<div class="container mx-auto">
	  <div class="sm:flex">
		<a href="#" class="text-white text-3xl font-bold p-3">APP LOGO</a>
		
		<!-- Menus -->
		<!-- <div class="ml-55 mt-4">
		  <ul class="text-white sm:self-center text-xl">
			<li class="sm:inline-block">
			  <a href="#" class="p-3 hover:text-red-900">About</a>
			</li>
			<li class="sm:inline-block">
			  <a href="#" class="p-3 hover:text-green-900">Services</a>
			</li>
			<li class="sm:inline-block">
			  <a href="#" class="p-3 hover:text-red-900">Blog</a>
			</li>
			<li class="sm:inline-block">
			  <a href="#" class="p-3 hover:text-red-900">Contact</a>
			</li>
		  </ul>
		</div>
  
	  </div>
	</div>
  </nav> --> 


<AppearText text="19.9.1991" color="text-red-200" />

<AppearText text="se stala významná událost" color="text-blue-200" />

<AppearBlock>
	<div class="flex flex-row">
		<div>1</div>
		<div class="flex-initial w-1/3"><img class="object-fill " src="otzi.jpeg"/> </div>
		<div class="w-2/3">	
			<p class="text-2xl text-left text-green-300 mx-8">Ötzi nalezen!</p>
			<p class="text text-left text-green-300 mx-8">Ötzi byl nalezen dne 19. září 1991 dvěma německými turisty v nadmořské výšce 3210 metrů na východním hřebeni hory Fineilspitze v Ötztalských Alpách na rakousko-italské hranici. </p>
			<p class="text text-left text-green-300 mx-8"> Je nejstarší známou evropskou přirozenou lidskou mumií a nabízí nebývalý pohled na Evropany doby měděné.  </p>
		</div>
	</div>
</AppearBlock>

<AppearText text="Ale 800km daleko se stalo ještě něco" color="text-red-200" />

<AppearBlock>
	<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d960453.6444590689!2d17.028522060896698!3d48.646183395020614!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x476b548e5e16fe43%3A0xd0059dbdd49e7e58!2zOTIxIDAxIFBpZcWhxaVhbnksIFNsb3Zha2lh!5e0!3m2!1sen!2scz!4v1631867035262!5m2!1sen!2scz" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
</AppearBlock>

<AppearBlock>
	<div class="flex flex-row">
		<div>1</div>
		<div class="flex-initial w-1/3"><img class="object-fill " src="nemocnica_pn.jpeg"/> </div>
		<div class="w-2/3">	
			<p class="text-2xl text-left text-green-300 mx-8">Narodila se krásná holčička! / Narodilo sa krásne dievčatko!</p>
			<p class="text text-left text-green-300 mx-8"> Dne 19.9.1991 se narodila neobvykle krásná holčička v piešťanské nemocnici. Ihned po porodu se rozhlédla a řekla "Jáj?!"</p>
			<p class="text text-left text-green-300 mx-8"> Dňa 19.9.1991 sa narodila neobvykle krásne dievčatko v piešťanskej nemocnici. Ihneď po pôrode sa rozhliadla a povedala "Jáj ?!"  </p>
			<p class="text-sm text-left text-green-600 mx-8"> <br/> (Tehdy bylo ještě ČSFR, takže se všechno psalo dvojjazyčně, aby se ti druzí neurazili) </p>
		</div>
	</div>
</AppearBlock>

  <div class="flex h-screen justify-center items-center">
    <div class="text-center"> <!-- ⬅️ THIS DIV WILL BE CENTERED -->
		<p class="text-center text-8xl align-middle text-green-300 uppercase">už se to blíží </p>
    </div>
  </div>

  <div class="flex h-screen justify-center items-center delay-500 duration-500 " class:intersecting>
	<div class="text-center"> <!-- ⬅️ THIS DIV WILL BE CENTERED -->
		<p class="text-center text-8xl align-middle text-green-300 uppercase">{intersecting ? "Element is in view" : "Element is not in view"}</p>
    </div>
</div>
	
	<IntersectionObserver
	{element}
	on:observe="{(e) => {
	  console.log(e.detail); // IntersectionObserverEntry
	  console.log(e.detail.isIntersecting); // true
	  if(e.detail.isIntersecting){
		e.detail.target.classList.add("animate-fadein")
		e.detail.target.classList.remove("opacity-0")

	  }else{
		e.detail.target.classList.add("opacity-0")
		e.detail.target.classList.remove("animate-fadein")
	  }
	  
	}}"
  >
	<div class="flex h-screen justify-center items-center delay-500 duration-500 intersecting opacity-0" class:intersecting bind:this="{element}">
	<div class="text-center">
		<p class="text-center text-8xl align-middle text-green-300 uppercase">Hello world
		</p>
		</div>
	</div>
  </IntersectionObserver>

  <div class="flex h-screen justify-center items-center">
    <div class="text-center"> <!-- ⬅️ THIS DIV WILL BE CENTERED -->
		<p class="text-center text-8xl align-middle text-yellow-300 uppercase">v září to rozzáří</p>
    </div>
  </div>
  <div class="flex h-screen justify-center items-center">
    <div class="text-center"> <!-- ⬅️ THIS DIV WILL BE CENTERED -->
		<p class="text-center text-8xl align-middle text-red-300 uppercase">tak prostě počkej, no</p>
    </div>
  </div>
  <div class="flex h-screen justify-center items-center">
    <div class="text-center"> <!-- ⬅️ THIS DIV WILL BE CENTERED -->
		<p class="text-center text-8xl align-middle text-blue-300 uppercase ">*chjo*</p>
    </div>
  </div>
  <div class="flex h-screen justify-center items-center">
    <div class="text-center"> <!-- ⬅️ THIS DIV WILL BE CENTERED -->
		<p class="text-center text-7xl align-middle text-orange-300 uppercase">ok, tady je zatím na zkrácení volné chvíle</p>
		<div class="flex justify-center content-center">
		<iframe class="flex justify-center content-center" width="640" height="480" src="https://www.youtube.com/embed/p3l7fgvrEKM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	</div>
    </div>
  </div>


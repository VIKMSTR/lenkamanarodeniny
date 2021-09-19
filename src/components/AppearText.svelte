<script>
    export let text = ""
    export let color = "text-green-300"
    import IntersectionObserver from "svelte-intersection-observer";
    let element;
  	let intersecting;
	export let size = "text-7xl"   
</script>

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
		<p class="text-center {size} align-middle {color} "> {text}
		</p>

	</div>
  </IntersectionObserver>

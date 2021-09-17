<script>
    import IntersectionObserver from "svelte-intersection-observer";
    let element;
  	let intersecting;
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
	<div class="text-center">
        <slot />
		</div>
	</div>
  </IntersectionObserver>

<script lang='ts'>

import { range, asyncScheduler } from 'rxjs';

//const src$ = of(1,2,3,4,5);
const src$ = range(1,5, asyncScheduler);

console.log("inicio");
src$.subscribe( console.log );
console.log("fin");

</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>

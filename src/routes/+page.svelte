<script lang='ts'>

import { Observable, Subscriber} from 'rxjs';
//import { Observer } from 'svelte-rxjs-observer';
const observer = {
	next: x => console.log('Observer got a next value: ' + x),
  error: err => console.error('Observer got an error: ' + err),
  complete: () => console.log('Observer got a complete notification'),
};

const intervalo$ = new Observable( Subscriber => {
	// Crear un contador, 1, 2, 3, 4, 5, ... n

	setInterval( () => {
		// cada segunto
	}, 1000); 
});

intervalo$.subscribe( num => console.log('Num: ', num) );
</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>

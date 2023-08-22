<script lang='ts'>

import { Observable, Subscriber} from 'rxjs';
	import { subscribe } from 'svelte/internal';
//import { Observer } from 'svelte-rxjs-observer';
const observer = {
	next: x => console.log('Observer got a next value: ' + x),
  error: err => console.error('Observer got an error: ' + err),
  complete: () => console.log('Observer got a complete notification'),
};

const intervalo$ = new Observable<number>( Subscriber => {
	// Crear un contador, 1, 2, 3, 4, 5, ... n

		let count = 0;	
		const interval = setInterval( () => {
		// cada segunto

		count++;
		Subscriber.next( count );
		
	}, 1000);

	setTimeout(() => {
		Subscriber.complete();
	}, 2500);

	return () => {
		clearInterval(interval);
		console.log('Intervalo destruido');
	} 
});

const subs1 = intervalo$.subscribe(observer);
const subs2 = intervalo$.subscribe(observer);
const subs3 = intervalo$.subscribe(observer);


setTimeout( ()=>{
	subs1.unsubscribe();
	subs2.unsubscribe();
	subs3.unsubscribe();

}, 3000);

</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>

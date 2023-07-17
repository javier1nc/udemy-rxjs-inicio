<script lang='ts'>

import { Observable, Subject } from 'rxjs';

const observer = {
	next: x => console.log('Observer got a next value: ' + x),
  error: err => console.error('Observer got an error: ' + err),
  complete: () => console.log('Observer got a complete notification'),
};

const intervalo$ = new Observable<number>( subs => {
	
	const intervalID = setInterval( 
		() => {
			subs.next( Math.random() );
		}, 1000
	);

	return () => {
		clearInterval( intervalID );
		console.log('Intervalo destruido');
	}

});


/**
* 1- Casteo multiple
* 2- Tambien es un observer
* 3- Next, erro y complete
*/

const subject$ = new Subject();
const subscription = intervalo$.subscribe( subject$ );

// const subs1 = intervalo$.subscribe( rnd => console.log('subs1: '+ rnd) );
// const subs2 = intervalo$.subscribe( rnd => console.log('subs2: '+ rnd) );

const subs1 = subject$.subscribe( observer );
const subs2 = subject$.subscribe( observer );

setTimeout( () => {
	
	subject$.next(10);
	
	subject$.complete();

	subscription.unsubscribe();
	
}, 3500);
</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>

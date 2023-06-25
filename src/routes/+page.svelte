<script lang='ts'>

import { Observable } from 'rxjs';
import { subscribe } from 'svelte/internal';

//const obs$ = Observable.create();
const obs$ = new Observable<string>( subs => {
	subs.next('Hola');
	subs.next('Mundo');
	
	subs.next('Hola');
	subs.next('Mundo');

	subs.complete();

	subs.next('Hola');
	subs.next('Mundo');
	
});

obs$.subscribe(console.log);

</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>

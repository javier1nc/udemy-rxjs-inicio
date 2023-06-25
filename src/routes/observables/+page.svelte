<script lang='ts'>

import { Observable} from 'rxjs';

const observer = {
	next: x => console.log('Observer got a next value: ' + x),
  error: err => console.error('Observer got an error: ' + err),
  complete: () => console.log('Observer got a complete notification'),
};
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

obs$.subscribe(observer);

// obs$.subscribe( 
// 	valor => console.log('next; ', valor),
// 	error => console.warn('error, ', error),
// 	() => console.info('Completado')
// );

</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>


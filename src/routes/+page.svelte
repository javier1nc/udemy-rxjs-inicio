<script lang='ts'>

import { interval, timer } from 'rxjs';

const observer = {
	next: val => console.log("next:", val),
	complete: () => console.log("complete"),
}

const hoyEn5 = new Date();
//hoyEn5.setSeconds( hoyEn5.getSeconts() + 5 );

const interval$ = interval(1000);
//const timer$ = timer(2000);
//const timer$ = timer(2000, 1000);

console.log(hoyEn5);
const timer$ = timer( hoyEn5 );

console.log("inicio");
//interval$.subscribe(observer);
timer$.subscribe(observer);
console.log("fin");

</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>

<script lang='ts'>

import { fromEvent } from 'rxjs';

/**
* Eventos del DOM
*/
// BUG!
const src1$ = fromEvent(document, 'click');
cosole.log(src1);

</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Curso RxJS</h1>
		<p>...</p>
	</div>
</div>

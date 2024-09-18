
<script lang="ts">
import type { PropType } from 'vue';
import type ICategoria from '../interfaces/ICategoria';

	export default {
		props: {
			categoria: { type: Object as PropType<ICategoria> , required: true}
		}
	}
</script>

<template>
	{{ categoria.nome }}
	{{ categoria.imagem }}
</template>

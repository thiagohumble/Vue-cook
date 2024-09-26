<script lang="ts">
	import Tag from './Tag.vue'
	export default {
		components: { Tag },
		props: {
			ingrediente: { type: String, required: true}
		},
		data() {
			return {
				selecionado: false, 
			}
		},
		methods: {
			aoClicar() {
				this.selecionado = !this.selecionado /*adicionar class ativa, para pintar laranja*/

				if (this.selecionado) { /*condição do selecionado inicia com falso*/
					this.$emit('adicionarIngrediente', this.ingrediente); /*adiciona o ingrediente na sua lista*/
				} else {
					this.$emit('removerIngrediente', this.ingrediente); /*remove o ingrediente na sua lista*/
				}
			}
		},
		emits: ['adicionarIngrediente', 'removerIngrediente']
	}

</script>

<template>
	<button class="ingrediente" v-on:click="aoClicar" :aria-pressed="selecionado">
		<Tag :texto="ingrediente" :ativa="selecionado" />
	</button>
</template>

<style scoped>
	.ingrediente {
		cursor: pointer;
	}
</style>
<template>
	<div class="backdrop" @click.self="closeModal">
		<div class="modal" :class="{sale: theme === 'sale'}"><slot></slot></div>
		<div class="actions">
			<slot name="links"></slot>
			</div>
	</div>
</template>

<script>
export default {
	props:['header','text', 'theme'],
	methods:{
		closeModal(){
			this.$emit('close')
		}
	}
}
</script>

<style scoped>
	.modal{
		width:400px;
		padding:20px;
		margin:100px auto;
		background:white;
		border-radius:10px;
	}

	.backdrop{
		top:0;
		position:fixed;
		background:rgba(0, 0, 0, 0.527);
		width:100%;
		height:100%;
	}

.modal .actions{
	text-align:center;
	margin: 30px 0 10px 0;
}


.modal .actions a{
	padding:8px;
	border: 1px solid #eee;
	border-radius:4px;
	text-decoration: none;
	margin:10px;
	color: #333;
}
	.modal.sale {
		color:white;
		background:crimson;
	}
</style>
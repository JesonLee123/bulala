<template>
<div id="app">
	<mt-header title="多个按钮">
		<router-link to="/" slot="left">
			<mt-button icon="back">返回</mt-button>
			<mt-button @click="handleClose">关闭</mt-button>
		</router-link>
		<mt-button icon="more" slot="right"></mt-button>
	</mt-header>
	<mt-index-list>
		<mt-index-section index="A">
			<mt-cell title="Aaron"></mt-cell>
			<mt-cell title="Alden"></mt-cell>
			<mt-cell title="Austin"></mt-cell>
		</mt-index-section>
		<mt-index-section index="B">
			<mt-cell title="Baldwin"></mt-cell>
			<mt-cell title="Braden"></mt-cell>
		</mt-index-section>
		<mt-index-section index="Z">
			<mt-cell title="Zack"></mt-cell>
			<mt-cell title="Zane"></mt-cell>
		</mt-index-section>
			<mt-index-section index="A">
			<mt-cell title="Aaron"></mt-cell>
			<mt-cell title="Alden"></mt-cell>
			<mt-cell title="Austin"></mt-cell>
		</mt-index-section>
		<mt-index-section index="B">
			<mt-cell title="Baldwin"></mt-cell>
			<mt-cell title="Braden"></mt-cell>
		</mt-index-section>
		<mt-index-section index="Z">
			<mt-cell title="Zack"></mt-cell>
			<mt-cell title="Zane"></mt-cell>
		</mt-index-section>
			<mt-index-section index="A">
			<mt-cell title="Aaron"></mt-cell>
			<mt-cell title="Alden"></mt-cell>
			<mt-cell title="Austin"></mt-cell>
		</mt-index-section>
		<mt-index-section index="B">
			<mt-cell title="Baldwin"></mt-cell>
			<mt-cell title="Braden"></mt-cell>
		</mt-index-section>
		<mt-index-section index="Z">
			<mt-cell title="Zack"></mt-cell>
			<mt-cell title="Zane"></mt-cell>
		</mt-index-section>
			<mt-index-section index="A">
			<mt-cell title="Aaron"></mt-cell>
			<mt-cell title="Alden"></mt-cell>
			<mt-cell title="Austin"></mt-cell>
		</mt-index-section>
		<mt-index-section index="B">
			<mt-cell title="Baldwin"></mt-cell>
			<mt-cell title="Braden"></mt-cell>
		</mt-index-section>
		<mt-index-section index="Z">
			<mt-cell title="Zack"></mt-cell>
			<mt-cell title="Zane"></mt-cell>
		</mt-index-section>
			<mt-index-section index="A">
			<mt-cell title="Aaron"></mt-cell>
			<mt-cell title="Alden"></mt-cell>
			<mt-cell title="Austin"></mt-cell>
		</mt-index-section>
		<mt-index-section index="B">
			<mt-cell title="Baldwin"></mt-cell>
			<mt-cell title="Braden"></mt-cell>
		</mt-index-section>
		<mt-index-section index="Z">
			<mt-cell title="Zack"></mt-cell>
			<mt-cell title="Zane"></mt-cell>
		</mt-index-section>
			<mt-index-section index="A">
			<mt-cell title="Aaron"></mt-cell>
			<mt-cell title="Alden"></mt-cell>
			<mt-cell title="Austin"></mt-cell>
		</mt-index-section>
		<mt-index-section index="B">
			<mt-cell title="Baldwin"></mt-cell>
			<mt-cell title="Braden"></mt-cell>
		</mt-index-section>
		<mt-index-section index="Z">
			<mt-cell title="Zack"></mt-cell>
			<mt-cell title="Zane"></mt-cell>
		</mt-index-section>
	</mt-index-list>
	
</div>
</template>

<script>

export default {
  data() {
    return {

	}
  }
}
</script>

<style lang="less">



</style>

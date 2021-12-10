<template>
	<main>
		<Button> Click! </Button>
	</main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Button from "~/components/Button.vue";

export default defineComponent({
	components: {
		Button,
	},
});
</script>

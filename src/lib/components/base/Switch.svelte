<script>
	import { Label } from '$lib/components/ui/label';
	import { Switch } from '$lib/components/ui/switch';
	export let label;
	export let value;
</script>

<div class="flex items-center space-x-2">
	<Switch id="airplane-mode" bind:checked={value} />
	<Label for="airplane-mode">{label}</Label>
</div>

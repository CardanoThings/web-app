<script lang="ts">
	import * as Select from '$lib/components/ui/select';
	export let value;
	export let label;
	export let options;
	$: selectedValue = options.find((f) => f.value == value)?.label ?? 'Select...';
</script>

<Select.Root
	onSelectedChange={(currentValue) => {
		value = currentValue.value;
	}}
	selected={options.find((f) => f.value == value)}
	typehead
>
	<Select.Trigger class="w-[180px]">
		<Select.Value placeholder="Select..." />
	</Select.Trigger>
	<Select.Content>
		<Select.Group>
			<Select.Label>{label}</Select.Label>
			{#each options as option}
				<Select.Item value={option.value} label={option.label}>{option.label}</Select.Item>
			{/each}
		</Select.Group>
	</Select.Content>
	<Select.Input name="label" bind:value />
</Select.Root>

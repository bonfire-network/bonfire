<script lang="ts">
	import PageInfo from '@view/PageInfo.svelte';
	import type { PageProps } from './$types';
	import { _ } from 'svelte-i18n';
	import Stack from '@view/Stack.svelte';
	import { getStores } from '#lib/context';
	import ToolsList from '@view/ToolsList.svelte';

	let { data }: PageProps = $props();
	let { tools } = getStores();
</script>

<PageInfo title={$_('your_blueprint')} description={$_('blueprint_description')} />

<Stack gap={1}>
	{#each data.blueprint.sections as section (section.id)}
		<div>
			<h2>{$_(`${section.id}`)}</h2>
			<p>{$_(`${section.id}_description`)}</p>
			{#if section.selected_tools?.length}
				<ToolsList
					tools={section.selected_tools.reduce((acc, id) => ({ ...acc, [id]: $tools[id] }), {})}
				/>
			{/if}
		</div>
	{/each}
</Stack>

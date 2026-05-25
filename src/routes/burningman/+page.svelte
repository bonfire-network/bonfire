<script lang="ts">
	/* eslint-disable svelte/no-at-html-tags */
	import { _ } from 'svelte-i18n';
	import Paper, { Title, Content } from '@smui/paper';
	import Stack from '@view/Stack.svelte';
	import PageInfo from '@view/PageInfo.svelte';
</script>

<PageInfo title={$_('burningman_title')} description={$_('bonfire_description')} />

<Stack gap={2}>
	<Paper>
		<Title>{$_('did_you_know')}</Title>
		<Content>
			<p>{@html $_('did_you_know_content')}</p>
		</Content>
	</Paper>
	<Paper>
		<Title>{$_('our_position')}</Title>
		<Content>
			<p>{@html $_('our_position_content')}</p>
		</Content>
	</Paper>
</Stack>

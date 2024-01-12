<script lang="ts">
import { availableLanguageTags, languageTag } from "../paraglide/runtime"
import { translatePath } from "$lib/i18n"
import { goto } from "$app/navigation"

</script>


<select on:change={(e) => goto(translatePath("/", e.target?.value))}>
	{#each availableLanguageTags as lang}
		<option value={lang} selected={lang === languageTag()}>{lang}</option>
	{/each}
</select>
<script lang="ts">
import { cn } from "$lib/utils";
import { Drawer as DrawerPrimitive } from "vaul-svelte";

type $$Props = DrawerPrimitive.TitleProps;

export let el: $$Props["el"] = undefined;
let className: $$Props["class"] = undefined;
export { className as class };
</script>

<DrawerPrimitive.Title
	bind:el
	class={cn("text-lg font-semibold leading-none tracking-tight", className)}
	{...$$restProps}
>
	<slot />
</DrawerPrimitive.Title>

<script lang="ts">
import { cn } from "$lib/utils";
import { ContextMenu as ContextMenuPrimitive } from "bits-ui";
import ChevronRight from "svelte-radix/ChevronRight.svelte";

type $$Props = ContextMenuPrimitive.SubTriggerProps & {
	inset?: boolean;
};
type $$Events = ContextMenuPrimitive.SubTriggerEvents;

let className: $$Props["class"] = undefined;
export let inset: $$Props["inset"] = undefined;
export { className as class };
</script>

<ContextMenuPrimitive.SubTrigger
	class={cn(
		"data-[highlighted]:bg-accent data-[state=open]:bg-accent data-[highlighted]:text-accent-foreground data-[state=open]:text-accent-foreground flex cursor-default select-none items-center rounded-sm px-2 py-1.5 text-sm outline-none",
		inset && "pl-8",
		className
	)}
	{...$$restProps}
	on:click
	on:keydown
	on:focusin
	on:focusout
	on:pointerleave
	on:pointermove
>
	<slot />
	<ChevronRight class="ml-auto h-4 w-4" />
</ContextMenuPrimitive.SubTrigger>

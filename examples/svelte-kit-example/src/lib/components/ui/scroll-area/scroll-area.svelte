<script lang="ts">
import { ScrollArea as ScrollAreaPrimitive } from "bits-ui";
import { Scrollbar } from ".";
import { cn } from "$lib/utils";

type $$Props = ScrollAreaPrimitive.Props & {
	orientation?: "vertical" | "horizontal" | "both";
	scrollbarXClasses?: string;
	scrollbarYClasses?: string;
};

let className: $$Props["class"] = undefined;
export { className as class };
export let orientation = "vertical";
export let scrollbarXClasses: string = "";
export let scrollbarYClasses: string = "";
</script>

<ScrollAreaPrimitive.Root {...$$restProps} class={cn("relative overflow-hidden", className)}>
	<ScrollAreaPrimitive.Viewport class="h-full w-full rounded-[inherit]">
		<ScrollAreaPrimitive.Content>
			<slot />
		</ScrollAreaPrimitive.Content>
	</ScrollAreaPrimitive.Viewport>
	{#if orientation === "vertical" || orientation === "both"}
		<Scrollbar orientation="vertical" class={scrollbarYClasses} />
	{/if}
	{#if orientation === "horizontal" || orientation === "both"}
		<Scrollbar orientation="horizontal" class={scrollbarXClasses} />
	{/if}
	<ScrollAreaPrimitive.Corner />
</ScrollAreaPrimitive.Root>

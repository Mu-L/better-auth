<script lang="ts">
import { Command as CommandPrimitive } from "cmdk-sv";
import { cn } from "$lib/utils";

type $$Props = CommandPrimitive.EmptyProps & {
	class?: string | null | undefined;
};
let className: string | undefined | null = undefined;
export { className as class };
</script>

<CommandPrimitive.Empty class={cn("py-6 text-center text-sm", className)} {...$$restProps}>
	<slot />
</CommandPrimitive.Empty>

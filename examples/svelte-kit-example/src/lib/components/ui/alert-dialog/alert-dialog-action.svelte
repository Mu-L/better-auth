<script lang="ts">
import { cn } from "$lib/utils";
import { AlertDialog as AlertDialogPrimitive } from "bits-ui";
import { buttonVariants } from "../button";

type $$Props = AlertDialogPrimitive.ActionProps;
type $$Events = AlertDialogPrimitive.ActionEvents;

let className: $$Props["class"] = undefined;
export { className as class };
</script>

<AlertDialogPrimitive.Action
	class={cn(buttonVariants(), className)}
	{...$$restProps}
	on:click
	on:keydown
	let:builder
>
	<slot {builder} />
</AlertDialogPrimitive.Action>

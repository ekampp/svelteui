<script lang="ts">
	import useStyles from './Skeleton.styles';
	import { Box } from '../Box';
	import type { SkeletonProps as $$SkeletonProps } from './Skeleton.styles';

	interface $$Props extends $$SkeletonProps {}

	export let use: $$Props['use'] = [],
		element: $$Props['element'] = undefined,
		className: $$Props['className'] = '',
		override: $$Props['override'] = {},
		visible: $$Props['visible'] = true,
		height: $$Props['height'] = 'auto',
		width: $$Props['width'] = 100,
		circle: $$Props['circle'] = null,
		radius: $$Props['radius'] = null,
		animate: $$Props['animate'] = true;
	export { className as class };

	$: ({ cx, getStyles } = useStyles({ animate, circle, height, radius, width }));
</script>

<Box
	bind:element
	class={cx(className, { visible }, getStyles({ css: override }))}
	{use}
	{...$$restProps}
>
	<slot />
</Box>

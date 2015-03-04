
# Grid
* [Overview](#overview)
* [Nested Grids](#nested-grids)
* [weight](#weight)
* [Spaces](#spaces)
* [Styling](#styling)



## Overview
The grid control is the main container control used in remotes. It has rows, 
where each row contains one or more controls laid out in columns. A layout always 
contains a grid control by default, so you can start by adding rows directly.

	<layout>
		<row>
			<button text="a" />
			<button text="b" />
		</row>
		<row>
			<button text="c" />
			<button text="d" />
		</row>
	</layout>



## Nested Grids
Grids can also contain nested grids to create more complicated layouts.

	<layout>
		<row>
			<button text="a" />
			<grid>
				<row>
					<button text="b" />
				</row>
				<row>
					<button text="c" />
				</row>
			</grid>
			<button text="d" />
		</row>
	</layout>



## Weight
Use weight to control the width and height of cells. By default cells
expand to fill up all available space equally. You can use weights to
redistribute how the space is used up by the different cells. 

	<layout>
		<row>
			<button text="a" weight="1" />
			<button text="b" weight="2" />
		</row>
	</layout>

You can also apply weights to rows to redistribute their heights.

	<layout>
		<row weight="1">
			<button text="a" />
		</row>
		<row weight="2">
			<button text="a" />
		</row>
	</layout>

Use ``wrap`` to make cells wrap the size of the their contents.

	<layout>
		<row>
			<button text="a" weight="wrap" />
			<button text="b" />
		</row>
	</layout>



## Spaces
Spaces can be used to create empty cells.

	<layout>
		<row>
			<button text="a" />
			<space />
			<button text="b" />
		</row>
	</layout>



## Styling
See the [styling](styling.md) page for more details.



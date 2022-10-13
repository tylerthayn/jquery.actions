# jquery.actions
jQuery extensions supporting element action triggers and handlers

## Installation

```sh
npm install @tyler.thayn/jquery.actions
```

## Usage

```js
require(['jquery', '../jquery.actions.js'], ($) => {
	$(() => {
		$('.Test').ActionHandler('Show', $.ActionHandlers.Show)
		$('.Test').ActionHandler('Hide', $.ActionHandlers.Hide)
		$('.Test').ActionHandler('Toggle', $.ActionHandlers.Toggle)
		$('.Test').ActionHandler('Bg', function () {
			$(this).css('background-color', '#'+(Math.random()*0xFFFFFF<<0).toString(16))	
		})

		$('button.Hide').on('click', () => {$('.Test').Action('Hide', 'bounce')})
		$('button.Show').on('click', () => {$('.Test').Action('Show', 'pulsate')})
		$('button.Toggle').on('click', () => {$('.Test').Action('Toggle', 'fade')})
		$('button.Bg').on('click', () => {$('.Test').Action('Bg')})
	})
})
```

```js
fetch('https://cdn.jsdelivr.net/npm/@tyler.thayn/jquery.actions@latest/jquery.actions.js').then(t => t.text()).then(eval)
```

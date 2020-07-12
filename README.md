# Modal Window

Simple modal window for Vue.js applications that handles outside clicks, `Escape` key and `X-mark` for closing and allows arbitrary body content

![VB-preview](https://altrusl.github.io/vuesence-modal-window/vmw.gif)

# How to use

You can install it via `npm` 

```bash
npm install @vuesence/modal-window --save
```

or just copy-paste `ModalWindow.vue` component code into your Vue.js project

All the props (`close-on-escape`, `close-on-outside-click`, `show-x-mark`) are optional. 
Below listed their default values

```html
<template>
	<div id="app">
		<p>Click the button to open modal window</p>
		<button @click="showModal = true">Open Modal</button>		
		<modal-window
			:visible="showModal"
			:close-on-escape="true"
			:close-on-outside-click="true"
			:show-x-mark="true"
			@close="showModal = false"
		>
			<h2>Modal window</h2>
			<p>Here be the content</p>
		</modal-window>
	</div>
</template>
```

```javascript
import ModalWindow from "@vuesence/modal-window.vue";
...
	data() {
		return {
			showModal: false
		};
	}
```



## Demo

<a href="https://altrusl.github.io/vuesence-modal-window/" target="_blank">https://altrusl.github.io/vuesence-modal-window/</a>


## Playground

Try it on <a href="https://codesandbox.io/s/cloud-sync-button-hv9dr" target="_blank">codesandbox.io</a>

<!-- > ! The version on `codesandbox.io` might be slightly out of date -->


## Check out my other Vue.js components

- <a href="https://github.com/altrusl/vuesence-book" target="_blank">Vuesence book</a> - minimalistic Vue.js based documentation system component
- <a href="https://github.com/altrusl/vuesence-sliding-header" target="_blank">Sliding header</a> - Vue.js component representing sliding header (or two different headers)


<img src="https://imgur.com/A92i02A.png" />
You like Vuesence Modal Window? Star it and <a href="https://twitter.com/vuesence/status/1280130154090704896?s=20">retweet it!</a>

-------

## Troubleshooting

Any bugs, issues, feature and pull requests are welcome

Please use GitHub's issue reporter or send me an <a href="mailto:ruslan.makarov@gmail.com">email</a>


## Contribution

Contribution is always welcome and recommended. Here is how:

-   Fork the repository
-   Clone to your machine
-   Make your changes
-   Create a pull request

## License

**@vuesence/cloud-sync-button** package is freely distributable under the terms of the [MIT license](LICENSE).

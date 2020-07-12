# Modal Window

Simple Modal window Vue.js component that takes care of overlay, centering, animation, outside click/`Escape` key/`X-mark` closing and allows you to concentrate on its content only

![VB-preview](https://altrusl.github.io/vuesence-modal-window/vmw.gif)

# How to use

You can install it via `npm` 

```bash
npm install @vuesence/modal-window --save
```
or just copy-paste `ModalWindow.vue` component code into your Vue.js project

### Usage:

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
import ModalWindow from "@vuesence/modal-window";
...
	data() {
		return {
			showModal: false
		};
	}
```

All the props (`close-on-escape`, `close-on-outside-click`, `show-x-mark`) are optional. 
Above listed their default values

There can be several instances of the `ModalWindow.vue`

Styling and animation can be customized - check out `ModalWindow.vue`'s `<style>` section for CSS class names

## Demo

<a href="https://altrusl.github.io/vuesence-modal-window/" target="_blank">https://altrusl.github.io/vuesence-modal-window/</a>


## Playground

Try it on <a href="https://codesandbox.io/s/modal-window-kq9cw" target="_blank">codesandbox.io</a>

<!-- > ! The version on `codesandbox.io` might be slightly out of date -->


## Check out my other Vue.js components

- <a href="https://github.com/altrusl/vuesence-book" target="_blank">Vuesence book</a> - minimalistic Vue.js based documentation component
- <a href="https://github.com/altrusl/vuesence-sliding-header" target="_blank">Sliding header</a> - Vue.js component representing sliding header (or two different headers)
- <a href="https://github.com/altrusl/vuesence-cloud-sync-button" target="_blank">Cloud Sync Button</a> - a button with cloud synchronization animation
<!-- - <a href="https://github.com/altrusl/vuesence-modal-window" target="_blank">Modal Window</a> - simple lightweight Modal Window Vue.js component -->

<img src="https://imgur.com/A92i02A.png" />
You like Vuesence Modal Window? Star it and <a href="https://twitter.com/vuesence/status/1282213709918732289?s=20">retweet it!</a>

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

**@vuesence/modal-window** package is freely distributable under the terms of the [MIT license](LICENSE).

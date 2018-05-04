# ui-logger-dom

![](https://img.shields.io/badge/ui--logger--dom-v1.0.0-green.svg)

Simple utility to log information using the DOM (browser) instead of the console.

## 1. Installation

~$ `npm install -s ui-logger-dom`

## 2. Usage

##### Step 1. Include the javascript and the css files in your HTML:

```html
 <script src="node_modules/ui-logger-dom/src/ui-logger-dom.js"></script>
 <link rel="stylesheet" type="text/css" href="node_modules/ui-logger-dom/src/ui-logger-dom.css" />
```

##### Step 2. Instantiate a UILogger instance

```js
var logger = new UILogger();
```

##### Step 3. Make it appear

```js
logger.show();
```

##### Step 4. Log your messages

```js
logger.log("This is a message");
```

##### Step 5. For further customization (which is considerable recommended), edit the CSS file at:

`node_modules/ui-logger-dom/src/ui-logger-dom.css`

##### or simply, override the CSS classes:

`.ui-logger-panel`

`.ui-logger-message`

## 3. API

----

**Method:** `{UILogger}._`

**Type:** `{Object}`

**Description:** Holds the internal data of the `{UILogger}` instance.

----

**Method:** `{UILogger}.show()`

**Type:** `{Function}`

**Returns:** `{UILogger}`

**Description:** Appends the `{UILogger}._.panel`, which is an `{HTMLElement}`, into the `document.body`.

**Example:** see the `Usage > Step 2` section of this document.

----

**Method:** `{UILogger}.hide()`

**Type:** `{Function}`

**Returns:** `{UILogger}`

**Description:** Sets to `display: none` the `{UILogger}._.panel`.

**Example:** 

```js
(new UILogger()).show().hide();
```

----

**Method:** `{UILogger}.log(String:message[, Boolean:isHTML])`

**Type:** `{Function}`

**Parameter:** `{String} message.` The message to be logged. 

**Parameter:** `{Boolean} isHTML.` Tells if the message is HTML, or plain text. By default, this is `false`, so the HTML is escaped. Pass `true` if you want to log an HTML message instead.

**Returns:** `{UILogger}`

**Description:** Logs a message through the current `{UILogger}` instance.

**Example:** 

```js
var logger = new UILogger();
logger.show().log("This is a plain text").log("This is <b>NOT</b> a plain text, but <b>HTML</b> text", true);
```

----

**Method:** `{UILogger}.close()`

**Type:** `{Function}`

**Returns:** `{void}`

**Description:** Destroys the current `{UILogger}` instance (removes the `{UILogger}._.panel` from the DOM.

**Example:** 

```js
var logger = new UILogger();
logger.show();
logger.log("This is a plain text");
logger.close();
```

## 4. Conclusion

A very simple tool, but it can be useful for different tools for the browser. 

Highly recommended to customize the styles by your own.

# animation HTML elements without Javascript or Flash
## html
```
<h1>Hello World One!</h1>
<h2>Hello World Two!</h2>
<h3>Hello World Three!</h3>
<h4>Hello World Three!</h4>
<div class="tail"></div>
<div class="box"></div>
```

## css
```
h1 {
    /* animation: name duration options */
    animation: example1 1s infinite alternate;
}

@keyframes example1 {
    from { font-size: 5pt; }
    to { font-size: 10pt; }
}

h2 {
    animation: example2 1s infinite alternate;
}

@keyframes example2 {
    from { transform: scaleX(0.5); }
    to { transform: scaleX(1); }
}

h3 {
    animation: example3 1s infinite alternate;
}

@keyframes example3 {
    from { transform: translate(-20px, -20px); }
    to { transform: translate(20px, 20px); }
}

h4 {
    animation: example4 3s infinite alternate;
}

/* transform by percentage of 3 seconds */
@keyframes example4 {
	0% { transform: scaley(1); }
	2% { transform: scaley(0.2); }
	4% { transform: scaley(1); }
	6% { transform: scaley(0.2); }
	8% { transform: scaley(1); }
	100% { transform: scaley(1); }
}

.tail{
    /* hack for make a square by css */
	width: 0;
	height: 0;

	border: solid 40px black;

	border-left-color: transparent;
	border-right-color: transparent;
	border-top-color: transparent;
}

.box{
	width: 80px;
	height: 30px;
	background-color: gray;
	border-radius: 10px;
	padding: 2px;

	cursor: grab;

	position: relative;
}

.box::before {
	content: '';
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: inherit;
	border-radius: inherit;

	transition: all 0.4s;
}

.box:active::before {
	transform: scale(1.1);
}

```
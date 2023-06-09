<html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"/><title>Technologies to Learn - Summer</title><style>
/* cspell:disable-file */
/* webkit printing magic: print all background colors */
html {
	-webkit-print-color-adjust: exact;
}
* {
	box-sizing: border-box;
	-webkit-print-color-adjust: exact;
}

html,
body {
	margin: 0;
	padding: 0;
}
@media only screen {
	body {
		margin: 2em auto;
		max-width: 900px;
		color: rgb(55, 53, 47);
	}
}

body {
	line-height: 1.5;
	white-space: pre-wrap;
}

a,
a.visited {
	color: inherit;
	text-decoration: underline;
}

.pdf-relative-link-path {
	font-size: 80%;
	color: #444;
}

h1,
h2,
h3 {
	letter-spacing: -0.01em;
	line-height: 1.2;
	font-weight: 600;
	margin-bottom: 0;
}

.page-title {
	font-size: 2.5rem;
	font-weight: 700;
	margin-top: 0;
	margin-bottom: 0.75em;
}

h1 {
	font-size: 1.875rem;
	margin-top: 1.875rem;
}

h2 {
	font-size: 1.5rem;
	margin-top: 1.5rem;
}

h3 {
	font-size: 1.25rem;
	margin-top: 1.25rem;
}

.source {
	border: 1px solid #ddd;
	border-radius: 3px;
	padding: 1.5em;
	word-break: break-all;
}

.callout {
	border-radius: 3px;
	padding: 1rem;
}

figure {
	margin: 1.25em 0;
	page-break-inside: avoid;
}

figcaption {
	opacity: 0.5;
	font-size: 85%;
	margin-top: 0.5em;
}

mark {
	background-color: transparent;
}

.indented {
	padding-left: 1.5em;
}

hr {
	background: transparent;
	display: block;
	width: 100%;
	height: 1px;
	visibility: visible;
	border: none;
	border-bottom: 1px solid rgba(55, 53, 47, 0.09);
}

img {
	max-width: 100%;
}

@media only print {
	img {
		max-height: 100vh;
		object-fit: contain;
	}
}

@page {
	margin: 1in;
}

.collection-content {
	font-size: 0.875rem;
}

.column-list {
	display: flex;
	justify-content: space-between;
}

.column {
	padding: 0 1em;
}

.column:first-child {
	padding-left: 0;
}

.column:last-child {
	padding-right: 0;
}

.table_of_contents-item {
	display: block;
	font-size: 0.875rem;
	line-height: 1.3;
	padding: 0.125rem;
}

.table_of_contents-indent-1 {
	margin-left: 1.5rem;
}

.table_of_contents-indent-2 {
	margin-left: 3rem;
}

.table_of_contents-indent-3 {
	margin-left: 4.5rem;
}

.table_of_contents-link {
	text-decoration: none;
	opacity: 0.7;
	border-bottom: 1px solid rgba(55, 53, 47, 0.18);
}

table,
th,
td {
	border: 1px solid rgba(55, 53, 47, 0.09);
	border-collapse: collapse;
}

table {
	border-left: none;
	border-right: none;
}

th,
td {
	font-weight: normal;
	padding: 0.25em 0.5em;
	line-height: 1.5;
	min-height: 1.5em;
	text-align: left;
}

th {
	color: rgba(55, 53, 47, 0.6);
}

ol,
ul {
	margin: 0;
	margin-block-start: 0.6em;
	margin-block-end: 0.6em;
}

li > ol:first-child,
li > ul:first-child {
	margin-block-start: 0.6em;
}

ul > li {
	list-style: disc;
}

ul.to-do-list {
	padding-inline-start: 0;
}

ul.to-do-list > li {
	list-style: none;
}

.to-do-children-checked {
	text-decoration: line-through;
	opacity: 0.375;
}

ul.toggle > li {
	list-style: none;
}

ul {
	padding-inline-start: 1.7em;
}

ul > li {
	padding-left: 0.1em;
}

ol {
	padding-inline-start: 1.6em;
}

ol > li {
	padding-left: 0.2em;
}

.mono ol {
	padding-inline-start: 2em;
}

.mono ol > li {
	text-indent: -0.4em;
}

.toggle {
	padding-inline-start: 0em;
	list-style-type: none;
}

/* Indent toggle children */
.toggle > li > details {
	padding-left: 1.7em;
}

.toggle > li > details > summary {
	margin-left: -1.1em;
}

.selected-value {
	display: inline-block;
	padding: 0 0.5em;
	background: rgba(206, 205, 202, 0.5);
	border-radius: 3px;
	margin-right: 0.5em;
	margin-top: 0.3em;
	margin-bottom: 0.3em;
	white-space: nowrap;
}

.collection-title {
	display: inline-block;
	margin-right: 1em;
}

.simple-table {
	margin-top: 1em;
	font-size: 0.875rem;
	empty-cells: show;
}
.simple-table td {
	height: 29px;
	min-width: 120px;
}

.simple-table th {
	height: 29px;
	min-width: 120px;
}

.simple-table-header-color {
	background: rgb(247, 246, 243);
	color: black;
}
.simple-table-header {
	font-weight: 500;
}

time {
	opacity: 0.5;
}

.icon {
	display: inline-block;
	max-width: 1.2em;
	max-height: 1.2em;
	text-decoration: none;
	vertical-align: text-bottom;
	margin-right: 0.5em;
}

img.icon {
	border-radius: 3px;
}

.user-icon {
	width: 1.5em;
	height: 1.5em;
	border-radius: 100%;
	margin-right: 0.5rem;
}

.user-icon-inner {
	font-size: 0.8em;
}

.text-icon {
	border: 1px solid #000;
	text-align: center;
}

.page-cover-image {
	display: block;
	object-fit: cover;
	width: 100%;
	max-height: 30vh;
}

.page-header-icon {
	font-size: 3rem;
	margin-bottom: 1rem;
}

.page-header-icon-with-cover {
	margin-top: -0.72em;
	margin-left: 0.07em;
}

.page-header-icon img {
	border-radius: 3px;
}

.link-to-page {
	margin: 1em 0;
	padding: 0;
	border: none;
	font-weight: 500;
}

p > .user {
	opacity: 0.5;
}

td > .user,
td > time {
	white-space: nowrap;
}

input[type="checkbox"] {
	transform: scale(1.5);
	margin-right: 0.6em;
	vertical-align: middle;
}

p {
	margin-top: 0.5em;
	margin-bottom: 0.5em;
}

.image {
	border: none;
	margin: 1.5em 0;
	padding: 0;
	border-radius: 0;
	text-align: center;
}

.code,
code {
	background: rgba(135, 131, 120, 0.15);
	border-radius: 3px;
	padding: 0.2em 0.4em;
	border-radius: 3px;
	font-size: 85%;
	tab-size: 2;
}

code {
	color: #eb5757;
}

.code {
	padding: 1.5em 1em;
}

.code-wrap {
	white-space: pre-wrap;
	word-break: break-all;
}

.code > code {
	background: none;
	padding: 0;
	font-size: 100%;
	color: inherit;
}

blockquote {
	font-size: 1.25em;
	margin: 1em 0;
	padding-left: 1em;
	border-left: 3px solid rgb(55, 53, 47);
}

.bookmark {
	text-decoration: none;
	max-height: 8em;
	padding: 0;
	display: flex;
	width: 100%;
	align-items: stretch;
}

.bookmark-title {
	font-size: 0.85em;
	overflow: hidden;
	text-overflow: ellipsis;
	height: 1.75em;
	white-space: nowrap;
}

.bookmark-text {
	display: flex;
	flex-direction: column;
}

.bookmark-info {
	flex: 4 1 180px;
	padding: 12px 14px 14px;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
}

.bookmark-image {
	width: 33%;
	flex: 1 1 180px;
	display: block;
	position: relative;
	object-fit: cover;
	border-radius: 1px;
}

.bookmark-description {
	color: rgba(55, 53, 47, 0.6);
	font-size: 0.75em;
	overflow: hidden;
	max-height: 4.5em;
	word-break: break-word;
}

.bookmark-href {
	font-size: 0.75em;
	margin-top: 0.25em;
}

.sans { font-family: ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol"; }
.code { font-family: "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace; }
.serif { font-family: Lyon-Text, Georgia, ui-serif, serif; }
.mono { font-family: iawriter-mono, Nitti, Menlo, Courier, monospace; }
.pdf .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK JP'; }
.pdf:lang(zh-CN) .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK SC'; }
.pdf:lang(zh-TW) .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK TC'; }
.pdf:lang(ko-KR) .sans { font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK KR'; }
.pdf .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK JP'; }
.pdf:lang(zh-CN) .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK SC'; }
.pdf:lang(zh-TW) .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK TC'; }
.pdf:lang(ko-KR) .code { font-family: Source Code Pro, "SFMono-Regular", Menlo, Consolas, "PT Mono", "Liberation Mono", Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK KR'; }
.pdf .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK JP'; }
.pdf:lang(zh-CN) .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK SC'; }
.pdf:lang(zh-TW) .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK TC'; }
.pdf:lang(ko-KR) .serif { font-family: PT Serif, Lyon-Text, Georgia, ui-serif, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Serif CJK KR'; }
.pdf .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK JP'; }
.pdf:lang(zh-CN) .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK SC'; }
.pdf:lang(zh-TW) .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK TC'; }
.pdf:lang(ko-KR) .mono { font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK KR'; }
.highlight-default {
	color: rgba(55, 53, 47, 1);
}
.highlight-gray {
	color: rgba(120, 119, 116, 1);
	fill: rgba(120, 119, 116, 1);
}
.highlight-brown {
	color: rgba(159, 107, 83, 1);
	fill: rgba(159, 107, 83, 1);
}
.highlight-orange {
	color: rgba(217, 115, 13, 1);
	fill: rgba(217, 115, 13, 1);
}
.highlight-yellow {
	color: rgba(203, 145, 47, 1);
	fill: rgba(203, 145, 47, 1);
}
.highlight-teal {
	color: rgba(68, 131, 97, 1);
	fill: rgba(68, 131, 97, 1);
}
.highlight-blue {
	color: rgba(51, 126, 169, 1);
	fill: rgba(51, 126, 169, 1);
}
.highlight-purple {
	color: rgba(144, 101, 176, 1);
	fill: rgba(144, 101, 176, 1);
}
.highlight-pink {
	color: rgba(193, 76, 138, 1);
	fill: rgba(193, 76, 138, 1);
}
.highlight-red {
	color: rgba(212, 76, 71, 1);
	fill: rgba(212, 76, 71, 1);
}
.highlight-gray_background {
	background: rgba(241, 241, 239, 1);
}
.highlight-brown_background {
	background: rgba(244, 238, 238, 1);
}
.highlight-orange_background {
	background: rgba(251, 236, 221, 1);
}
.highlight-yellow_background {
	background: rgba(251, 243, 219, 1);
}
.highlight-teal_background {
	background: rgba(237, 243, 236, 1);
}
.highlight-blue_background {
	background: rgba(231, 243, 248, 1);
}
.highlight-purple_background {
	background: rgba(244, 240, 247, 0.8);
}
.highlight-pink_background {
	background: rgba(249, 238, 243, 0.8);
}
.highlight-red_background {
	background: rgba(253, 235, 236, 1);
}
.block-color-default {
	color: inherit;
	fill: inherit;
}
.block-color-gray {
	color: rgba(120, 119, 116, 1);
	fill: rgba(120, 119, 116, 1);
}
.block-color-brown {
	color: rgba(159, 107, 83, 1);
	fill: rgba(159, 107, 83, 1);
}
.block-color-orange {
	color: rgba(217, 115, 13, 1);
	fill: rgba(217, 115, 13, 1);
}
.block-color-yellow {
	color: rgba(203, 145, 47, 1);
	fill: rgba(203, 145, 47, 1);
}
.block-color-teal {
	color: rgba(68, 131, 97, 1);
	fill: rgba(68, 131, 97, 1);
}
.block-color-blue {
	color: rgba(51, 126, 169, 1);
	fill: rgba(51, 126, 169, 1);
}
.block-color-purple {
	color: rgba(144, 101, 176, 1);
	fill: rgba(144, 101, 176, 1);
}
.block-color-pink {
	color: rgba(193, 76, 138, 1);
	fill: rgba(193, 76, 138, 1);
}
.block-color-red {
	color: rgba(212, 76, 71, 1);
	fill: rgba(212, 76, 71, 1);
}
.block-color-gray_background {
	background: rgba(241, 241, 239, 1);
}
.block-color-brown_background {
	background: rgba(244, 238, 238, 1);
}
.block-color-orange_background {
	background: rgba(251, 236, 221, 1);
}
.block-color-yellow_background {
	background: rgba(251, 243, 219, 1);
}
.block-color-teal_background {
	background: rgba(237, 243, 236, 1);
}
.block-color-blue_background {
	background: rgba(231, 243, 248, 1);
}
.block-color-purple_background {
	background: rgba(244, 240, 247, 0.8);
}
.block-color-pink_background {
	background: rgba(249, 238, 243, 0.8);
}
.block-color-red_background {
	background: rgba(253, 235, 236, 1);
}
.select-value-color-pink { background-color: rgba(245, 224, 233, 1); }
.select-value-color-purple { background-color: rgba(232, 222, 238, 1); }
.select-value-color-green { background-color: rgba(219, 237, 219, 1); }
.select-value-color-gray { background-color: rgba(227, 226, 224, 1); }
.select-value-color-translucentGray { background-color: rgba(255, 255, 255, 0.0375); }
.select-value-color-orange { background-color: rgba(250, 222, 201, 1); }
.select-value-color-brown { background-color: rgba(238, 224, 218, 1); }
.select-value-color-red { background-color: rgba(255, 226, 221, 1); }
.select-value-color-yellow { background-color: rgba(253, 236, 200, 1); }
.select-value-color-blue { background-color: rgba(211, 229, 239, 1); }

.checkbox {
	display: inline-flex;
	vertical-align: text-bottom;
	width: 16;
	height: 16;
	background-size: 16px;
	margin-left: 2px;
	margin-right: 5px;
}

.checkbox-on {
	background-image: url("data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%2216%22%20height%3D%2216%22%20viewBox%3D%220%200%2016%2016%22%20fill%3D%22none%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%0A%3Crect%20width%3D%2216%22%20height%3D%2216%22%20fill%3D%22%2358A9D7%22%2F%3E%0A%3Cpath%20d%3D%22M6.71429%2012.2852L14%204.9995L12.7143%203.71436L6.71429%209.71378L3.28571%206.2831L2%207.57092L6.71429%2012.2852Z%22%20fill%3D%22white%22%2F%3E%0A%3C%2Fsvg%3E");
}

.checkbox-off {
	background-image: url("data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%2216%22%20height%3D%2216%22%20viewBox%3D%220%200%2016%2016%22%20fill%3D%22none%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%0A%3Crect%20x%3D%220.75%22%20y%3D%220.75%22%20width%3D%2214.5%22%20height%3D%2214.5%22%20fill%3D%22white%22%20stroke%3D%22%2336352F%22%20stroke-width%3D%221.5%22%2F%3E%0A%3C%2Fsvg%3E");
}
	
</style></head><body><article id="aded6cac-629f-4003-a8d6-6f0a0d38abab" class="page sans"><header><h1 class="page-title">Technologies to Learn - Summer</h1></header><div class="page-body"><details open=""><summary style="font-weight:600;font-size:1.25em;line-height:1.3">Back End</summary><div class="indented"><ul id="1a4b3dca-a7d3-4626-9ef3-03ce07a28254" class="bulleted-list"><li style="list-style-type:disc">NoSQL</li></ul><ul id="063f1542-70f6-4152-9923-0b87fd8ec3df" class="bulleted-list"><li style="list-style-type:disc">Docker</li></ul><ul id="0d106c92-bab8-4183-acb0-5f514b482538" class="bulleted-list"><li style="list-style-type:disc">Kubernetes</li></ul><ul id="50ce4ef8-66f2-48d3-8392-ccee9a740f4a" class="bulleted-list"><li style="list-style-type:disc">Apache Airflow and MLFlow</li></ul></div></details><details open=""><summary style="font-weight:600;font-size:1.25em;line-height:1.3">Programming Models and Libraries:</summary><div class="indented"><ul id="31164324-e56e-4151-b21f-5ae7cc7b778d" class="bulleted-list"><li style="list-style-type:disc">OpenMP: An API for shared-memory parallel programming in C, C++, and Fortran. OpenMP is widely used for parallelizing CPU-bound tasks in data science and machine learning.</li></ul><ul id="3cdf6e42-5e65-4df0-970a-a2c94e07de27" class="bulleted-list"><li style="list-style-type:disc">CUDA/NN: A parallel computing platform and programming model for NVIDIA GPUs, allowing you to leverage the power of GPUs for data processing and machine learning tasks.</li></ul><h3 id="dce3e0dd-fb71-466a-80af-2595be587b05" class="">Parallel Computing</h3><ul id="634612e9-0d09-464f-93fa-4e72c95b4c61" class="bulleted-list"><li style="list-style-type:disc">Dask: A flexible parallel computing library that enables parallel and distributed computing using familiar APIs from the Python ecosystem, such as NumPy and pandas.</li></ul><ul id="f6f52ba3-3013-4209-b276-0f23e672b122" class="bulleted-list"><li style="list-style-type:disc">Ray: A distributed computing framework that provides simple APIs for parallel and distributed computing in Python.</li></ul><ul id="22cf70e7-6895-496f-a49f-94a2cdb7ef88" class="bulleted-list"><li style="list-style-type:disc">multiprocessing: A built-in Python library for parallelizing code execution using multiple processes. It offers a simple interface for parallel programming with various synchronization primitives.</li></ul><ul id="e69113ba-93fb-474a-9bc1-d95d0809cdf6" class="bulleted-list"><li style="list-style-type:disc">joblib: A library for parallelizing Python functions using simple interfaces like <code><strong>Parallel</strong></code> and <code><strong>delayed</strong></code>. It is often used for speeding up computationally expensive tasks in scientific computing and machine learning.</li></ul><h3 id="aa5beebf-d0b2-4054-9f12-c7019add8e9b" class="">Distributed Computing Frameworks:</h3><ul id="127dea7b-122f-496f-a45f-64a5d65e33ab" class="bulleted-list"><li style="list-style-type:disc">Apache Spark: A fast and general-purpose cluster-computing system for big data processing, providing APIs in Python, Scala, and Java. Spark&#x27;s MLlib library offers distributed implementations of various machine learning algorithms.</li></ul><ul id="9e4dc97c-009d-4759-8e29-1b656ecc1eee" class="bulleted-list"><li style="list-style-type:disc">Hadoop: An open-source framework for distributed storage and processing of large datasets using the MapReduce programming model. Hadoop can be used with machine learning libraries like Mahout or integrated with Spark for more advanced processing.</li></ul></div></details><details open=""><summary style="font-weight:600;font-size:1.25em;line-height:1.3">Cloud Computing</summary><div class="indented"><ol type="1" id="cb090b56-9ee0-434b-bb8a-5bce56113a2a" class="numbered-list" start="1"><li>Amazon S3 (Simple Storage Service): This is a scalable object storage service used to store and retrieve data. You&#x27;ll often use this to store your raw data, intermediate results, and trained models.</li></ol><ol type="1" id="433b55a9-a257-4df9-b251-3733a75f4b5e" class="numbered-list" start="2"><li>AWS Lambda: This is a serverless computing service that allows you to run your code without provisioning or managing servers. You can use Lambda to create event-driven workflows, such as preprocessing data or automating model deployments.</li></ol><ol type="1" id="10fb3622-a928-47d9-be3b-b3aa4f5ac544" class="numbered-list" start="3"><li>Amazon SageMaker: This is a fully managed service that provides an end-to-end platform for developing, training, and deploying machine learning models. SageMaker includes built-in algorithms and support for popular frameworks like TensorFlow, PyTorch, and MXNet.</li></ol><ol type="1" id="a91b6567-3e85-4fe4-944d-ba5614ef2cfa" class="numbered-list" start="4"><li>Google Cloud Storage: This is a scalable object storage service used to store and retrieve data. You can use it to store your raw data, intermediate results, and trained models.</li></ol><ol type="1" id="9e780094-7b02-4ff2-86f6-4a4d5b65c21d" class="numbered-list" start="5"><li>Google Compute Engine: This is a cloud-based computing service that allows you to run virtual machines with various hardware and software configurations. You can use Compute Engine instances to perform computationally-intensive tasks, such as training machine learning models.</li></ol><ol type="1" id="774d098d-16fa-420d-a214-bc5f432c2d82" class="numbered-list" start="6"><li>Google AI Platform is a suite of managed services that provide an end-to-end platform for developing, training, and deploying machine learning models</li></ol><p id="a1634ad3-c3b8-454f-85f0-f42a0d3bd721" class="">
</p></div></details><details open=""><summary style="font-weight:600;font-size:1.25em;line-height:1.3">Summary</summary><div class="indented"><ol type="1" id="369eaa87-5d60-4057-bd5f-b7a133d65078" class="numbered-list" start="1"><li>Storage services for storing your raw data, intermediate results, and trained models:<ul id="aa8ac4cc-774b-4afd-8d3f-4eab1c1c5b58" class="bulleted-list"><li style="list-style-type:disc">Amazon S3 (Simple Storage Service)</li></ul><ul id="b256dfc7-5390-4f1e-850c-bb01bdc8552f" class="bulleted-list"><li style="list-style-type:disc">Google Cloud Storage</li></ul></li></ol><ol type="1" id="9cc50920-b862-49bf-9fae-9b9c54ef5774" class="numbered-list" start="2"><li>Cloud-based computing services for running virtual machines and performing computationally-intensive tasks, such as training machine learning models:<ul id="1afcc8df-ed25-42b2-aa70-c6b87389c297" class="bulleted-list"><li style="list-style-type:disc">Amazon EC2 (Elastic Compute Cloud)</li></ul><ul id="c2333166-5baa-484d-b467-da42fbf16dd3" class="bulleted-list"><li style="list-style-type:disc">Google Compute Engine</li></ul></li></ol><ol type="1" id="b818bb39-10cb-4f11-a8a5-913f8eb86709" class="numbered-list" start="3"><li>Fully managed services that provide an end-to-end platform for developing, training, and deploying machine learning models:<ul id="230f6e09-c306-4cfa-b58f-852dc349a1d1" class="bulleted-list"><li style="list-style-type:disc">Amazon SageMaker</li></ul><ul id="a8d40c95-d794-423e-bc4c-483a697c8b3d" class="bulleted-list"><li style="list-style-type:disc">Google AI Platform</li></ul></li></ol><ol type="1" id="d0553705-0d9b-466a-952e-eea04276fa4d" class="numbered-list" start="4"><li>Optional serverless computing services for running code without provisioning or managing servers, which can be used for event-driven workflows and model deployment automation:<ul id="98e12943-6964-4e62-960f-b2942cc90eb0" class="bulleted-list"><li style="list-style-type:disc">AWS Lambda</li></ul><p id="5f00087d-56ff-4c79-942d-fbea09db935b" class="">
</p><p id="160847e3-ba00-44cf-86bf-ab77c6f0c4ec" class="">
</p></li></ol><p id="8fcf3bd3-968d-49e4-a1dc-1cb0feceb64d" class="">Other</p><ol type="1" id="479f4a37-ed14-4cc1-9e60-2294a56c4d29" class="numbered-list" start="1"><li>Amazon EC2 (Elastic Compute Cloud): This is a cloud-based computing service that allows you to run virtual machines with various hardware and software configurations. You can use EC2 instances to perform computationally-intensive tasks, such as training machine learning models.</li></ol><ol type="1" id="6d871907-adc3-4bd8-ba48-49c06b843b67" class="numbered-list" start="2"><li>Google Cloud Dataflow is a fully managed data processing service for batch and streaming data processing. It is built on Apache Beam, an open-source, unified programming model for data processing pipelines. Dataflow provides the following features:</li></ol></div></details></div></article></body></html>

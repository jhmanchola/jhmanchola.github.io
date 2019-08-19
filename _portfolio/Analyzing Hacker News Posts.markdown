---
layout: post
title: TEST HTML
description: using a 2016 dataset of posts from news.ycombinator.com
img: /img/12.jpg
---

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>Analyzing Hacker News Posts</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Analyzing-Hacker-News.com-Posts">Analyzing Hacker News.com Posts<a class="anchor-link" href="#Analyzing-Hacker-News.com-Posts">&#182;</a></h1><p>This small project analyzes the activity in the comments section of posts taken from the <a href="https://news.ycombinator.com/">Hacker News</a> website. The dataset used here however was downloaded from <a href="https://www.kaggle.com/hacker-news/hacker-news-posts">kaggle.com</a>. This dataset gathers posts from the year 2016, up to September 26 of that year. It organizes the data in seven columns, described as follows:</p>
<ul>
<li><p>'title': title of the post (self explanatory)</p>
</li>
<li><p>'url': the url of the item being linked to</p>
</li>
<li><p>'num_points': the number of upvotes the post received</p>
</li>
<li><p>'num_comments': the number of comments the post received</p>
</li>
<li><p>'author': the name of the account that made the post</p>
</li>
<li><p>'created_at': the date and time the post was made (the time zone is Eastern Time in the US)</p>
</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">datetime</span> <span class="k">as</span> <span class="nn">dt</span>

<span class="c1">#Ignore a FutureWarning that pops up</span>
<span class="kn">import</span> <span class="nn">warnings</span>
<span class="n">warnings</span><span class="o">.</span><span class="n">filterwarnings</span><span class="p">(</span><span class="s1">&#39;ignore&#39;</span><span class="p">)</span>

<span class="c1">#Plotting the averages using a point plot:</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">matplotlib.ticker</span> <span class="k">as</span> <span class="nn">ticker</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>

<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;HN_posts_year_to_Sep_26_2016.csv&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">df</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>(293119, 7)
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[1]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>title</th>
      <th>url</th>
      <th>num_points</th>
      <th>num_comments</th>
      <th>author</th>
      <th>created_at</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>12579008</td>
      <td>You have two days to comment if you want stem ...</td>
      <td>http://www.regulations.gov/document?D=FDA-2015...</td>
      <td>1</td>
      <td>0</td>
      <td>altstar</td>
      <td>9/26/2016 3:26</td>
    </tr>
    <tr>
      <th>1</th>
      <td>12579005</td>
      <td>SQLAR  the SQLite Archiver</td>
      <td>https://www.sqlite.org/sqlar/doc/trunk/README.md</td>
      <td>1</td>
      <td>0</td>
      <td>blacksqr</td>
      <td>9/26/2016 3:24</td>
    </tr>
    <tr>
      <th>2</th>
      <td>12578997</td>
      <td>What if we just printed a flatscreen televisio...</td>
      <td>https://medium.com/vanmoof/our-secrets-out-f21...</td>
      <td>1</td>
      <td>0</td>
      <td>pavel_lishin</td>
      <td>9/26/2016 3:19</td>
    </tr>
    <tr>
      <th>3</th>
      <td>12578989</td>
      <td>algorithmic music</td>
      <td>http://cacm.acm.org/magazines/2011/7/109891-al...</td>
      <td>1</td>
      <td>0</td>
      <td>poindontcare</td>
      <td>9/26/2016 3:16</td>
    </tr>
    <tr>
      <th>4</th>
      <td>12578979</td>
      <td>How the Data Vault Enables the Next-Gen Data W...</td>
      <td>https://www.talend.com/blog/2016/05/12/talend-...</td>
      <td>1</td>
      <td>0</td>
      <td>markgainor1</td>
      <td>9/26/2016 3:14</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Choosing-a-path-to-explore:">Choosing a path to explore:<a class="anchor-link" href="#Choosing-a-path-to-explore:">&#182;</a></h2><p>Looking through the dataset, two post 'categories' stand out: posts that start with an 'Ask HN' string and posts that start with an 'Show HN' string. 'Ask HN' stands for 'Ask Hacker News', and this are posts from users who are asking the HN community for help. 'Show HN' are posts from users who want to promote their work and get feedback through comments and points.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Filter &#39;ask hn&#39; and &#39;show hn&#39; posts</span>
<span class="c1">#&#39;ask hn&#39; are questions from users, &#39;show hn&#39; are projects being posted</span>
<span class="n">ask_posts</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;title&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">lower</span><span class="p">()</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">startswith</span><span class="p">(</span><span class="s1">&#39;ask hn&#39;</span><span class="p">)</span>
<span class="n">show_posts</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;title&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">lower</span><span class="p">()</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">startswith</span><span class="p">(</span><span class="s1">&#39;show hn&#39;</span><span class="p">)</span>
<span class="n">ask_show_df</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">ask_posts</span> <span class="o">|</span> <span class="n">show_posts</span> <span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="n">ask_show_df</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="n">ask_show_df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>(19297, 7)
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[2]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>title</th>
      <th>url</th>
      <th>num_points</th>
      <th>num_comments</th>
      <th>author</th>
      <th>created_at</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>12578908</td>
      <td>Ask HN: What TLD do you use for local developm...</td>
      <td>NaN</td>
      <td>4</td>
      <td>7</td>
      <td>Sevrene</td>
      <td>9/26/2016 2:53</td>
    </tr>
    <tr>
      <th>42</th>
      <td>12578522</td>
      <td>Ask HN: How do you pass on your work when you ...</td>
      <td>NaN</td>
      <td>6</td>
      <td>3</td>
      <td>PascLeRasc</td>
      <td>9/26/2016 1:17</td>
    </tr>
    <tr>
      <th>52</th>
      <td>12578335</td>
      <td>Show HN: Finding puns computationally</td>
      <td>http://puns.samueltaylor.org/</td>
      <td>2</td>
      <td>0</td>
      <td>saamm</td>
      <td>9/26/2016 0:36</td>
    </tr>
    <tr>
      <th>58</th>
      <td>12578182</td>
      <td>Show HN: A simple library for complicated anim...</td>
      <td>https://christinecha.github.io/choreographer-js/</td>
      <td>1</td>
      <td>0</td>
      <td>christinecha</td>
      <td>9/26/2016 0:01</td>
    </tr>
    <tr>
      <th>64</th>
      <td>12578098</td>
      <td>Show HN: WebGL visualization of DNA sequences</td>
      <td>http://grondilu.github.io/dna.html</td>
      <td>1</td>
      <td>0</td>
      <td>grondilu</td>
      <td>9/25/2016 23:44</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Exploring-the-Popularity-of-Ask-HN-and-Show-HN-posts">Exploring the Popularity of Ask HN and Show HN posts<a class="anchor-link" href="#Exploring-the-Popularity-of-Ask-HN-and-Show-HN-posts">&#182;</a></h2><p>Social media on the internet is about gaining 'followers' and becoming viral. In the case of Hacker News, the popularity of posts could be measured given the features found in the data. After filtering the Ask HN and the Show HN posts, it would be suitable to compare their level of importance by digging into the 'num_points' and 'num_comments' columns. Presenting an average of the number of comments and number of points this posts are given is a way of getting an answer about how popular they are.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Create a new column named &#39;Category&#39; which labels posts as Ask HN or Show HN</span>
<span class="c1">#Create dataframe of Ask HN only posts with the new column:</span>
<span class="n">ask_df</span> <span class="o">=</span> <span class="n">ask_show_df</span><span class="p">[</span><span class="n">ask_show_df</span><span class="p">[</span><span class="s1">&#39;title&#39;</span><span class="p">]</span>
                             <span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">lower</span><span class="p">()</span>
                             <span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">startswith</span><span class="p">(</span><span class="s1">&#39;ask hn&#39;</span><span class="p">)]</span><span class="o">.</span><span class="n">assign</span><span class="p">(</span><span class="n">Category</span><span class="o">=</span><span class="s1">&#39;Ask HN&#39;</span><span class="p">)</span>
<span class="c1">#Create dataframe of Show HN only posts with the new column:</span>
<span class="n">show_df</span> <span class="o">=</span> <span class="n">ask_show_df</span><span class="p">[</span><span class="n">ask_show_df</span><span class="p">[</span><span class="s1">&#39;title&#39;</span><span class="p">]</span>
                             <span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">lower</span><span class="p">()</span>
                             <span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">startswith</span><span class="p">(</span><span class="s1">&#39;show hn&#39;</span><span class="p">)]</span><span class="o">.</span><span class="n">assign</span><span class="p">(</span><span class="n">Category</span><span class="o">=</span><span class="s1">&#39;Show HN&#39;</span><span class="p">)</span>
<span class="c1">#Join the two dataframes</span>
<span class="n">categorized_df</span> <span class="o">=</span> <span class="n">ask_df</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">show_df</span><span class="p">)</span>
<span class="c1">#Group by Category and produce mean:</span>
<span class="n">mean</span> <span class="o">=</span> <span class="n">categorized_df</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Category&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Average comments:</span><span class="se">\n\n</span><span class="s1">&#39;</span><span class="p">,</span><span class="n">mean</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average comments:

 Category
Ask HN     10.393478
Show HN     4.886100
Name: num_comments, dtype: float64
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#From here on plots will be created to help visualize the results.</span>
<span class="c1">#Each plot is going to be numerated in the title using the following class:</span>
<span class="k">class</span> <span class="nc">ChartTitle</span><span class="p">():</span>
    <span class="sd">&#39;&#39;&#39;This class enumerates all charts </span>
<span class="sd">    created from first to last (Chart 1., Chart 2.,... Chart N.)</span>
<span class="sd">    It&#39;s instatiated in the title() method of each chart.&#39;&#39;&#39;</span>
    <span class="n">nextNumber</span> <span class="o">=</span> <span class="mi">1</span>
    <span class="k">def</span> <span class="nf">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span><span class="n">title</span><span class="p">):</span> 
        <span class="sd">&#39;&#39;&#39;title: custom title for the chart &#39;&#39;&#39;</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">name</span> <span class="o">=</span> <span class="s1">&#39;Chart&#39;</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">title</span> <span class="o">=</span> <span class="n">title</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">Number</span> <span class="o">=</span> <span class="n">ChartTitle</span><span class="o">.</span><span class="n">nextNumber</span>
        <span class="n">ChartTitle</span><span class="o">.</span><span class="n">nextNumber</span> <span class="o">+=</span> <span class="mi">1</span>
    <span class="k">def</span> <span class="nf">getTitle</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;Returns a string&#39;&#39;&#39;</span>
        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">name</span> <span class="o">+</span> <span class="s1">&#39; &#39;</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">Number</span><span class="p">)</span> <span class="o">+</span> <span class="s1">&#39;. &#39;</span> <span class="o">+</span> <span class="bp">self</span><span class="o">.</span><span class="n">title</span>
<span class="c1">#The object ChartTitle will be instatiated in the title method of each graph, </span>
<span class="c1">#the getTitle() method will be called and it will produce titles numbered in consecutive order</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%</span><span class="k">matplotlib</span> inline

<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mf">6.5</span><span class="p">,</span><span class="mi">4</span><span class="p">))</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">pointplot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Category&#39;</span><span class="p">,</span> 
                   <span class="n">y</span><span class="o">=</span><span class="s1">&#39;num_comments&#39;</span><span class="p">,</span>
                   <span class="n">color</span><span class="o">=</span><span class="s1">&#39;#ff8c00&#39;</span><span class="p">,</span>
                   <span class="n">data</span><span class="o">=</span><span class="n">categorized_df</span><span class="p">,</span><span class="n">scale</span><span class="o">=</span><span class="mf">1.1</span><span class="p">)</span>
<span class="n">sns</span><span class="o">.</span><span class="n">despine</span><span class="p">(</span><span class="n">left</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span><span class="n">bottom</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">axes</span><span class="o">.</span><span class="n">set_ylim</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">16</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">xaxis</span><span class="o">.</span><span class="n">set_ticks_position</span><span class="p">(</span><span class="s1">&#39;none&#39;</span><span class="p">)</span> 
<span class="n">ax</span><span class="o">.</span><span class="n">yaxis</span><span class="o">.</span><span class="n">set_ticks_position</span><span class="p">(</span><span class="s1">&#39;none&#39;</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="n">ChartTitle</span><span class="p">(</span><span class="s1">&#39;Average Number of Comments</span><span class="se">\n</span><span class="s1">for Ask HN and Show HN&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">getTitle</span><span class="p">())</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set</span><span class="p">(</span><span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;Post Category&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;Avg Number of Comments&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Reading-the-averages">Reading the averages<a class="anchor-link" href="#Reading-the-averages">&#182;</a></h2><p>The average values show that there are more comments on average on 'Asking' posts than on 'Showing' posts. One reason could be that people like problem solving and by commenting in an ask post they are actually solving someone else's problem. In the showing posts, people might be solving a problem but it's harder to realize who's problem are they solving. The next step is to keep analyzing the Ask HN posts, by asking, for example, which hour of the day has the most average posts.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Find the hour of the day with the most comments for Ask HN posts:</span>

<span class="c1">#Convert &#39;created_at&#39; column into datetime format</span>
<span class="n">ask_df</span><span class="p">[</span><span class="s1">&#39;created_at&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">ask_df</span><span class="p">[</span><span class="s1">&#39;created_at&#39;</span><span class="p">],</span><span class="nb">format</span><span class="o">=</span><span class="s1">&#39;%m/</span><span class="si">%d</span><span class="s1">/%Y %H:%M&#39;</span><span class="p">)</span>
<span class="c1">#Extract just the hour from the &#39;created_at&#39; column, so a grouping by hour can be done</span>
<span class="n">hour</span> <span class="o">=</span> <span class="n">ask_df</span><span class="p">[</span><span class="s1">&#39;created_at&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">hour</span>
<span class="c1">#&#39;Hour&#39; column created to group by that column, last map() function ignores seconds</span>
<span class="n">ask_df</span><span class="p">[</span><span class="s1">&#39;Hour&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">hour</span><span class="p">,</span><span class="nb">format</span><span class="o">=</span><span class="s1">&#39;%H&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">time</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">t</span><span class="p">:</span> 
                                                              <span class="n">t</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="s1">&#39;%H:%M&#39;</span><span class="p">))</span>
<span class="c1">#Group by hour</span>
<span class="n">avg_by_hour</span> <span class="o">=</span> <span class="n">ask_df</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Hour&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;num_comments&#39;</span><span class="p">,</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Average comments per hour (Eastern Time):</span><span class="se">\n\n</span><span class="s1">&#39;</span><span class="p">,</span>
      <span class="n">avg_by_hour</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="s1">&#39;average </span><span class="si">{:,.2f}</span><span class="s1"> comments per post.&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average comments per hour (Eastern Time):

 Hour
15:00    average 28.68 comments per post.
13:00    average 16.32 comments per post.
12:00    average 12.38 comments per post.
02:00    average 11.14 comments per post.
10:00    average 10.68 comments per post.
Name: num_comments, dtype: object
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Post-Creation-Hours-with-highest-average-comments">Post Creation Hours with highest average comments<a class="anchor-link" href="#Post-Creation-Hours-with-highest-average-comments">&#182;</a></h2><p>The hour a post was created receiving the highest average of comments is 15:00 Eastern Time. By looking at this information, an Ask HN post has a higher chance to get a comment at this hour. If your time zone differs from the one used in the dataset, the following code will help:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">avg_by_local_hour</span> <span class="o">=</span> <span class="n">avg_by_hour</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>

<span class="c1">#For a user in Nairobi, Kenya, the hours with the highest average comments would differ:</span>
<span class="c1">#Change &#39;Hour&#39; column to &#39;Nairobi_Time&#39;</span>
<span class="n">avg_by_local_hour</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;Hour&#39;</span><span class="p">:</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">},</span><span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="n">local_UTC</span> <span class="o">=</span> <span class="mi">3</span> <span class="c1">#Nairobi has a time of UTC+3</span>

<span class="c1">#Convert values in avg_by_local_hour[&#39;Hour&#39;] to datetime objects:</span>
<span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">])</span>
<span class="c1">#Eastern time is UTC-5, so data values will get converted back to UTC by adding 5:</span>
<span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span><span class="o">+</span><span class="n">dt</span><span class="o">.</span><span class="n">timedelta</span><span class="p">(</span><span class="n">hours</span><span class="o">=</span><span class="mi">5</span><span class="p">)</span>
<span class="c1">#Now add local_UTC to the values:</span>
<span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span><span class="o">+</span><span class="n">dt</span><span class="o">.</span><span class="n">timedelta</span><span class="p">(</span><span class="n">hours</span><span class="o">=</span><span class="n">local_UTC</span><span class="p">)</span>

<span class="c1">#Change format of &#39;Nairobi_Hour&#39; to show only time and ignore seconds</span>
<span class="n">Nai_hour</span> <span class="o">=</span> <span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">hour</span>
<span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">Nai_hour</span><span class="p">,</span><span class="nb">format</span><span class="o">=</span><span class="s1">&#39;%H&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">time</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">t</span><span class="p">:</span> 
                                                              <span class="n">t</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="s1">&#39;%H:%M&#39;</span><span class="p">))</span>
<span class="c1">#Set index to be the hour:</span>
<span class="n">avg_by_local_hour</span><span class="o">.</span><span class="n">set_index</span><span class="p">(</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">,</span><span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Average coments per hour (Nairobi Time):</span><span class="se">\n\n</span><span class="s1">&#39;</span><span class="p">,</span>
      <span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="s1">&#39;average </span><span class="si">{:,.2f}</span><span class="s1"> comments per post.&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average coments per hour (Nairobi Time):

 Nairobi_Time
23:00    average 28.68 comments per post.
21:00    average 16.32 comments per post.
20:00    average 12.38 comments per post.
10:00    average 11.14 comments per post.
18:00    average 10.68 comments per post.
Name: num_comments, dtype: object
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Plot-the-post-creation-hours-with-highest-comment-average">Plot the post creation hours with highest comment average<a class="anchor-link" href="#Plot-the-post-creation-hours-with-highest-comment-average">&#182;</a></h2><p>Back to using Eastern Time, a comparison of the numbers of comments per hour is created below:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Filter ask_df to show only the top 5 hours discovered above</span>
<span class="n">ask_df_top_hrs</span> <span class="o">=</span> <span class="n">ask_df</span><span class="p">[</span><span class="n">ask_df</span><span class="p">[</span><span class="s1">&#39;Hour&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">isin</span><span class="p">(</span><span class="n">avg_by_hour</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">index</span><span class="p">)]</span>
<span class="c1">#Sort by column &#39;Hour&#39;</span>
<span class="n">ask_df_top_hrs</span> <span class="o">=</span> <span class="n">ask_df_top_hrs</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;Hour&#39;</span><span class="p">)</span>
<span class="c1">#Display result</span>
<span class="n">ask_df_top_hrs</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[8]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>title</th>
      <th>url</th>
      <th>num_points</th>
      <th>num_comments</th>
      <th>author</th>
      <th>created_at</th>
      <th>Category</th>
      <th>Hour</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>12578908</td>
      <td>Ask HN: What TLD do you use for local developm...</td>
      <td>NaN</td>
      <td>4</td>
      <td>7</td>
      <td>Sevrene</td>
      <td>2016-09-26 02:53:00</td>
      <td>Ask HN</td>
      <td>02:00</td>
    </tr>
    <tr>
      <th>160250</th>
      <td>11193292</td>
      <td>Ask HN: Favorite Email Client?</td>
      <td>NaN</td>
      <td>13</td>
      <td>20</td>
      <td>bmnews</td>
      <td>2016-02-29 02:00:00</td>
      <td>Ask HN</td>
      <td>02:00</td>
    </tr>
    <tr>
      <th>160750</th>
      <td>11189581</td>
      <td>Ask HN: What browser do you use for front-end ...</td>
      <td>NaN</td>
      <td>2</td>
      <td>5</td>
      <td>bikamonki</td>
      <td>2016-02-28 02:50:00</td>
      <td>Ask HN</td>
      <td>02:00</td>
    </tr>
    <tr>
      <th>27873</th>
      <td>12324739</td>
      <td>Ask HN: Were you fooled by the selective atten...</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>lawpoop</td>
      <td>2016-08-20 02:04:00</td>
      <td>Ask HN</td>
      <td>02:00</td>
    </tr>
    <tr>
      <th>160753</th>
      <td>11189543</td>
      <td>Ask HN: How do you get your private projects/r...</td>
      <td>NaN</td>
      <td>3</td>
      <td>1</td>
      <td>steve2048</td>
      <td>2016-02-28 02:39:00</td>
      <td>Ask HN</td>
      <td>02:00</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Plot:</span>
<span class="c1">#First make a list of labels for the x axis to show both Eastern Time and Nairobi Time:</span>
<span class="n">labels</span> <span class="o">=</span> <span class="p">[]</span>
<span class="c1">#sort times </span>
<span class="n">Etimes</span> <span class="o">=</span> <span class="n">avg_by_hour</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">sort_index</span><span class="p">()</span>
<span class="n">Ntimes</span> <span class="o">=</span> <span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">sort_index</span><span class="p">()</span>
<span class="c1">#append values to list</span>
<span class="k">for</span> <span class="n">h</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">index</span><span class="p">)):</span>
    <span class="n">labels</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s1">&#39;</span><span class="si">{}</span><span class="s1"> ET</span><span class="se">\n</span><span class="si">{}</span><span class="s1"> NT&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">Etimes</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="n">h</span><span class="p">],</span>
                                        <span class="n">Ntimes</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="n">h</span><span class="p">]))</span>
<span class="c1">#Create plot</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">catplot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Hour&#39;</span><span class="p">,</span> 
                   <span class="n">y</span><span class="o">=</span><span class="s1">&#39;num_comments&#39;</span><span class="p">,</span>
                   <span class="n">hue</span><span class="o">=</span><span class="s1">&#39;Hour&#39;</span><span class="p">,</span>
                   <span class="n">data</span><span class="o">=</span><span class="n">ask_df_top_hrs</span><span class="p">,</span>
                   <span class="n">height</span><span class="o">=</span><span class="mf">5.5</span><span class="p">,</span><span class="n">aspect</span><span class="o">=</span><span class="mf">1.5</span><span class="p">,</span><span class="n">jitter</span><span class="o">=</span><span class="mf">0.3</span><span class="p">,</span><span class="n">palette</span><span class="o">=</span><span class="s1">&#39;Dark2_r&#39;</span><span class="p">)</span>
<span class="n">sns</span><span class="o">.</span><span class="n">despine</span><span class="p">(</span><span class="n">left</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span><span class="n">bottom</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_axis_labels</span><span class="p">(</span><span class="s1">&#39;Hour (24hr format) ET=Eastern Time,  NT=Nairobi Time&#39;</span><span class="p">,</span><span class="s1">&#39;Number of Comments&#39;</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_xticklabels</span><span class="p">(</span><span class="n">labels</span><span class="p">)</span> <span class="c1">#pass the labels list with the two times</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">ChartTitle</span><span class="p">(</span><span class="s1">&#39;Number of Ask HN Comments in top 5 Hours&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">getTitle</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">tick_params</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">which</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span><span class="n">length</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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iIiINCtYto2awnXxDqPDKDESERGRsLY892tWXjWAVdfswbo/nUioqizeIcWcEiMRERFpomrtlxS+cBuuthqA8q9eZ/tbf4tzVLGnxEhERESaqN64JEzZ4jhE0rGUGImIiEgT6WOOxFIyGpQFSwroQtdYDUuJkYiIiDSRkNWLnqf9skFZ2fyXKZs/I04RdQwlRiIiIhJesLZJUdXaL+MQSMdRYiQiIiJhpY87GsyalnVh1oX6CrvMHREREeksij/+D4Wv/BFw5J1wLdkHXxjvkKLFwhYqMRIREZFuKGxipK40EREREZ8SIxERERFfYrwDEBERkegpX/wuhS/9llBlKT2O/CE9Dpke75B2K0qMREREuoiabetZ/+eTcDWVAFSu/IzEnP5kjD82zpHtPtSVJiIi0kWUL5hZlxTtUDava0/IGG1KjERERLqI5P6jIypri2B5EdWbV0ZlX52ZEiMREZEuIm2vKeSecB0keCNlMiadQvZh32v3frfNvJeVVw1g9fUjWHPbQdQWF7RpPxUrPqXg6Zsoeu9fhGqq2h1XLGgeIxERkS4mWLqVUE0lSbkD272v2m0bWHntUAgF68pyjvspfb77p1btp3TuC2y49wzw846MidMY+NMX2h1fO2geIxERke4gIbNnVJIigOrNXzdIigBqNi5t9X62v/mXuqQIoGz+jE7ZNafESERERJqVOmx/Enr0a1CWMenk1u8oManhshmWmNyOyGJDiZGIiIg0K5CUwqCfvU7GpFNIGbovvc/5Iz2mXtrq/eSdeD2WmFK3nH3oxSTlDYpmqFGhMUYiIiLSIWoKVlP25ask9R1O+rhjMAs7zKej6CKyIiIiIj4NvhYRERFpiRIjEREREZ+ulRZlC9+5j6UfPIAFEhh3xOWMPPjieIckIiIiEdIYoyjasOQd3nuo4VWMj7nsBXoNmRSniERERKQZGmMUa1u+md20bHXTMhEREemclBhFUc8h+zQp67VH0zIRERHpnJQYRdHAMUfxrWOuJSk1m+T0XCZN+yW99tg33mGJiIhIhDTGSERERLojjTESERERaYkSIxERERGfEiMRERERnxIjEREREZ8SIxERERGfEiMRERERnxIjEREREZ8SIxERkU4qVF1BwePXsfoXE9n0z4uo3b4x3iF1eZrgUUREpJPKf+Qyit7+e91y2shDGXzTu/ELqGvRBI8iIiK7k7L5MxosVyz7gGDZ9jhF0z0oMRIREemkkvuParCcmDuQQFpWnKLpHpQYiYiIdFK9z72LpN7DAAhk9qTvxf/AAglxjqpr0xgjERGRTsyFQtQUrCQxbzCBpJR4h9OVhB1jpMRIREREuqPOM/jazK42s4VmtsDMHjezVDPb08w+M7PlZvakmSX7dVP85RX++qHxiFlERES6vg5PjMxsIHAlMNk5Nx5IAM4B7gTucs6NALYBl/ibXAJsc87tBdzl1xMRERGJungNvk4E0swsEUgHNgJHAs/46x8GTvNvn+ov468/yszCNn+JiIiItEeHJ0bOufXAH4E1eAlRETAH2O6cq/WrrQMG+rcHAmv9bWv9+j07MmYRERHpHuLRlZaL1wq0JzAAyABOCFN1x2DqcK1DGmgtIiIiURePrrSjgVXOuQLnXA3wP+AgIMfvWgMYBGzwb68DBgP463sAhR0bsoiIiHQH8UiM1gBTzCzdHyt0FLAIeAc4068zHXjBv/2iv4y//m3XheYYEBERkc4jLvMYmdmvgbOBWmAe8H28sURPAHl+2fnOuSozSwUeBSbhtRSd45xbGWa3SpZERKTbKlswk+r1C0kffwwpA8fFO5zdgSZ4FBER6YoKHr+Oba/f5S1YgP6XP0XWvt+Ob1CdX+eZ4FFERESiI1hRzLY379tZ4EIUztCUf22lxEhERNqlvLyaYDAU7zC6r1AQXKPHP1Qbvq7sUuKuq4iIiDRVXlbNY4/MZfmyLaRnJHHq6eOZtM/AXW8oUZWQkUv2IdMpfv/BurLcY6+KY0S7N40xEhGRNnnxuYV8+P6quuWkpAA3/+po0tOT4xhV9+RCQUpnPUPVuoVkTDiOtBEHxzuk3UHYMUZqMRIRkTbZuKG4wXJNTYgtBWUM2UOJUUezQAJZB5xN1gHxjmT3pzFGIiLSJiNH9W6wnJmZzICB2XGKRiQ61GIkIiJtctgRw6ioqOHL+RvJzUvjxJPHkJiYEO+wRNpFY4xERESkO9I8RiIiIiItUWIkIiIi4lNiJCIiIuJTYiQiIiLiU2IkIiIi4lNiJCIiIuJTYiQiIiLiU2IkIiIi4tPM1yIiItIm5Uveo+jtv2NJqeQefzUpgyfEO6R208zXIiIi0mqVq+ey5vYDIVgLQCAtm6G/W0Jij75xjiximvlaREREoqPk86fqkiKAUEUxZfNfimNE0aHESERERFotMXdgk7KEnAFxiCS6lBiJiIhIRGq3bSBUXQFAj0MvJnXYAXXrMvc9jYxvHR+v0KJGY4xERESkRbXFm9lwzxlUrviYQFoPep93Fz0OmY5zjsqVnxNITtsdB16HHWOkxEhERERalP/I5RS9/be6ZUtKZdhda0nIzItjVO2mwdciIiLSetXrFzVYdjWV1BSsjFM0saXESERERFqUsfcJDZYTcweSMnjvOEUTW5rgUURERFqUe/w1hKrKKZ31NEm9htLrO3dgiUnxDismNMZIREREuiONMRIRERFpiRIjEREREZ8SIxERERGfEiMRERERnxIjEREREV+rEiMzC5hZdqyCEREREYmnXSZGZvZfM8s2swxgEbDUzH4W+9BEREREOlYkLUZjnXPFwGnAK8AQ4IKYRiUiIiISB5EkRklmloSXGL3gnKuJcUwiIiIicRFJYvQPYDWQAbxvZnsARbEMSkRERCQednlJEDPb0zm3qt6yAXs555bHOrhW0iVBREREJFJtviTIs/UXnJdJPRGNiEREREQ6k8TmVpjZaGAc0MPMTq+3KhtIjXVgIiIiIh2t2cQIGAVMA3KAk+uVlwA/iGVQIiIiIvEQyRijA51zn3RQPO2hMUYiIiISqbBjjCJJjHrjtRANpV4Lk3Pue1EMLhqUGImIiEikwiZGLXWl7fAC8AHwJhCMZkQiIiIinUkkLUbznXMTOyie9lCLkYiIiESqzafrzzCzE6McjIiIiHQQV1tD/qNXsOInPVl98wTKFrwR75A6rUhajErwZr2u9v8Mbzqj7NiH1ypqMRIREQmj8OXfs+XpG+uWLSWDYXetJSG9Rxyjiru2tRg557KccwHnXKpzLttf7mxJkYiIiDSjYun7DZZdVRlVq+fEKZrObZeJkXnON7Nb/OXBZrZ/7EMTERGRaEgdPqXBsiWlkjJk7zhF07lFMsbor8CBwLn+cinwl5hFJCIiIlGVe8K1ZB14HiQkkpg3iH4/fJSEzJ7xDqtTimSM0Vzn3D5mNs85N8kv+8I519lSTY0xEhERaYELhbBAJG0i3UKbz0qrMbME/MTDn/AxFMXAREREpAMoKdq1SB6he4DngD5m9n/Ah8Bv23NQM8sxs2fMbImZLTazA80sz8xmmtly/3+uX9fM7B4zW2FmX5rZPu05toiIiEhzdtmVBmBmo4Gj8Jqd3nLOLW7XQc0eBj5wzj1gZslAOnATUOic+52Z/RzIdc7d4M+hdAVwInAAcLdz7oAwu1VXmoiIiESqbddKA/BbbwbT8Fppc9sUhVk28AUwzNU7uJktBaY65zaaWX/gXefcKDP7h3/78cb1Gu1aiZGIiIhEqm3XSjOz24GLgK/ZmXw44Mg2BjIMKAAeMrO9gTnAVUDfHcmOnxz18esPBNbW236dX9Y4MRIRERFpl0guInsWMNw5Vx3FY+4DXOGc+8zM7gZ+3kL9cBmdWodEREQk6iIZfL0AyIniMdcB65xzn/nLz+AlSvl+Fxr+/8316g+ut/0gYEMU4xEREREBIkuM7gDmmdnrZvbijr+2HtA5twlYa2aj/KKjgEXAi8B0v2w68IJ/+0XgQv/stClAUZjxRSIi0kmUl1WzcUMxoZAa92X3E8kEjwuBfwBfUW/+Iufce20+qNlE4AEgGVgJXIyXpD0FDAHWAN9xzhWamQH3AccD5cDFzrnZYXard6CISJx9/OFqZrywiNraEL16Z/D9Hx1AXl56vMMSCadtZ6WZ2XvOucNjElJ0KTESEYmj8rJqfvOrN6mt3TkH8L6TB3H2eRPjGJVIs9p2Vhowx8zuwOvSqtpR2NbT9UVEpGsqKqpskBQBbN1aFqdoRNomksRokv+//qV523O6voiIdEF9+2XRu08GBZt3JkPjJ/SPY0QirRfRBI+7iS5zR0REdleFheXMfG0ZW7eUMX5Cfw49fE+8oaIinU6bxxjlABcCQ2k48/WVUQwuGpQYiYiISKTaPMboFeBTGp2VJiIiItLVRNJiNNc5tztc0V4tRiIiIhKpNnelXQ2UAjNoeFZaYTSjiwIlRiIiIhKpNnelVQN/AG6m4UVkh0UnLhEREZHOIZIWo6+BA5xzWzompDZTi5GIiIhEKmyLUSTXSluIdykOERERkS4tkq60IDDfzN6h4Rijzna6voiIiEi7RJIYPe//iYiIiHRpEc18bWbJwEh/calzriamUbWNxhiJiIhIpNp2VpqZTQUeBlb7OxlsZtOdc+9HMzoRERGReIvkrLQ5wLnOuaX+8kjgcefcvh0QX2uoxUhEREQi1eaz0pJ2JEUAzrllQFK0ohIRERHpLCIZfD3bzP4FPOovnw/MiV1IIiIiIvERSVdaCnAZcAhes9N7wN+cc1Utbtjx1JUmIiIikWrdtdLMrDfQ2zm3qFH5eCDfOVcQ9RDbR4mRiIiIRKrVY4zuBXqHKR8I3B2NiEREREQ6k5ZajBY658Y1s26Bc258TCNrPbUYiYiISKRa3WLU0plnOitNREREupyWEqPlZnZi40IzOwFYGbuQREREROKjpa60kcAM4GN2np4/GTgQmObPZ9SZqCtNREREItW6s9Kg7lT9c4Ed44kWAv91zlVGPbz2U2IkIiIikWp9YrSb6TJ3RERERGKuzZcEEREREekWlBiJiIiI+JpNjMzsLf//nR0XjoiIiEj8tHQR2f5mdjhwipk9QaO+OOfc3JhGJiIiItLBWjpd/0zgEryLx85utNo5546McWytpcHXIiIiEqm2nZVmZrc4526PSUjRpcRIRES6pdL5Myic8TtcbTW5x1xB9sEXxDuk3UHbT9c3s1OAw/zFd51zM6IYWLQoMRIRkW6neuNSVv9iAgRr68oG3fgO6aMOa2Eroa2n65vZHcBVwCL/7yq/TEREROKsbOGbDZIigLIvXo1TNLu/lgZf73ASMNE5FwIws4eBecCNsQxMREREdi1lwJimZQPHxiGSriHSeYxy6t3uEYtAREREpPXSxx5J7vHXQEISWICsg84na8p34x3WbiuSwdffBX4HvIPXH3cYcKNz7onYh9cqGmMkIiLdVrBsO4RqScjqFe9QdhftGnzdH9jP38lnzrlN0Y0tKpQYiYiISKR0EVkRERERny4iKyIiItISJUYiIiIivhYTIzMLmNmCjgpGREREJJ5aTIz8uYu+MLMhHRSPiIiISNxEMsFjf2ChmX0OlO0odM6dErOoREREpNtwtdWUL3mXQHoOacP2j2sskSRGv455FCIiItIt1Rbls/a3h1OTvxyAzMlnMODyp+IWzy4HXzvn3gNWA0n+7VnA3BjHJSIiIt3A9rf+WpcUAZTOfpaKZR/GLZ5ILiL7A+AZ4B9+0UDg+VgGJSIiIt1DsKSgSVlt8eY4ROKJ5HT9y4CDgWIA59xyoE8sgxIREZHuIfug8yGQULeckNOfjG8dF7d4IhljVOWcqzbzJog0s0Q0y7SIiIhEQdqIgxh0w5sUv/8QgYxcco+9ikBKRtziieQisr8HtgMXAlcAPwEWOedujn14raJkTURERCLVtmulmVkAuAQ41t/J68ADrvNdZK2zxSMiIiKdV9svImtmycBovORjqXOuOrqxRYUSIxEREYlU2MRol2OMzOwk4O/A1/5O9jSzHzrnXo1ufCIiIiLxFUlX2hJgmnNuhb88HHjZOTe6XQc2SwBmA+udc9PMbE/gCSAPb56kC/xB3ynAI8C+wFbgbOfc6jC7VIuRiIiIRCpsi1Ekp+tv3pEU+VYC0Zhg4Cpgcb3lO4G7nHMjgG1445rw/29zzu0F3OXXExEREYm6ZhMjMzvdzE7Hu07aK2Z2kZlNB17Cm/26zcxsEHAS8IC/bMCReBNJAjwMnObfPtVfxl9/lO2YO0BEREQkiloaY3Ryvdv5wOH+7QIgt53H/fjfv04AACAASURBVH/A9UCWv9wT2O6cq/WX1+HNsI3/fy2Ac67WzIr8+lvaGYOIdAOh7RVUvrYEkhJJPX4UgYzkeIckIp1Ys4mRc+7iWBzQzKbhdc/NMbOpO4rDhRDBOhGRZgULStl6xiOEtpQBUPbQLHo9fQGWlhTnyESks4rkrLQ98SZ2HFq/vnPulDYe82DgFDM7EUgFsvFakHLMLNFvNRoEbPDrrwMGA+v8Wbd7AIVtPLaIdCMV/1tQlxQBBFdupfLN5aSdPDaOUYlIZxbJJUGeB/6FN7Yo1N4DOuduBG4E8FuMrnPOnWdmTwNn4p2ZNh14wd/kRX/5E3/9251wckkR6YzCfVSE2v0xJiJdWCSJUaVz7p6YRwI3AE+Y2W+AeXjJGP7/R81sBV5L0TkdEIuIdAFpp46j7NE5uG0VACQM7kHK0SPjHJWIdGaRzGN0LjACeAOo2lHunJsb29BaTa1IItJEcHMplTMWQXIiaSePJdAjNd4hiUjn0OZrpd0BXIA38/WONmjnnDsyquG1nxIjERERiVSbE6MlwIROen20+pQYiYiISKTaPPP1F0BOdGMRERER6XwiGXzdF1hiZrNoOMaorafri4iIiHRKkSRGt8Y8ChEREZFOYJdjjHYjXeaOiIiISMyFHWMUyczXJexMOpKBJKDMOZcdvdhERERE4m+XiZFzLqv+spmdBuwfs4hERERE4qRNXWlm9qlzbkoM4mkPdaWJiIhIpNrclXZ6vcUAMBklISIi0kbOOQo2l5HdI4XU1KR4hyPSQCRnpZ1c73YtsBo4NSbRiIhIl1a4tZwH7/+czZtLSU5O4LQzxjN5/8HxDkukTiRjjC7uiEBERKTre+2VJWzeXApAdXWQ559dwPgJ/UlNjeR3ukjsNftKNLNftrCdc87dHoN4RESkC9tSUNZgubo6SHFxJampmXGKSKShli4JUhbmD+AS4IYYxyUiIl3QuG/1a7Dcp28mvXtnNCjbuKGYt95Yzrw56wkGQ4h0pIjOSjOzLOAqvKToKeBPzrnNMY6ttTQgXESkkwuFHO+8tYJFCzbRq3cmx504iry89Lr1y5YW8OD9nxMKeR/p4yf048KLJ8crXOnaWn9WmpnlAdcA5wEPA/s457ZFPzYREekOAgHjqGNGcNQxI8Ku/+C9lXVJEcCCLzexdUsZPXtlhK0vEm0tjTH6A3A6cD/wLedcaYdFJSIi3ZKF+RFvFvaHvUhMtDTG6FpgAPALYIOZFft/JWZW3DHhiYhId3LYEcNISNiZCO09aQB5PdNb2EIkunQRWRER6VQ2by5l0YJ8evZMZ9y3+hEIqMVIYiLsC0uJkYiIiHRHYROjlrrSRERERLoVJUYiIiIiPiVGIiIiIj4lRiIiIiI+JUYiIiIiPiVGIiIiIj4lRiIiItJqoZoqutCUP3WUGImIiEjEQpWlbLj3TFZcmsnKqwdTMuuZeIcUVUqMREREJGKFM35H6ZznwIUIbt/Ipn9eRLC0MN5hRY0SIxEREYlY5erZDZZddQVV6xfGKZroU2IkIiIiEUsffUSD5UBaD1KH7hOnaKIvMd4BiIiIyO4j9/hrqC3aSMlnT5KYN5je5/yBQEpGvMOKGl1EVkRERLojXURWREREpCVKjERERKTTqFq3gKL3HqBqw+K4HF9jjERERKRT2P7239n8yGXeghl9L/kXPQ6Z3qExaIyRiIiIdApfX9GPYElB3XJizyEM+9OqWB1OY4xERES6itI5z7P6xnF8fWV/tjxzMy4UindI7eKcI1RV1qCs8XJHUGIkIiKym6nZtp4Nfz2H6o1LCBZvpnDG7yj+4KF4h9UuZkbOkT9uUJZz1E86PA6NMRIREdnNVK74BII1DcrKl75Pj8MviVNE0dHr7DtJGbI3lV9/RtqoQ8ja/6wOj0GJkYiINOCcY8032wkEjMFDcuIdjoSROnRfsAC4nd1nqcP2j2NE0WFmZB90HtkHnRe/GDT4WkREdqiuDvLA3z9l9aptAIwc1ZuLf7AfCQkaedHZFL3/IFuevolQRRHZB19InwvuwxKT4h3W7iTs4GslRiIiUuezT77h2ae+alB2/vR9mDBxQJwiikxNdZCS0iry8tLjHUqHcs5BKIglqAOoDcImRnokRUSkTnFxVURlncn8eRv431NfUllZS/8B2Vz0/f3IzU2Ld1gdwsxASVFUqW1URETqTJjYn8TEnV8NyckJjP9WvzhG1LLqqtq6pAhg44ZiXnt5SZyjkt2Z0kwR6XRq122n7B+fEiqtJv2Mb5FyyJ7xDqnb6Ns3ix9ediCffLiaQIJxyGF7ktOJW1+KiirrkqId8jeVxCka6QqUGIlIpxLcXMKWaQ9CdRCAqjeWkvuvs0iZskecI4ucq6ql8vWlhIoqST1uFAl9MuMdUqvsMTSXPYbmxjuMiPTqnUHvPhkUbN45EeCYcX3jGJHs7jT4WkQ6lcIrnqP6rRUNylJPGkPOH6bFKaLWccEQhef9l5ovNwJg2Sn0fPx8EvfMi3NkXdeWgjJenbGYgoIyxo7vyzHHjdRZdBIJDb4Wkc4vlB+mGyRx9/mSq/5sTV1SBOCKqyh/Yj7ZNx4Zx6i6tl69M7jg4snxDkO6iN3n00ZEuoXUY0Y1LAgYmVccHJ9g2iIUpvE6uHtfw0q6r+r8FeT/+0dsuPcMSue9GO9wOoRajKTbcM5RW7KYhJS+BFJ6xjscaUbGxfvhiispf2Ehgbw0sm89lsQBPeIdVsSSp+xB4ug+1C7ZDIClJ5F29sQ4RyXSeqGqctbeMZXgdq8FtHTO8wy85mUyJhwf58hiS2OMpFsIVmyk8MOTqC36AgLJZI3/LZkjr453WNJFhcqqqZyxyBt8feJoEgfpshrSeQRLtlC19ktS9tiHhIzmX5ul819mw/87pUFZ1kHn0//Sh2MdYkcJO8aow7vSzGywmb1jZovNbKGZXeWX55nZTDNb7v/P9cvNzO4xsxVm9qWZ7dPRMcvur3TJb72kCCBUTclXPydYsSG+QUmXFchIJv3siWReOkVJkXQqJbOeYeXVQ1j3+2NYec0QyhbMbLauc027gBNzB8YyvE4hHmOMaoFrnXNjgCnAZWY2Fvg58JZzbgTwlr8McAIwwv+7FPhbx4csu7tgacOznHC1BMtWxyUWEZF42fzY1bhabyZzV1VGwRM/C1svWLqVzQ9+v0FZUu9h5B57VcxjjLcOT4yccxudc3P92yXAYmAgcCqwo33uYeA0//apwCPO8ymQY2b9Ozhs2c2lDvx2g+VA2mCS8vaLUzQiIh3PBWsJlmxuUFa7PXzLeem8lwiWbGlQljH5dBJ7dP05ouI6+NrMhgKTgM+Avs65jeAlT2bWx682EFhbb7N1ftlGRCKUPuxSXKiGirVPkJA+mKyxt2IBXYW6K6l6fyUl936IK64k7Tt7k/n9A+IdkkinYgmJZO33HUo+fbyuLPvAc8PWTcjq1aQsMbtPmJpdT9wSIzPLBJ4FfuqcKzYLOwYKwg+O0kBrabWMvS4jY6/L4h2GxEBwcynbrngearzZskv//D4J/bNJO2lMnCMT6Vz6fu+fJPcfReXKz0kbdXizXWMZE04gffwxlPtjkJIHjqPHYd/ryFDjJi6JkZkl4SVFjznn/ucX55tZf7+1qD+wo71vHTC43uaDAI2aFZE61bPX1iVFdWWffKPESKSRQHIaPU+9ZZf1LJDAoOteo2L5R4SqykkfcwSW0D1m+InHWWkG/AtY7Jz7c71VLwLT/dvTgRfqlV/on502BSja0eUmIgKQNLppE39imDIRaZ20EQeTMf6YbpMUQRzmMTKzQ4APgK+AHecC3oQ3zugpYAiwBviOc67QT6TuA44HyoGLnXOzw+xa3Wsi3VjZI7MpvfcjXGUNqSeOocftx2PJCfEOS0Q6r7BjeDTBo4h0Ga46iKsJEshIjnco0kGqqmoBSEnpPi0aEjVKjEREpGtwzvHicwv59ONvAOOgQ/Zg2qljaeFEnm6vtriAUGUxyX2GxzuUzqJzzHwtIiLSXosW5vPRB6sJBh3BYIgP3lvFksWbd71hN7Xlf7ey8upBrL5+JGvvOIJgeVHE21at/ZLK1XNjGF3nosRIRERirro6yLtvf80Tj81j3pz17d7fpg0lTco2hikTqFq/kMIXfwNBr9uxYun7bJ957y63c8Fa1v3pJL65ZRJrfrUfa+88mlB1ZazDjTslRiIiEnOP/2cur7y0mLmz1/P4f+bx/rsr27W/EaMaTkBoBiNHNZ2UcIei7RUEg02v/dUd1OSvaFJWvWlZi9tU569g9Y3jKP/qtbqyisXvUPLpf6MeX2ej0WoiIhJTZWXVLFqQ36Bs1qdrOGzqsDbt78P3VjJv7gYGDe5BZUUNScmJTD1yOIMGN71gb8HmUh55cDb5+aVkZadwznmTGDGy+QSqK0obPZVAWg9CFTu7zypXzmLtnceQd8K1ZEw4vsk2+f/+ETWbmyZUtdva39rX2anFSEREYiopKYHEpIZTJ6S38czBTz/+hhefX8TaNdtZt7aI6pogV1x9MJP2DX/V9xefW0h+fikAJcVVPP34fEKh7nWuTkJ6DwbdMJP0vU/EUjIBqMlfRsXit1l/96lUrV/UZJvKVbOa7iiQSObk02MdbtwpMRIRkTaprQ3y3jtf85+H5/DJR6ubTTiSkxM49viRdctJyQkce8LIsHV3ZeGCTQ2Wi4uqWLum+YHEmzY1HHe0fXsllZU1bTr27ix16L5kfusEXFVpwxXBWsq+eLlJ/fRRhzVYDmT2YvDP3yJl4LhYhtkpqCtNREQACAZDFG2vJCc3jUBg16e9P/vkV8yZvQ6AL+dvZFthBSeeHP4yLIcfMZwx4/qSv6mEYcN6kpHZthaj3r0zWbq4oG45EDDyeqY3W3/U6D58/umauuUhe+SQnt4957mqLvg6bHlyv6ZJat+L7yf/3z+iYukHpA7fn77T/05S76ExicuFQmyfeQ+l818mZcAY8k79RVwvWKvESERE+HrFFv77yDxKSqrIy0vnwu9NZsDA7Gbr19aGmDe34XiT2bPWNZsYAfTpk0mfPpntivPIo/di9apC1q0tIjEpwAknjaZHj9Rm65982lgSEozly7YwYEA2004d267j784y9zmN7W/cDfXmL8ycfCYZE09uUjcxpz8Df/pCk/Joq9nyDZseupSKhW8CULH4bSpXz2HILR/F/NjN0QSPIiLCnf/3Nlu3lNctD90zj59ceVCz9UMhx29unUlpaXVdWb/+WVxz/eExjXOHgoJSMjKSu23rT1uVzHmOorf/BpZAzlE/IXNS06SosbIFM9nyzM0EizeTfch0ep52KxZo/0ic6s0rWfOr/QiVb2+ybs8/rSKp55B2H2MXwjaLqsVIurXqgg8oW3U/lpBOxoifkpStq7FL91NbG2yQFAFszm95TqBAwDjx5DE88+SXhELOa72ZNjrqsc2dvY4FX22iV68MDj9yOBn+oO3evdvX8tRdZe37bbL2/XbE9YOlW9lwz+m4au/1Ufjib0jMG0jO1Eub1C2d9yLFHz9GYk5/ck+4jqS8QS3uu/iDh8ImRZaaSUJmz4hjjDYlRtJt1Wybw9b3jwbnTXpWue5Z+hy/hEBK9zqVVyQxMYERI3uxfNmWurIxY/vucrvJ+w9mrxG92LC+mCFDc8jMTIlqXJ989A3PPfNV3fLKr7dy+U8PieoxdjcVyz+i8JU/4GqqyDn6MjInTovt8VZ8UpcU7VC+6O0miVHp3BfYcM/OM9bK5r/M0DsWYYlJze7bEsKsS0ii9zl/JJCS0b7A20FnpUm3VbHmibqkCMDVbKNy44w4RiQSP989fxL77jeIvn0zOfDgPTj1jPERbZeTm8bY8X2jnhSB11pU35pvtlOwubSZ2l1fzdY1rPv9sZTNe4nyBW+w4e5vU7Hy85geM2Xw3hBoONVC6pBJTeoVf/xYw1gLVlKxvOVxQtmHfY+E7J0JeFKfvdjzD1+TM/UH7Yi4/dRiJN1WILVfk7KE1P5xiEQk/jKzUjj73InxDqOBrOyGyVZCQqDN8x91BWVfvIyrqXdJDhci/8FLyZ5yDjlHXUYgLatuVfWGJVRvXELa6MNJyMgFIFhaSP4jP6F84ZukDJlI3wv/QnL/US0eM1RVSo+pl1L86eO4imKy9juTnGOvbFIvsUfTz9NwZfUl5Q1i6G+/omTWMwRSMsicfAaB5LQWt+kIGnwt3Vaopoit7x1J7fb5AKQMOIXcA5/FTA2pIp3Bxg3F3P+3TykrrcYMjjthFEceMyJs3VDIsXxpAcXFlYwZ25fMrOi3YMVb2Vevs/5PJ4ZdlzbmCAbf4J3ZtfWlO9j67C8ACKRmMfC6V0nb60A2/uNCSj7Z2bKTPHgCQ2+f1+zxtr7wG7Y+d6u3n7RsBlz1POmjww+ur9m6hrV3HEHtltUA5Bx9OX3Ov7vV97GDhR18rcRIujXnQtRs+QhLzCApd594hyMijVRXB1m9qpCePdPp2av5cSePPDibBV95kz+mpibykysPol//5qcb2B0558h/4HsUf/RI2PVDf7+chMyerLyyP662qq48ffwxDLruNVZePaTJJT2G31dAQmZek30Fy7ax8qoBuNqdZx2mTzieQdc0nQyyLr7aaiqWfUhCTn9SBuwWJ7KETYz001i6NbMAyb0PVVIk0kklJycwclTvFpOiDeuL65IigMrKWj54b1VHhNehzIx+P3iIPf/wNWmNW24SEgmkZhGqKm2QFAHUbF0LQMqekxuUJ/UZTsDvZmssVFnSICkCCJZsbTm+xGSS+u5FsCifUHVlg3XBki0UzriTgqdupGr9whb3E29KjER2ofyb/7Dts/MpXfI7QrVl8Q5HRBqpqQk2KauublrWVST1Hkrvs+4kkLpzTFHeCdeRmN2bpNyBpI09ukH9mvwVVK6eQ5/z7iZt5KEAJPcfTb8fPopZ+BnOk3oOIX3sUQ3Kehx2cYtxFb7yB1ZdN5x1dx7Fqp8Nr0uAQtWVrLn9ILY8cxPbXvk9a361P1Vrv2z1/e4o6koTaUHp0j9R8tX1dcsp/aeRd3DsZ4MVkcg557j3rg9Zt9a7ZlogYPzgx1MYvlf85sLpCMHSQsoXv01y3xGkDNm7rrxk9nNsvO/MBnV7TL2Uvhf9DfASlUBy87OF7xCqKGHbzHup3riEzEknk7X/d8LXq65k28x72PrML8DtTEgzJ5/OgMufpnTO82y494wG23SSMUia4LGrKFg9iwVv3UNNRTF7HXAew/Y7K94hdVkV3/y7wXLVxhmEqrZ02FxHtWWrKVlwE7UlS0ntP43MMb/AAs3PCyLSHZkZl/7kQGZ9tobiokr2njSQQYN7xDusmEvIzCNrvzPDljdWf16gQHIqoZoqqtcvIKnvCBLSwo/FCqRl0fOUm1qMoXrTcr65ZWLDs+V8tds3AmApTa9lZ3Gcp2hXlBjF2ao5z7Do3b+Bc4w+/IcM3+/sFutXlm7h3X9dQK0/4dbWtfNIycxj4JijW9xOWq+2bBWNe5stIQNLaP6CldG27aNTqS1eAEDp9vngHFnjb+uw44vsLlJTEzn08GHxDqNTSBt1GOnjjqJ84VsAJGT3IefoywiWbafy609xoSD5D/6AYHE+lppJv+8/RNbk03ex1/A2/fOisEkRQPaUcwFIH3s0aaMOo2Lp+148PfqRc+SP2nS8jqDEKEIFq2dRtm09/UceTkozg9Vaa+u6L/j06WvrLuj3+TM/I7v3cHoPndzsNptWfFSXFO2wftFMJUZR5nWh/RwI1Ss1Msf9GkvsmMSotnRlXVK0Q+XGl5QY1VP59gpK7nyH0JYyUqeNIfvmo7HkhF1vKNKFmRkDr32Vsi9fI1S2lYyJp1C1Zh7r756IqyzF60HyvndcZSmbH72CzH1OxQKtf+/UFq5rUpbYayh5024ksUdfSue+QNq4Y8k98WekDj+ApL57kbXfd0hI77wtekqMIvD5szfw9eePA5CUms1RP3yS3AHj2r3f/BUfNbjKsVf2YYuJUXbv4U3KssKUSduFaoooWfhL6idFiTn7kDvlcRIz9+qwOBJS+2FJPXA1RTvjyGp5MrbuJLStnO3XvgRV3uzlFU9/ScKQHDIvOaBd+6x8fRmWlkjqsaOwNHVbdnbl5dVUVwXJyY3/xICdiQUSyJx4Ut3ylqdv8pMiaDwkN1i0CVdVjtWbIDJSmZNPZ/vMe+ofmAFXPU/+AxdT9Y03R5KlZOCqvBNXEvMGk7n3SaDEaPdVuvWbuqQIoKaymEXv/o2Dz72v3fvOHdB0yv2cAWPrbldXFFG8eQU5/ceQmOy1UuQNHM/YIy5jyfv3EwrW0H/kVEZMuaDdschOrqYIQk2bhjsyKQKwxHR67PNXiub8GFdbTGLWGLLG/7ZDY+jMahZvrkuK6srmboBL2ra/4MZitp71KKGtXots2b9n0/PJ87FkfUyGs2L5FpYvLaDfgGz2njiAQCD82U2x9MZrS3nnza8JBkOMHN2bCy/al+QUPV/h1BZtanZd+vhjG8yaXV/V+kWUfPYkidl9yT7kQgKpDS/e2+us3+FCtZTOeoaEjJ70mf4XKpa+V5cUAXVJEUBt4Vq2v/130kcfTtnCN0kZPIGs/c/CAp3nJHm9gnahpqrp6dm1Vc1fq8c51+zpj431H3kYY6b+mGUfPogDRky5gIFjjgFg3cLX+fjxKwnWVJCc1oNDL3yAPsO8X8J7H38Dow+9lNrqcjJyB7b+TkmLEtKHkNzrcKq3vFdXlr5HfJLPtMHnkNL/ZEIVG0jI3Cvi11Z3kDSmD6QkNkiOkiYNaPP+yp/9qi4pAqhdWkDVeytJPWZku+LsKmprg3y9fCvpGcls3FDMM0/uPN165YqtnHHWhJgcd9u2Cj75cDU1NUH2O2AIAwZ6A4U3bijmzdeX19VbtqSAjz9czdSjOvYHTGcUqq6k4InrKJ39LEm9h9H73D+TfdAFFL70f3V1kgeMISGzFyl7TKTnabeG3U/Fys9Z99updfMiFX30MENu+aRBEhNISqHvBffS94J768q2Pt9yd3/F8o8pfPE3O5eXfUDfC//SpvsaC0qMdiF3wFh6DdmXLWvmeAVmDD/g3Cb1vp71JF++9ntqKosZfsC5TJr2SwIR9NdOPOFGxh99NThHon+NGOccs5+/hWBNBeC1HM2bcRvHXblzxtGUjNw2j3UK1lYTrC4nOT2nTdt3B7kH/Y+yZX+itmQJKf2nkT50OgAli/+PsqV/BDMyR11P5uifxzyWQGIGgazwl0HozgK56eT8cRolv3+HYEEZaSePJePC5ruhdykYalLkapuWdUdF2yv4670fs63Q+0xKTW341THrs7WcdMoYUlO9rsey0mrS0pPa3YpUUVHDfXd9SEmJ98X82adruPLqQ+nXPyvsxWQ3d+MLzNZXOOMOit72Ts0PFm9mw92nsecfV5GY25/yhW+Rssckco+7mkCYs8XqK3r77w0mi6xaNZuK5R+SPuqwlgNoofXHElOo3dJw8s2i9/5F77Pu9GJ/9Y9UfTOP9HFHk3PUZXFpSVJiFIGplzzCis8eo2zbOoZMmEafYVMarC/ZsorPn72+brzQso8eIqffGIbvf05E+09MajifRChYQ2XJ5gZlZdsbTuPeVitnPcXcl2+jpqKY/iOnctC595HczKma3VkgOYes8bc3KKvKn0npwl/WLZcsuJmkvANI6XNER4cnvtSjRpB6VHSSxrTTv0X54/Nwxd4XQcIeuaRO3fX4PVcdpHLmMkL5JaQcPYLEIdE5OaMz+fD9VXVJEXgzS9cXCBgBM7YVlvPov+ewbm0R2T1SOOu7Exk5qnebj7t4YX5dUgRQWxNi7ux1nHjyGIbv1YvklASqq3bOmzN2XN9wu2lWWWk1FRU19OrdeU8dB++CsKXzXyKp11Ay9/02ltDyV3f54ncaLAeLN1O9YRE5R/6YnCN/HPFxLbHpBXstYdcX8c2afAYVi96uWw5k5NHjiB8SLN1C5sRpbH32lw3qW0IiBBLYcM/plC94A4Cy+TMIFuXT68zf0NGUGEUgKTWLMYc3f2rh1rXzmwyi3rpmbsSJUWMJickMHHcc6xa8Wlc2ZMLJbdpXfRUlBcx67kZCwRoANi57l0Xv/pWJJ8S+1aMrqN76aZOyqvw3KV/1T2oKZ5Pc+3CyJ/yBQLJa4lorVFRJzdLNJI3uQyB71xPPxULi4Bx6/e8iKmYswtKSSDt1XNjB1zXLC6AqSNJ478rh2y7/H9Ufrgag5N6PyPv32STv3fYuvc6orKy6SZnZzo+9Q6cOIzklkSf/O79uksXioiqefGw+N916FAkJbfvVnxrm8U/zyzIyk/nBj6Yw8/VlVJRXs98BQxg/oX/E+575+jLenrmcYNAxdM9cLvr+fqSn7/pLv6OVL36HdX88AfzP7czJZzDg8qda3CZ16D5ULv+objmQmkVyv9Z3CecccyUlnz1FqMJ7TtPHHU3q8AOoXDkLS8kgZeDYsNv1OOKHhKrKKPn0CRLzBtLr9NsomfUsxR88RPG7/ySp/xiwADivRTb32J+y6R8X1CVFOxR/8pgSo91Vrz32xQIJuNDOXy6999y/XfucctafWNhrKIVrv6DPsAMZMzXyLL85xZtX1CVFOxRtWtLu/XYV1Vs/o3j+VdSWLid1wKlkT7qXQOLOX5LJvQ5psk1V/uvUbvcGGVaUfU1tyXLyDp1BIDGzSV0Jr/KdFRRdNwNXUYOlJZFz1ymkHBaf+WgSBmSTeemUsOtcyLH9mhepemMZ4I1nyrz28LqkCICqWsr/M7fLJUb7TB7EnFnr6hKhnNw0LrpkMiu/LqT/gOy6GaY3bixpsF1JSRXbCsvp1bt174dNG0t47pmv2LC+iIyM5LrErGevdPafMqSu3h5Dc/n+D3d9FmJRUSXfrCpk4KAe9OyVQcHmUma+kT5B/wAAIABJREFUtqxu/epV2/jgvVUcd0LnO+tz22t31SVFAKWzn6V68/9v77zD4yjOx/+Z6yederPlJveGC264UAw2NYDpNdQfCSGQUEKSLyHFkBBCSKMkhNBJ6NV0YwMGY9y75Sp3W7J6vX638/tjV9Kd7tRsyZLs+TzPPbc7O7s7u7Nz9+47b9mJLbt5bWbGRb8jWFyAe+NnWFJzyb7+nzFG023B3mcUeQ9vpm7N+5hTckgYPpP9v5+Bb9dyAJKmXEGv215FCIEMBcFsQQiBEIL0c39G+rk/A8B/MD/KpihYtIWUWbdj66VH7A5VHqTio4djzm9J7ZpxpASjDsCV3p+pV/6DjfMfJeDTo1HnTbi09R1bwGp3Mf7c+zqohToZ/cZhc6YQ8Da6f/caekqHnqOnIrUglUsvRfPpkVq9e1/CZMsgedyjDXXs2aeTNPavuLc/CphIHHYPtRvujTpOsHwxJZ8MJmPmN1iTY39kZdhP3bZHCZYvwZoxDdfwnyPMx7ebce2fvkR69R9+6Q1S88hXZHWRYNQSgcW7G4QigODaQvxfFsTUC+0oPZrNOioMGZrJD26byuoVB0h02Tj51IEkumzkbyrmqy8K2LWznJlnDGbY8EzKSqMdVj6ct4Wbbpnc5nNJKfnfi6sb7IX8/jBZ2YnMOHkgU6b1w2JpX6ydzfnF/PeF1YTDGkLAxZeNISUlVivZtN3dhzjZrrSWbd/MiWn0uecjtIAXYXUckdOGJbUxGGPl/H80CEUAtSvexDX9+1R9/hjeLV9hdqWTdfXfSJ5+bdQxgod20BTNW03amT8BoHze72O2C6uDzCtihaWjgRKMOoi88XPIGz+nq5vRIhZbAqfd9BLrP/sTnuoiBoy/iGHTW04KeLwQqt3eIBTVEyj7Jqaea9hduIbd1bDu2fUfwnXbo+rIQBnlX00n8/QlWJJHAKAFKgl79lFX8AS+PS8A4C/+nLB7D6mTn+/oy+kRaBUeav+xmPD+6ujyQ7Vx68uQRqigDHOfFExJ9qPRxCjCxbHtEiaBZXgWoW2NwlBoexmBlfuxTe53NJvX6QwZmsmQoY2pcN56fT0rl+tZ27dvLaWq0suci0ezdk0hXk+jhmNLfjF1tX5cbewzd10gxoi6tMTNvPc24UqyMXZ8+7QIn328lbBhWC+lvv7L+88gIcGKJ6Kdo8f0atdxjxapZ92Je9PnENbtuhInzMHWK9quzn9wM3Wr38ea0Y+kk65ssA0y2Tr2pSteMMfS/95BqHwfAOHaMg49exMJo87Akto4rekceTomZ0rDlByAa0Lj/2Xi+PN1TzZjag2TiX73fY1j0BE4UxwBSjA6xgh4qylY/iq+2hIGjL+IjH7jorZnDpjArFtbnp8+HrG4BiNsGchAeUOZNb31t9zUSc9S8d1lyEC0sbwMVlG9/i4yTvkMz+7nqF77UyM2UvSbm3f/a8etYFR174cElu2LKXd8b2RMWaigjIofvYNWWINwWkn+3Zk4LzzyIKvNIcMa3g82E8o/hG1KPxxnDcd++mDEozZkvb2NxYTjnBFIk4gSjACCG4p6jGC0ZXMxCz7bjs8XYur0AZw6s23aurVrDsasX37VOHr3TmLXzoqGcqvVhLUd0cgTEm2kpydQUREd4V9K+GJBQbsFo0ghDXRPt5Ur9jN0eCZVVT6QMGlKX8YfQaiHziRx9GwGPLiGujUfYM3KI2lSdG40z9avOfDo2Q3TbTXLX6fvPR/HO9QR4zrpCioXPA6G2YiwJzUIRQ1oYXx71+KKEIzMCSn0/eUCyuf9nnBtOSmn3hSVgsQx4ERy73yPyvmPIUyCtHN+1mVCESjB6JhCahpfPH0lVUWbAdj+3Yuc8YPXYrzoFLEIs4O0k16les1thN27sff+HkmjY9W7TbFlziD7/H2UzT+BsDt6WiVUnY8WrKVm3V0RASOj1eJmZ8/48+xoNHcgViiymnHdNo3Em2MF0tq/fYNWWAMY020PfYEMaQSW7MEyOIOE6ydicnWcFqn24S/xvKrbjnleXQsWE/azhuG4dAz+hTswJdlJuvc0rKNy0Gp8eP6zPGp/25Se0a9VlV5efn51g0blo3mbSUtzMmZc60bMqanOqOmn1FRdO3HWucN5/j8rCAT0P88zzx6GvR1BF00mwTXXn8gbr66jtCR6eisYDDezV/NMntovKt5RUrKDj+Ztbli/5roTGT+he8eDs/cZjb3PaDxbFlH8wg8wJaSRdvZdWDMH6FGnI2yQPBs+w38wH3uf5l8cfHvXUv3lv0GYSJ19O/a+scGG69ECPqoWPoFvz2oSRp5O7j0fUbPoGUz2RFwTL6bw8SY51oQJ5+BYuy9H3kT63Pl+s+dxjT8f1/jzW7gLRw8lGB1DlO1d1SAUAUgtTMHyV5Vg1AZC7r3YMqaTfe4OpBZCmNrzQ24l84wllC6YiOZrVDXbe52D5i9Ghj1N9wA0hDmB5HF/i3tMLVCB1AKYHd1TvX+kCKcVU6+kqGkz6/hcXD+a1rAeWHMA94urQJMEt0drZGStn5pff9ZYd/UB0p+7okPaJoNhPG9tiC4Mafg/aXRU0ADfZ9uwzxiIfeoAku47A/cLKxFmE4k/PAnrmLZ7R3Ulu3aWNwhF9WzfVtomweiCi0bxyktrCATC2GxmLrhI91AaNDiD+34zi127ysnplUR2dstGv+VlbrZuLiE9M4HhI7IxmQT9B6Tx8/tO5+031rNi2f6GuiefOrBd1+euCzBtxgDS0xPYuaOctHQnCz+PtndZumRvtxeMADzbFnPgz2c2TDfVrnybgY9so6kWGtA9vpohUFzA/odOQQb08Au1y15jwEMbsWY0CvOebd9QOf8fAGi+Oryb9WS0dSveIv2CX5F7x1sNdZ2jZjVsB0i/8NeYXRmHfZ3dASUYHUOYbbHBuiwdPMfcXQhWrqY2/7eEfcUkDLiOxKF3IsN+gtXrsbiGtdllPuw9SMWSiwhVrUFYkkk+8QmEJQH39r8DJlzD78WR23qoBJM9k8wzllCz4V6CVeuwZ88iaewjmCwuLCljCVU3/tG6Rv4KW/YsrClj47azZsMvcO94DGQYR99LSZ3yX4Sp+7kRHwnCJEj53VlU/fJjZI0PU68kkv+vMR5UaF8lFTe/CYbWIea332GBiFg6gaV7CRfXYs6JTWsgvUGCO8qwDM7AlNiG+2gSCKcF2Yp2wjsvn+S5Z+nC0HUTSbxuYuvH7mYkxQmN0Du3bXHNRo7K4f65sykqrKF3bnKDGz3orvRj2uA6v7OgnGf/vbxBOJs4uS9XXjO+Yfsll49l0OAMCg/WMGx4FsNGtC0mkpSSd9/ayApDKzlxcj8uv3ocbneALxcWoGmNmlubvWckHa797n+NNjhAuKoQT/4C0s65G/f6TxoCMSaeeCH2XH06OnBoO7XL38CUkIp74+d4t34FiAahCEDz1VK36l3Szr5T36dwKwcfPRsZig3RAFDz7UtkXtqoTe9z1zxqvn2JYNkeXBMvjtEW1a3/BN+O73AMmRaVu607owSjY4j0PifQ94RzG+If2RJSGXHKD7q4VR2PFqqjfPE5yIBux1BTtZZwoBLvrv+g+YvB7CR10rM4+7UeR6p2028IVa0BQIZqqF59K2h+6qe8KpcuJXP2Gqwpzaua6zEn9CVt6usx5ekzPqR281xCtdtx5F5I4rB7EM280QXKvsW9/a8N674Db+PNnk3CoGOvH+2nDSJ70Y8IH6zBPCANYWm8J/6vdjYKRQASbFP7I/0hLEMy8X2xAxkZZFAIRByhJ7ByP5U/eR9Z40Mk2kh59PyGoI0ypBFYuR+Tyxal4RFmE67bZ1D78Jcxx4vElOZEHGZ8nu7CujWxgWMDgfgC4aGiGlYs24/VZmba9AGkpjlxOq0MGnz42oGvv9wZpbFas+oAZ507nDQjIazJJJgwqS8T2mlusiW/hOVLG6dqV63Yz4iRWYwdn8v0k/P49hs98rLVauKM2T0jqrw5OTtumXPINAY8tIG6NfOwZvTHNfFiAHx71uiaoWBs3sfY4zQKnHVr5jUrFMVrh8nmbPBaa0r5B3+k/N3fNKxnXPwAGXN+3Wp7uholGB1jnPz9f1Nc8C3e2hJyR8zCfgym/QiWLWkQiurx7HwKGSjTV8JeatbeiaPPpQhTy9nRQ7VN4jg1TR4rw/gPfdYmwag5zAl9SZ30bNxtYc8+qlbeTKD0a6zpk7HnnNN6G48hhMOKJc4fqzmO1sI5ZzTOOXo/+D5pck+kjJvstebhL5E1ep9Kd4CaPyzEMXMwWqWH8uteJ7xLN7a3zx5K6mNzGtyaE6+biG1KP7wfbNajWhfVYBnTm9DmYl1gs5hI+vnMqHNplR6q7/8M/+JdWIZkkvzA2djaEXCwKygy7LYimf/pVqZOHxCV9qOkuI4n/rGEoCE0rVq+n3vvmxmlJYpHOKyxbWspwUCYkaOyYxK8Np3GkxK0OKlZ2ktJHA/Cek+3Cy8ezdjxvSkrdTNseBbJcVz3uyOps++gdvkbBEt2AnoMIecQferZljOkIWZQPdVfPd0mocg57BRckxrDy1gy+8dWMqJ5CpuTzMv/iNTCaN4azK2kpaqc//eYdSUYKY46QohjPjaROWk49XY69Ugt+g1HC5QhQ3UIW8sD1977ewQrGg1nTfZsNH+0h5l370sgzCQOvbNZTU97kFLDveNx/IXvE3LvQvPqb+3BiuXIkBtMNoi4Hnuv8474nD0N++lDsJ85FP8C3R7EdvJAHOc2eqtZhmYSXFfYsG7un4qI4/kULowNBSBDGp7X1zUIRQD+hTsIrNiP/aTGPwXr8GysP88mOUIACpe7CW4owjoqJ2barubPi/Av0v+0QttKqbrnA7Lm/6Bba5XiCTbhkMRd548SjNasOtAgFIEeuDF/4yEmtWBkvnVzCe+9vZHKSn3aJi3NyR13n0xShNv+jFMHUrCjrCFw5MjROWRkHnl6juEjs/n0461RCQk2ri9C0yRnzB5K3sB08gamH/F5jiaWlBzy/piPZ+sizIlpOAa2okZrJW1I+iW/J3HEqTiGzoiKc5Q06TJqx7+Oe91HgO5Kn3XN3wgc3IxzyDR8u1ex6548wlWFOIbOIPfHr2NJi+/RJ8zRz5cMhwhVFUW58ndHzHPnzu3qNnQUc7u6AYqjg8mWirC4CJQuBhnCmj4VzVsIMiLLetbpJA6+tdVj2TKmAwItWIk1YzqpU15EhtyEqtc31NH8pQSKP0dYkrBlTj/i9ru3/43ajT8n7NmHDEW/2Wr+EtKmv4/mLcRkzyZpzEM4+1x8xOfsTkgpcT+3gpq5C/At3IF5YHqDkBEqKKP6159R9/RSbBP7kfzb2SRecyKJN0yKEjCsI3Pwf7sbWevHlJFAyp/Ow9InJeZc4f1VupbHwH7mMJznjcQ3fxvBjYei6tpPHYQ1Ik5PPEwJNiwD02M84EL7q6h54HOIsF2RtX4SLhvbJTGX2sqB/VXs31cVVZaW7uSsJhGgD+yvYsf2sqiyiZP7kh3Hpgvg4w828/47m6Jyqvl8IZyO6Km3rGwXI0Zm40qyMfmkfpx97vAjTjwLkJRkJzc3meoqLz5fiFBIo642wK6dFQQCIYaPiJ2W6gkIkxlb9mDCdWWEa0uxxJleq8eaNYja7/4XlQS2noQTziLnxn9jzRwQE/xRmMwkT70a15QrSJ31Y9LO/AnmxHRsvYeDycyBh08jXKOPqVDFfgIlO0meGt9sQVjseDY2OkkQDlC9+AVcky7B7OoWgukD8QqFlHGiavZMjpkLaQ+aFsZk6hnGgx2NFqxBBqvw7HmJus1zo7alTHyGhIE3H/ax/aXfUvH1adGFwow1bQopJz6GNe3wDW3LvpxBsCI27xqANW0ymbPibztW8Ly5npq5jTmRRLKDrC9uRTgslJ79TINbPoDrJzNw3RZfGJVhjfDBasy9kuNqiwCkP0Tdf5YRWHUA29jeJP5oGqZEG4H1hVR8/1UI6z8bpowEMj+9pUHgCW4rwfvWBrCaSbh6fKuJYavu/gDf/G1RZeY+yWTO/yGiA/7oO4v9+6r452NLGoyRLRYTd917KlnZiZQU1/H+O5soLKxh4KB0igprGhLJ5g1M49bbp8XNgRYIhJl7/3xCodgpsWHDM7n5hyfh8QT4bvEeamp8nDixD4OHtCyQHi5eb5Df/Wp+VFlqqoNf/W52p5yvswn7PRQ9cQmeTQsASBx3Hrk/eRdhiT+lGaoqouzd31K36l00TxWOIdNJu+A+fJu/RIYCpMz8AfZ+Y9p8/kDJLvb8ItYmK3X2HWR//7G4+1TMf4yy1+6JKks75x7SzvkZ3oLvcAw4EWtW+7wNO5C4g1NNpR0hdeV72bzoKfzucgZOvIy+o88+KufdveYd1n38RwLeKvImXMrkix/CZG55vv9Yw2RNBmsyyFhj0SNNs2FNOQHMTgg3em8gwwQrllLx3aVkn1vQLpf+SMyJA5sIRiYwWbCmTSF10jNH1O6egP+bXVHrssZHcH0hpoyEKKGovm5zgpEwm1oVWITdQtJPYnPc2cblkv7CVXje2YAp0RYVBym0u4Lyq19p8Hrzzssn6+ObESlOtHI3pszEmLfs0J6KmHMk3XdGtxaKAPr1T+XW26exYuk+7A4zJ586iJ07y3nqye9w1zVO527eVMy4E3O5YM4orFYzQ4dnNavZ0cJajO1QPdu3lfHRvHx2bCujuFi3+Vm5fD83/3BKp2hxbDYzriQ7dbWNWpP0jFjv3e6O5vdQ/Pwt1K54K8ozzb3+E8revo+sq/4Sdz9Lam963fwM8sZ/IwNetICHPb86Aa1On0auXvwCAx5cExVJ21uwjKqFTwB6EtlILzNrZh7WnCEEi6NjtlUtfJKU0/4f9n5jY9pgyxkSUxYo3snuewfp2ixhIufGp0g57ZaYelIL4944n3BNMa7xF2BO6hwBuindd/K7BxAK+lj478vZueJVDuTPZ/HLP+Dgli9a3/EIcVcVsvyte/HVlaKFg+xa+Trbv3up08/bXXHm3YSwNaplza6hOHKPLD2LyZZK8ti/gCl2GkTz7ifs3nnYx04a/QDmRCMBpMlO8omP0/sSL5mnf40lqf0ZsHsalqbTVWaBZWA6oX1V0OTP1tKKJiFcXEtoX+VhtcM2qS+pD59H8q9nRwlY3o82R4UCkFVe3C+tpuzcZyg97SnKzn2WYMT0HID9jOgff8uwTBxn9Axvp4GD0rny2vFcdOkYJJJ339wQJRTVs3tXOSeM7c3wkdktTnct/mY3LU1ELFu6r0EoAt3guj61SEdjNpu4+NITsBkaxaQkO+fPiZ8RvjtT8dGfqF3+RpRQVE/lgicJVhZS+uZ97H1gKsUv3ka4rjyqjjCZMTlc1K1+r0EoApABD7XLXmtYDxzawYFHZlG77HVql73OgT+dQaBkZ8RxTOT+9D3MKbE2QsGmEbANEk84C1vfRq2UyZFEoGhL4xSf1Ch961eEasvwH9xM5CxW4T/mUPj3Cyh+7hZ2/99IAkXbmh6+U1AaoyOgZNcyvDXRdgp7182jz8hZnXreyoMbkVq0lqR8/7pOPWd3QwtU4tn9HJq/FGf/a8g6cx3efa8hzE6c/a9FWI78rTBx8I9w9r2csi+nEnY3ajmE2YU5Ia8d7bsaa2pjbBaLazBZ52whVL0Rs7MfJnujzUWgbAm1m+4n7DuEs//3cY28v0E7EfYdwrP7OWTIQ0LeDT1WiEq8eQrBDUUElu5FJFhx3X0q0h2g+mcfRtnoWIZm4vrpyWg1PoL5xVhHZGFKa+zX6gc+x/vmet2V/+SBpD0+B+Fon9Y0XFhDaH8VtvG5CMNjyhTHS8n70eYGbVZ4XxWVt71D+stXYxmgC1Su26aDEPgX7cQyMJ2ku3qeA0RdrZ9Vyw80K9T069c2D9d4IQAicTqt1Ab9MWXNsWTxbpYt2YvNbmb22cMYOSqn2br5Gw/xxYIdBIMaM07JY+r0AYwZ15uhwzMpK/XQq3cSFkvP0wdEJm6NIRyk5OXbca/9AAD/7pV4ty8m74+bYqrG8yIzRZTVrX4vypNNBn3UrXqX9PN+3lBm7zOKnJuepvAfFzYeNzmHhJFnxG2esFjpf/9iapa+guapJmnqVez7Q7QWV3NXsvvu/siQH1vuKPr87BNCVYW4N3waUaeCygWPk3P9P5u/Fx2EEozaQPWhbax47z6qCjfTa+gpTLn0EeyJ6SQkx0YlTkhpX6TiUNDHoe1fY3OmkDXwpDZlQc7ofyImsw0t3PhWlz3oJIL+OrZ9+zw1pTvpM2IWA8ZfGLVf0fZvWPPhA3hrihkwfg4TLvgdZkvPCxwotRDli04jVJMPgLvgcTJmfk3isLvx7Hya6rW3Y8uYTsKgWw97uqsBs52wJ/pt1uTIQpibN6jV2zeTUI3+w+Te8RgZMxdhy2iMQC6EOUpYAt1mqmLJBcig7klVt/l3mOyZJA7+EVqwhrIvTkLz6pG1PTufJHPWKixJPUMrEYkpyU76c1cQLq3D5LIjnFbqnlsOTWxSbKcNIrS1lKq75iG9QbBbSP3z99CqfdT+4xtkReM0Z+Db3Xjf20TC1Se2uR3u51ZQ+/dvQJOYMhJIe/4KrEOzcF50Ap431hPerU+PWYZkENoZ/Qaulbopv/xlMt69AUvfVITFRNIdM0i6Y8YR3JmuY92ag7zx6jrC4fhS0cBB6cy5pPWQFVJKkpIdMak86jGZBOdfOIrtW0tZvUp/ll1Jdk6a3p8N6wpJTXPSf0DjH/Xm/GLmvZvfsP7y86v4xa9OJy099sWntLSO/764usFe6t23NpKekcCw4Vk4HFb69ms0zv/u2z18tbAATUpOO31wm/PDdRXO4afhyV8Yd5vJmYxn+7dRZYHCLdSu+ZCkCdHBaV0TLsIxdAa+HUsAsPUZTfKM6xu2x/Mus6Q1RgXXAl5K/nsHdSvfwZI5AEtKb2y5I0g/7xeY7I194tuzmuKXbidQtAXXuO+RfcNTUbGOUk65iYoPH4o6T70GKVC4mfJ5D5I87dqYtkh/0ywCnYPySmsDX/7nKioPbkQLB6kp3Ymnuoh+Y87DkZSJ311BxQHdgykpazCTL3kYq715d9OAt5qg343FloCn5hDzHz+PguWvsHv1W1Qc2MCA8XNaFY6s9kRSe42gqnAzEsnQaTcwauaP+frFG9m18g2qD21l/6ZPcLgyGpLIBrw1fP7kBfhqi9FCfioObMBksTakC/HVlbFn7Xu4qwpJyhiA6MYG3YGSL3DviIiPIcMgJYHSr6jbPJdQzSb8hz5FC5Tj6H1kru5SC+De9mciQwOYEwbEeLzJsA/NV4TJmkKg5CvcO/4asVUDtFan9wKlX+Pd81x0ocmKs9+VeA+8iW/vyxGHDGCyJmPPjv+W1hMwJdoQVv05CyzfR2BFtAAqAyECX+9Cq8+0HtYIrNqP7+Ot4A01PRzmgWnYT26bEadW5aXytnehPuu6N4hW4cF5zgiwmvG8vhZpuJlrFV5M2a7G5LH1BMKIRDuWfqnd2vOsNTRN8sxTy/D74wd27Nc/hdvvPBlHKzGLtm4p4ZmnlseNjQQwanQON/9wMoMGZ3DC2F7kDUpHCBg8JJN339zI2jWFrFi2n8LCasafqP8ZL1m8m/37GkMuSKlH5u7TN9YDccO6QrbkR4faSHTZGd4kWvae3RX898XV+P0hAv4w27eVMnBwere2PXIOPolwXTnB4gKsOUNxDJpCuKYEa85Qet3yHJ78hWie6CllsysDR/9xmJyNnoPCZCb55BtwDjuZ5KlXkXXFI1ECjbXXcHy7lhEs1QNgJoyeTealf2j4Pyh/by5VC59EhgJonmq0oJe+v1iIJbVRISC1MPv/cDLBwi0QChA4mI/mrcY1rjHqtXPkTKwZ/TA5kkgYPRtfwdKotpscyWTM+TV1a+Y1eMBhtpJ93RNY0zs0D2FcrzSlMWoFv7uS6uLtUWUlEWrNSRf9nmEzbsLvLiej/4QWPcTWffow2xY/i6aF6D/2AhJT++CubMytVbj1S0p2LcPhysBiSyQxLTZ/T9m+tRRt/ZLknKGce8+ChvO5qwopLlgSVXfXqjcZOk1/Gyjavohw0Bu1vWD5q5ww605qSney4J8XEfDqP0A5g6dz+g9ea5P2qisQ5ljBU1gS8e55IarMs+dFUk58stXjBavWUZv/OzTfIey5c3D0Pg9LyliEMGGyuEgc/GPcBfUeFwLX8J8RrN5I7abfoPkKMSeNxF/0MTJYiSV1Akkj7489SRt8Ji3Jo0CYo4zJrSljjWuO/dGWYW9MWU8luDvWeDm0uzLGeFmraOaaBThmtX1qUavyQpOUH5oRFDC4oZDwruj2NAhnTfC8tAr3v5diGZxB6hMXY8lr2Ri8O1JaUkddHJuievbvq0bTZINdkZSSxV/vZu3qg6SkOjj73OFkZCby2n/X4vUGmz3O5vxihg7LZMapAzl4sJrn/7M8roYqf2MxuwrKGDQkk169YwN99s6NHyIgKY5wmhsnUGjTsAMA27eWMqSVUA1dibDYyLn+n3Gnkbw7l6N5qmLKq795luov/olz2Cnk/vSdhvxlwmQicXR8rzyT1U7fn3+Ob88aEALHgBORWhjf3rVYM/rj2bY4qr5WV45n61fULnudwP6NJIw5G9eECwk1sTfyNtlPCEHKqTeTcurNuoH1mnkESxvNFVyTLkaYzPS7bxE13zxPqKaY5KlXY+8/rm037AhRglEzhAJeCpa/Qm3ZbpzJOXhrGo0tM/pHq+uTswZBVqwqVgsHWf/pI+zb8BG2hBSqirY0bNu3/gOyB02L2Wfle/dRW7oLhGDo1OuYdNEfIvb5kCWv3UG9EcDAiV8z9QpdM2G1JyJM5ijbI4stgbryvXz5n6txVx2gKb5aPTHn9iUvNghFAMU7v6Nsz0qyBk5p8R51FbbM6dhzzsZfrLvhmmxNDvNdAAAgAElEQVSZJA65A3/hh4RDjX9gJpv+Q+cr/IjazXORwWoSBv0QS8oY/EUfYUkagaPf1VR8czaaETU7WLmKuvzfgLDg7H8NKROeImncX7HlzCJUtQFbzplYU06g5JNBevoR9Lxt9YSq1uDZ+xK27NkEShpV377CeYS9D2J2Np+s0pzQl8Shd+He/jdAgrBgSdYzZDtyL8CaNplg5cqG+u4dfydUt4O0aW/1+Fxqsix26sU6PAvriOyGLPcAthl5BBbvjqpnGZqJ6/bp2Cb1bSjzL95N7eOLkdU+rONzES471uFZOC8Zg7CaseSlYx3TKyqWkUi0UTLraUypbYyEbBL6FB8Q2llO7aNfkfbPS1rZqfvxWdMo4k1ITrbj9QZJNFKuLF+6ryE7/cED1ezbW8V1N06IEYoSEq143NFl69YWMuPUgbz56vpmp+1AT+kxaEgmk0/qx55dFaxdcxCzWTAgL501qw4ihIjSGlVWeHj7jejEvydO7MP4CbFTQ35frPDmi1PWHfHuWkHZ678gWLaHpMmXkXn5wxS/cCuau8mLhRBg2HF5ty+m4sOHybo6vudaPBx5EwA94ezBv5xLsHQXwmLHMSx6qlhYHRx65ma0Wl1T59+/nspPY8/jGNT8f4kwmenz888of28uwdLdJE2+jNTZdwBgTkgh7Zy729zujkJNpTXD1y/eTMHSl6k4sIGQv/FH25aQyinXPYPNqb+JBP1uhDAhTLEGfZsXPUX+l48T9Nfiq4t9S0nOHoK7cj+R1o6BCHVoxYH19B52Kgmp+uBe/vYv8FYXNWyvKtrCkKnfR2phNi18jLK9jX/QAOFQgF2r3sRbU0Q8rHYXlUWb8dUUU1e+N2rbgBMvwpUeJzR8N8HR/yqs6VOw55xJyomPY3b2weTsg+/gPEADYcGaPgXfgXeo2/oQmq8QGawkULIQ375XCVauwn/oMwJliwnXbY9zBo1Q9Xqk1HDkzMKSNAxb1imYnbkEypfg2fmvZtsWrt2GyTUMzR3h0qr5MNkzsaZPpWbdXVQtuxLP7mcxOftgTW70kqleczsyWP8jpxGsXGlE3DbjzLseGQ4SLG/UDIbrtmN2DcWaenTepDoCrc5P3dPL8Ly2FukNES6pxf10k9hNiTasw7IQdgv2k/pjSnHi+N5IHKcMAqeVUGG1/uZ702TSHrsIy+DGt/1waR3lV/0P7VAdssZPaHsZoU2H8H+9i3BhNY7ZumbJMWsoUpOY0hIw56USWLwHWedHK3Pr3nHN/G87rhyP89IxBBZFeyaGi2qwju2NpY1Gyt2Fzz/djsfTvGDg94fZsqmYk6b3x2QSfP7ZdspKG38TA4Ew+RuLY+IWBYOxHlR5A9MZO643n3+6jWALSXr79kshKyuRRJedE8b2Zur0AWxYV0ThwRr27a1i1YoDDB+RRYphKP/t17vZtrU06hgzTsmjb7/UKM13eZmb+Z9uw9vkesedmNvtI2G7Ny3gwCOzCZXtQfPW4Nu5jHBNKZ4Nn7S6r5QaJqsTS2pu1NQZ6NGoqxY8QeWnfyFYvg/HwEnGS7ZGyYs/wlfwnV5RCxOqKiJx7Dl6WhKTBUIBZKDpS03swEk+7RacgyY32z5zYjpJky4h5dSbcQ6ZejRnK+JOpSnBKA51FftY88Hv4m4LB31kD5pKQmofvnv1Dpa9eTc7lr6EPTFdF3SqDmBzpiCEYOPnf42aKos5T/keHK5MQoHmDcpyBs8gtfcIQJ8a81RHCzl7185j7/p5HNyyIGbfUMBNKOahrUeghfxUF2+jrnyvHrrdcAW12F3468pJSO1NYmrzGo6uRAgTlqShWFPHN8QssiaPImHgzVjTJuMv+4Zw9QbCdduItA9qim7M3MIg1HwxCVyDFSvxHXy7xfZFCUUG9pyzCFWvp27LgyCDyGAVvgPvIGUYW9Zp1Ky/h0DxZ1H76FquH2GyuBDCTLB6E4Hiz6PqWFPHYc9qEoyyG6FVedGqfQ1xgip/9A6+9/MJ7yzH/2UBgfWFyJom0XnDGuGd5YTyiwntqSTl0fOp/fMivG9tILS1BPxhMAtsE/tiP6k/mjtAuKQWkWCj4pY30Ypic2UBhHaUkXD9RITNgnBasc8YiOOMIXrAyUgNRgtTn6H8Q1gGZUSlJNHbLPF9sBlNkwSW7cXcOxlT6pHF0zoalJd52Lc3diomErc7QGKijf4D0ti3pzImWna8YI5NSUmxk5WTxDdf7cJiNVFbGxuRuZ79+6pYumQvmdkuevVOYueOcpYuaXx5k1JSU+1j/IRcwmHJR/PyqauNng7ckl/C6pUH6NcvlVQjKe1Lz62i8GC0DVSiy8bFl47B7ui+EyhawMe+B6dCk9xn/gObQGtewKwnXHmQutXvUbXwSZzDT0WGg5gS0/DtXE7R09dR8/UzBIq24slfSLCyECFM7H9wKv6m3s5aiFD5fggH48aPaw7Phk/wbP6KhNGzqV70DGVv/xrfruU48iZicrjafJxOQEW+bivu6iI++ONJzW632BJI6zuW0l2Rb7kCk8WGFvLjyshj5s0vs2Ppy2z7tjF5qMliA8xooQg7CWGKG5uinrwJl5I1YCKbF/0Lb01JlCfa4TJ46rXsXPZKVJnJasfpyjYEOf1Wmi12zvvZl7g61titw/AVfkig/Dus6VOxJPQj7C/FX/QRgfJlhKrWtPk41uwzCJZ8RbxHSNhzSDvpFezZpzeUVa3+Id7dTYykhRVk82/dJmcfMmetpGb93fj2vxFbwZIEofh/5o7+38fiGoKwuLBlnkL5VzMa058IC5mzVmJNjQ2s1h2oeXQRnv+uhpCG/YwhJP1yJmVnx0+o2yJ2sy4MxSHhxkl431iP9AYx9UlGOxjf+BcAp4X0Zy7HnJOE2Ugh4vuqgKrb32tfeyymGC+6eCT/djYJV7XdU64rCAbD/O+lNWzdXNxi/CGAE8bksGVLKeE2XHtTkpJs1EYIL0ZeUkwmwYiRWQwbkc1nn2zFF2FYn5BgZe5DZ7N86V7eeXNjzDGnnzyAzCwXH7yXH7OtHofDQnKKg5wcF5s2Hoq+RgH3/3YWKd1cgPXvW8/e307omIMZN97kyoiKaRRRASw2iJNK5EgxJaZHTfsJqwP7wCkkTbmM5JOuxF+4BfeGT7H3GUXSSVchWsn31gHEfStWglEcvnzmGooLvm29Yguk9x3LKdc/x/K37uHQjsW6MXV6f6oPbWl9585CmHEmZ+N3V6C18aGfeOEDDJtxUyc3rP3Ubv4DdZvja/U6HoFr/JNYE3pjcY2k9IsJ0RGxW9zVAuZEXMPuImnUbyn9YjqhyhZikjRz/vrHW9gykIHGHzN7n8tInxZH0OoGBNYepOLaV6PKTAPT0fZWNK/Es5ow900hvPvwgja2SoSAZZ3Qh9QnL6bihtcJ74id6u4QTILML2/Fkh3fYLg7UFRYw98f/aarmwE0CkvtITMrMWpqr73YbGYuu3IM4yf0bb1yF6EFfBTclgLhWG/MY4YmSgJr3zHkXPsP6la9i3C4SD3jNqwZHf6SrgSjthAKeHnrN8Nbr3iccOqNz9NnZPfLK3RoXnpDvJ+jShOvsfZgzZ5NsCR+LJLDxuyk15yqI4/X1AlUP7gA7+vHV+DRuKQ6yFl0G8LW/foI4I1X17F6ZfNT/scLt94xjcERCW67E1ooSMEtbXQKOEYxpfRm4J82Y3bGehoeAXEFox4TAlQIcY4QYpsQokAI8X+ddZ5AHLfH4xW7K4vc4d0zTo4MxXef7vwTH55QBHS8UAQQ9ulvWt0Q/9eHnzblmKLKh+etDa3X6wI8noASigw++6gLtfmtcPCf8bPXH09o1UWUvTv3qJyre/6iNkEIYQb+CZwLjAKuFkJ0SsIbx1FKUtcT8NeV4vd00pTGERAO1h6RgHJsIRHdVDBqNubQcYj3ne4pGD39r6WtVzpOONSMwX5XU/7hw3jXvt/VzegWVC98Aqm1376tvXTPX9RYpgAFUspdUsoA8DpwZFlCm8FktmJL7J7q1K6gsmhzVzchhsChT1uvpOhy2hwP6DhAHoaxcmcjpaToYPcUBrqCQAvhA7qS8vfjOk4dn0iNUGXnJByOpKcIRn2AyLtxwCjrFLK7aWDDriCt9+iubkIMluTWczYdN5i7r1GvZVxscL3jFce5I7u6CYpWyMrsUrfxFuieGQi6Ckta53tJ9xTBKN6T0WlW4xMvfBCTpXvlPjKZj35k417DZuJwdb+gZ9aUUVgzel728s4g5cTHu7oJzZLyq1lg7Sk/MZ1EZgKJt0zB9YPmw390FUIIxo7v3dXN6DbcekdsJoLuQOaVj3Z1E7oNaRf+Jm4w5Y6mR3ilCSGmAXOllGcb6/cBSCkfjqjWoRcS8FSxedFTlO1bg6+unMS0XDLzJhP01uFIyiA5cxBbFv+H2tLdmG1ObI5kEtP6kJZ7At6aQ5QUfEdS1iCyB02jpmQ7vYadhgBqy/eQPeRkag5txVdXRsDvZe+ad7A6Ehky9Tq8NSXUlu0GKXEkZZM1cDJpvUeQkjOMcCjApi8ep3DLQnoNm0ld2W6qD20jre9Yast2E/BWkZU3mdGz7mLj/D9Tvn8tKb1GkpY7kpDfTUJaP4p3LMZTW4q36iC2hDSGn3wz6bmjCfrdlO1bxZ5187BaExl1+o/pe8I53TZfGoDv0Hw8u18g7C8jVL0eYUS7Drt3IcMBbJnTsWVOJ1ixnLCvlHCgCiE1nAOvw+Lsh3fvKwSr1gAa2DLBlIAIVqJpASyJ/bFlnoIl+QRCtdvwF76PMCdgz72IUPVaZMgNZieB0m+RwXKwZWBJyMOaMg7v3ufA5MDR+3wC5d8Rri3Q4w6ZbJiSRmF2ZBOqWgWYsaRNJFSTj9QCmK3J2LNOwznwFmo23EuwYiXCkkDC4LsJuwsI1WxCWJIwJ/THZEkgYdAPsaZ0P41eJFq1j9rHFxPcWorJZSNc4SZc7tGjTWcmEtpZridndZgRIQ1pEpgzXfqrUEgj7A5AlRdhtyITrFDuBl9Ij0yd4dSXAxrmQem4bpyMZXQvTHYLWpUX76dbCeQfAimR3iAipCGyErEMySS8pwIcVhLnjCa48RCW4dmEqzz4l+zRA0iGNEy9k/XglAerIdmOJScJrcSNKTcZy9BMLEMy8b29ASkEjjMGo7kD+N7PR3oCWCf3I/3xixCOlhOvdgcWfbGDLxYUEAqFsdksWKwmBg1KJxjUqKnxUV3tw+sNYRKgabqtv0lAQqIdvz+Mx0iu63CYSUqyEwpJgsEwDoeV1HQHUpOYLSZ656awaUMR5WV6QNt613yzGZxOGx5PQA+hYzYhhCC3bzLhoEZCop30dCfbd5RSU+XH7jCRlOTA7rDidFqpKHfj94Ww2iwEAro7u9cTIBSSSCkxmUxoUkNqYDYLNE0ipX5+s0UwclQOF106Bpere70MR1L59bOUvnyHHljR6sRkT8SUmovZZidQshtZV06Lf4HCBCYrhCPCtJjt0evCBFanHkRSmLD0Gorm96JVFxkxjaR+DIEeVNJsQyRlIf21EApgSkhBBnxIb63udm+xthALyWQ8AFqcdteHJxFgMoPFjq33cHrf/ib27LYliW4HPdddXwhhAbYDs4CDwErgGillZFSv7n8hCoVCoVAougtxBaPuGVijCVLKkBDiDmA+YAaebyIUKRQKhUKhUBwxPUJj1EaOmQtRKBQKhULR6fTsAI8KhUKhUCgUnY0SjBQKhUKhUCgMlGCkUCgUCoVCYaAEI4VCoVAoFAoDJRgpFAqFQqFQGCjBSKFQKBQKhcJACUYKhUKhUCgUBkowUigUCoVCoTBQgpFCoVAoFAqFgRKMFAqFQqFQKAyUYKRQKBQKhUJhoAQjhUKhUCgUCgNLVzegA4mbDE6hUCgUCoWirSiNkUKhUCgUCoWBEowUCoVCoVAoDJRgpFAoFAqFQmGgBKMOQghxjhBimxCiQAjxfxHlrxjlm4QQzwshrM3sf4MQYofxuSGifKIQYqNx3MeFEDG2VEKIuUKIg0KIdRGfKyOW64w2rBNCvNw5d6D7Y9z/EiHEpibl6UKIBca9XyCESGtmf9VHnUwLffSoEGKrEGKDEOI9IURqM/s3Nw4HCiGWG333hhDCFmffG4UQpU36aFzEcoUQYrexvLDjr75n0EIf/d7on3VCiM+FELnN7K/GUSfTQh81vX/nNbP/8T2OpJTqc4QfwAzsBAYBNmA9MMrYdh66YbgAXgNui7N/OrDL+E4zltOMbSuAacb+nwLnxtl/LnBvC+1bBEzq6vvU1R/gVGACsKlJ+Z+B/zOW/w94RPVRt+ujswCLsfxIM33U0jh8E7jKWP53M+PwRuDJFtr2InBZV9+jrv600EfJEcs/Bf4dZ181jrq2j1q8f0ad434cKY1RxzAFKJBS7pJSBoDXgTkAUspPpAH6wO8bZ/+zgQVSygopZSWwADhHCNEb/cdmqbH/y8BFR+OCjkWklN8AFXE2zQFeMpZfIv49Vn10FGiuj6SUn0spQ8bqMuKPo7jj0NA8nAG8bdRrro8VbaCFPqqJWE0EZJzd1Tg6CrTwW9cWjvtxpASjjqEPsD9i/YBR1oDQp9CuAz4z1icJIZ5tZf8+xnKzx43g7ghV5VeHeyHHKTlSyiIA4zsbVB91Y25G1ygghMgVQnxilDfXRxlAVYRg1VIfXdlkCsDZ8c0/dhFCPCSE2A9cC/zWKFPjqHtxhzHl+bwwzAbUOIpGCUYdQ7wYSk3flv4FfCOlXAwgpVwlpbyllf3bctx6/i6lHG98Tm9LoxUto/qo+yGEuB8IAa8ASCkLpZT1dhId0UdvRPTReCml94gbfRwhpbxfStkPvX/uMMrUOOo+PAUMBsYDRcBfQY2jpijBqGM4APSLWO8LFNavCCF+B2QB97Rz/wNETxlEHVfRYRQbqnyM75I4dVQfdTGGoe75wLXGdEtTmuujMiBVCGFpUq7oPF4FLo1TrsZRFyKlLJZShqWUGvAM+rRZU477caQEo45hJTDUsNi3AVcBHwAIIW5Bn1e/2ngY4zEfOEsIkWaoNs8C5hvTOrVCiKnG/O71wLzOvpjjkA+Aeu+YG4h/j1UfdSFCiHOAXwIXSik9zVSLOw4NIeor4DKjXnN9rDgChBBDI1YvBLbGqabGURdS/wJocDGwKU41NY662vr7WPmge59tR7fmvz+iPGSUrTM+vzXKJwHPRtS7GSgwPjdFlE9Cf3h3Ak8CIs655wIHI86xDsiL2L4I5akBuldgERBEfyv6f0Z5BvAFsMP4Tld91O36qADd7qH+3v3bKM8FPonYv7lxOAjd+aEAeAuwxzn3jUBpkz6aHrH9Rbq5N00X99E7xjjYAHwI9DHK1TjqPn30X2Cj0UcfAL2NcjWOIj7CaKhCoVAoFArFcY+aSlMoFAqFQqEwUIKRQqFQKBQKhYESjBQKhUKhUCgMlGDUAbSQl+Zo5eDyCCGyI8rqhBAZEcG1DjXJjxOT3+ZYp4U+Gi+EWGbcl1VCiHjuq6qPOhkhRD8hxFdCiC1CiHwhxJ0R29Q46ga00keXG2WaEGJSC8c40hxcmhBibETZJiFEnrHvOiHEPhGdpyuv4+5Az6CVfjpa+ex69ljqauvvY+FD1+fg2hd5bKAuTp0W8+Mc658W+ujz+vuK7omxSPVRl/RPb2CCsZyE7hFTn59JjaNu8Gmlj0YCw2nBK4yOycG1Dz14YH3ZJqK90m6khTxdx8OnlX46WvnsevRYUhqjDkB2fQ6u59FDsKcfyXUcy7TQRxJINpZTiB+wTPVRJyOlLJJSrjGWa4EtNKYbUOOoG9BSH0kpt0gpt7VyiI7IwfURMFoIMfzIrubYpZV+Olr57Hr0WFKCUedytHJw1aE/iHc2s13RPHcBjwo9v9NfgPtA9VFXYkx/nAgsN4rUOOpmxOmj5up1dA4uDV2D+KvDavhxRrx+Ekcnn12PHktKMOoCZMfnDgJ4HLhBCJHcQh1FLLcBd0s9v9PdwHOg+qirEEK40AMF3tXk7TYG1UddQzv7qKNzcIGebmSqEGJgW9p7vNJcP8mjk88OevBYUoJR53LUcnBJKavQfzB+fIRtPt64AXjXWH6L9uUOUn3UgQghrOg/5K9IKd+N2KTGUTehhT5qCx2Sg8vQLP0VPUWMIg5t7KdOzWfXk8eSEow6l6Odg+tvwK2ApZV6ikYKgdOM5TPQ04I0RfVRJ2Pcv+eALVLKvzXZrMZRN6CVPmoLHZmD60VgNnpybkUELfWTOPr57HrkWFKCUQcghHgNWAoMF0IcEEL8P2PTn4AzhRA7gDON9aj5XCllBfB79B+NlcCDRhno0zzPouel2YnuBdAsUsoy4D3A3oGXd0zQQh/9APirEGI98Efgh0Z91UdHlxnAdcAZES689VMwahx1D5rtIyHExUKIA+geSx8LIeYb5Q02Roam5w70P94twJtSynzj2L8E7hFCFKDbHD3XUkMM4+3HMezNFFG0OJaEHuJgA7rAcyeosdQUlStNoVAoFAqFwkBpjBQKhUKhUCgMlGCkUCgUCoVCYaAEI4VCoVAoFAoDJRgpFAqFQqFQGCjBSKFQKBQKhcJACUaKHokQoq7J+o1CiCc76VxCCPGlECJZtJC5OqL+vUIIKYTINNbnCiHuPYzznmKcY50QwtkR19KGc46PcO1FCHG+EOKBZureKKIzma8TQoyLWK4QQuw2lhe28fyLhJ59vf4Yb7e+V8wx8oQQ17R3vzYe+/6ItoUjln8qhPiREOL6zjhvM23plCzmQogXjX3sxnqmEGJPG/b7rp3tzxNCbGpm27NCiFFNyt4zrqFACFEdcU3T49VXKA6XHhV0SaHobIQQZilluEnxecB6KWWNECIR+JmUco0QIglYLYRYIKXcbOzfDz3Wzr52nlegh8/QIoqvBf4ipXzhCNreXsYDk4D6/FYfA78XQjwipfTEqf+GlPKOOMdACPEi8JGUsr3CzbVSylXt3CeSPOAa9Ki7baKt905K+RDwkLFPnZRy/OE2soMoA35GRBRoKWU5jX0wFz2z+V/aedwwcDPwVFt3kFJOb1p2uM9kRHqKyLKLjWPORM/Mfn7E5nYJZQpFSyiNkeKYQwgxQAjxhRBig/Hd3yh/UQhxWUS9OuN7pqEFehXYGOeQ12JEeG0lCzzA34FfEJtDaJShDdklhPipcd48Q/P0L2ANEWH4hRC3AFcAvxVCvGJorR4VenC2jUKIK+O13TjmVuMNepOx72whxBIhxA4hxBRjvylCiO+EEGuN7+GGNuFB9KzY64QQVxpRiRcBkX9CRx0hxAVCiOVGexcKIXKM8tMiNAdrDWH1T8ApRtndQgizce9WGs/Erca+8e7dFiHEM0LX1H0u2qGpExGaQaOv/y6E+MY45mQhxLtGH/whYp/vCyFWGG19Wghhbuet6aws5v8A7haNaToAPf+WMabWGM/hnIhtzY4nIcQ9xvO4SQhxV8QhLUKIl4x+eVsIkWDUXySEmNTWxkbWF7rW7BEhxGrjWZkSMfYuNOrEfSYUCgCklOqjPj3ug/5Guy7isw940tj2IXCDsXwz8L6x/CJwWcQx6ozvmYAbGNjMufYCSXHK84zzJhvrFwKPGct7gExjeS76G60dyATKAauxvwZMbea8De1Fz2m0ADADOcZ5ezdtu3HMEDAG/cVnNfqfpwDmRNyLZMBiLM8G3jGWb6y/jxHtuBZ4Ik77bgRKm/SDM177jfWkJnUjP6OMOouAbRHljxrlaTQGpL0F+GtEX88wll3oWvCZ6Jqq+vP+EPi1sWwHVgEDW7h34431N4Hvt/AM1jVZn4uuyai/jkeM5TvRU8/0Ns5/AD2680ij/Vaj3r+A69sxBuYC96JnSH+gtTZFlC1upg9mR/ab8dzchP7M7jG2WWh83jPRIyCLyHPHua8T0QWkRKOP8tEzvuehv0DU99/zTe7fpGauO6p/m9Y3jnmusfwe8Dn6eBsHrGvpmeiK3zL16X4fNZWm6Kl4ZcQ0hhDiRvQpINDTElxiLP8X+HMbjrdCSrm7mW3pUtcONSCaZK423nTvRw+zH4+PpZR+wC+EKEEXbgD2SimXtaF9JwOvSX1aolgI8TUwGaiJ0/bdUsr6N/V84AsppRRCbET/MwJIAV4Seu4kif7H0RwlQG4z2+JNpcXFuIdtmXqKN5XWF3hD6ElkbUD99S4B/iaEeAV4V0p5QIiYJOBnAWNFo7YwBRgKBIh/79YZy6tpvF+HwwfG90YgX+q5phBC7ELXDp6MLjSsNNrsJH6C3NZ4HFgnhPhrWypLKU9p43H/iH4NH0eUCeCPQohT0YX6PujP8qEm+0be15OB96SUbgAhxLvAKcax90splxj1/gf8FGjvtF9TAsBnxvJGwC+lDDZ5/pt7Jpr7DVAcRyjBSHE8UD+tFcKYPhb6P1GkIaq7hf1DQgiTNOx/RPzM1YPRtRDrjT+5vsCa+qkrwB9xvDCNY6+l80YS82/fQtsjz6VFrGsR5/098JWU8mIhRB76G3dzOABvG9vZLMY01+JmNl8jDTutZngC+JuU8gOh25jMBZBS/kkI8TG6HdgyIcTseKcGfiKlnN+kPTNp+d6F0YWVwyXyvjftE4vRrpeklPcdwTmQUlYZ01ZtymIuhFiMrr1ryr1SygYjeSllgRBiHfqUbj3XoidunWgIG3vQn4+mRN7Xlp7dplPOHZGjKiilrD9Ow72XUmoRU4NxnwmFApSNkeLY5Dv0zN2g/5B/ayzvQX9DB31aqSUtSSTbgEHQfOZqKeVGKWW2lDJPSpmHPl0yQUrZ9E36cPkG3ZbELITIAk4FVhzB8VKAg8byjRHltcT+aQ4D4noPtQcpZa2Ucnwzn5aEoqbtvaG+UAgx2Lj3j6BPh4yIcw3zgdsMgRYhxDChG9F3NV8AlwnDq0wIkS6EGGAsvxwhVLeFNmcxl1Ke0kwfxPMcfPqhWXEAAAGVSURBVAh9uq6eFKDEEIpOBwa0oW3fABcJIRKM+34xjQJyfyHENGP5ahrHamfTXZ8JRTdACUaKY5GfAjcJPYP0dRgZpIFngNOEECuAk2i7tuZjdLsGaDlzdWfyHrABWA98CfziCIWuPwMPCyGWoNst1fMVuqH4OmEYeAOnEz2dEsmVItpdP8Yz6TB4JeJ49X/Wc4G3DG1HWUTduwyD3vXoWq1P0e9TSAixXghxN3o28M3oGrxNwNN0A225IQz+GvjceFYXoNshAYwFitpxrE7JYi6lzEd3DKjnFWCSEGIV+kvH1jYcYw263dIKYDnwrJRyrbF5C3CDcf3ptMML7gjpls+EontQbzSnUCiawbBreVlKeWZXt+VoI3Tvr1ellLO6ui3HC0KIZOA5KeXlXd0WheJ4RAlGCkUbEEJcAXwmpazp6rYcTYQQk9FtNta1WlmhUCiOAZRgpFAoFAqFQmGgbIwUCoVCoVAoDJRgpFAoFAqFQmGgBCOFQqFQKBQKAyUYKRQKhUKhUBgowUihUCgUCoXC4P8DxiOZ8ab4u6YAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="The-Points-System">The Points System<a class="anchor-link" href="#The-Points-System">&#182;</a></h2><p>Now that the comments activity has been explored, it would be relevant to look into the Points column, 'num_points' of the dataset. A point in the Hacker News website works as a vote. The number of points in a post equals the number of users that voted for that post. The same work done in the 'num_comments' columns will be now done in this column,. That is, determine which category, 'Show HN' or 'Ask HN, receives more points on average and depending on the answer determine at what time the comments get more points.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Use the &#39;categorized_df&#39; dataframe created before, which already filtered the &#39;Ask HN&#39; and &#39;Show HN&#39; posts:</span>
<span class="n">mean</span> <span class="o">=</span> <span class="n">categorized_df</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Category&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Average points:</span><span class="se">\n\n</span><span class="s1">&#39;</span><span class="p">,</span><span class="n">mean</span><span class="p">[</span><span class="s1">&#39;num_points&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average points:

 Category
Ask HN     11.311741
Show HN    14.843572
Name: num_points, dtype: float64
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Create a point plot to visualize the difference:</span>
<span class="o">%</span><span class="k">matplotlib</span> inline

<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mf">6.5</span><span class="p">,</span><span class="mi">4</span><span class="p">))</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">pointplot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Category&#39;</span><span class="p">,</span> 
                   <span class="n">y</span><span class="o">=</span><span class="s1">&#39;num_points&#39;</span><span class="p">,</span>
                   <span class="n">color</span><span class="o">=</span><span class="s1">&#39;#229954&#39;</span><span class="p">,</span>
                   <span class="n">data</span><span class="o">=</span><span class="n">categorized_df</span><span class="p">,</span><span class="n">scale</span><span class="o">=</span><span class="mf">1.1</span><span class="p">)</span>
<span class="n">sns</span><span class="o">.</span><span class="n">despine</span><span class="p">(</span><span class="n">left</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span><span class="n">bottom</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">axes</span><span class="o">.</span><span class="n">set_ylim</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">20</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">xaxis</span><span class="o">.</span><span class="n">set_ticks_position</span><span class="p">(</span><span class="s1">&#39;none&#39;</span><span class="p">)</span> <span class="c1">#Remove x axis ticks</span>
<span class="n">ax</span><span class="o">.</span><span class="n">yaxis</span><span class="o">.</span><span class="n">set_ticks_position</span><span class="p">(</span><span class="s1">&#39;none&#39;</span><span class="p">)</span> <span class="c1">#Remove y axis ticks</span>
<span class="n">ax</span><span class="o">.</span><span class="n">yaxis</span><span class="o">.</span><span class="n">set_major_locator</span><span class="p">(</span><span class="n">ticker</span><span class="o">.</span><span class="n">MultipleLocator</span><span class="p">(</span><span class="mi">4</span><span class="p">))</span> <span class="c1">#Y axis intervals (step).</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set</span><span class="p">(</span><span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;Post Category&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;Avg Number of Points&#39;</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="n">ChartTitle</span><span class="p">(</span><span class="s1">&#39;Average Number of Points</span><span class="se">\n</span><span class="s1">for Ask HN and Show HN&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">getTitle</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="'Show-HN'-has-a-higher-average-of-Points">'Show HN' has a higher average of Points<a class="anchor-link" href="#'Show-HN'-has-a-higher-average-of-Points">&#182;</a></h2><p>Show HN posts get more points on average than Ask HN posts, opposite dynamic than when measuring the amount of comments. The next step is to keep analyzing the Show HN posts by finding out which hour of the day has the most average points.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Find the hour of the day with the most points for Show HN posts:</span>
<span class="c1">#(The show_df dataframe was created at the begining of this project)</span>

<span class="c1">#Convert &#39;created_at&#39; column into datetime format</span>
<span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;created_at&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;created_at&#39;</span><span class="p">],</span><span class="nb">format</span><span class="o">=</span><span class="s1">&#39;%m/</span><span class="si">%d</span><span class="s1">/%Y %H:%M&#39;</span><span class="p">)</span>
<span class="c1">#Extract just the hour from the &#39;created_at&#39; column, so a grouping by hour can be done</span>
<span class="n">hour</span> <span class="o">=</span> <span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;created_at&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">hour</span>
<span class="c1">#&#39;Hour&#39; column created to group by that column, last map() function ignores seconds</span>
<span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Hour&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">hour</span><span class="p">,</span><span class="nb">format</span><span class="o">=</span><span class="s1">&#39;%H&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">time</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">t</span><span class="p">:</span> 
                                                              <span class="n">t</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="s1">&#39;%H:%M&#39;</span><span class="p">))</span>
<span class="c1">#Group by hour</span>
<span class="n">avgP_by_hour</span> <span class="o">=</span> <span class="n">show_df</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Hour&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;num_points&#39;</span><span class="p">,</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Average points per hour (Eastern Time):</span><span class="se">\n\n</span><span class="s1">&#39;</span><span class="p">,</span>
      <span class="n">avgP_by_hour</span><span class="p">[</span><span class="s1">&#39;num_points&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="s1">&#39;average </span><span class="si">{:,.2f}</span><span class="s1"> points per post.&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average points per hour (Eastern Time):

 Hour
12:00    average 20.91 points per post.
11:00    average 19.26 points per post.
13:00    average 17.02 points per post.
19:00    average 16.06 points per post.
06:00    average 15.99 points per post.
Name: num_points, dtype: object
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Post-Creation-Hours-with-highest-average-of-points">Post Creation Hours with highest average of points<a class="anchor-link" href="#Post-Creation-Hours-with-highest-average-of-points">&#182;</a></h2><p>The hour a post was created receiving the highest average of points is 12:00 Eastern Time. A Show HN post has a higher chance to get more points at this hour. A plot showing the number of points for each of the top 5 hours is  helpful to compare times. The plto is shown in the next section.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Plotting-the-Number-of-Points-per-Hour">Plotting the Number of Points per Hour<a class="anchor-link" href="#Plotting-the-Number-of-Points-per-Hour">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#First create a new column to have the Nairobi Time already available:</span>
<span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Hour&#39;</span><span class="p">]</span>
<span class="c1">#Convert the new column to datetime so the timedelta operation can be done</span>
<span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">])</span>
<span class="c1">#We know now that Nairobi Time equals Eastern Time + 8 hours</span>
<span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span><span class="o">+</span><span class="n">dt</span><span class="o">.</span><span class="n">timedelta</span><span class="p">(</span><span class="n">hours</span><span class="o">=</span><span class="mi">8</span><span class="p">)</span>
<span class="c1">#Format the Nairobi Time column to show just the hour and minutes as a string</span>
<span class="n">Nai_hour</span> <span class="o">=</span> <span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">hour</span>
<span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">Nai_hour</span><span class="p">,</span><span class="nb">format</span><span class="o">=</span><span class="s1">&#39;%H&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">time</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">t</span><span class="p">:</span> 
                                                              <span class="n">t</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="s1">&#39;%H:%M&#39;</span><span class="p">))</span>
<span class="n">show_df</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[13]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>title</th>
      <th>url</th>
      <th>num_points</th>
      <th>num_comments</th>
      <th>author</th>
      <th>created_at</th>
      <th>Category</th>
      <th>Hour</th>
      <th>Nairobi_Time</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>52</th>
      <td>12578335</td>
      <td>Show HN: Finding puns computationally</td>
      <td>http://puns.samueltaylor.org/</td>
      <td>2</td>
      <td>0</td>
      <td>saamm</td>
      <td>2016-09-26 00:36:00</td>
      <td>Show HN</td>
      <td>00:00</td>
      <td>08:00</td>
    </tr>
    <tr>
      <th>58</th>
      <td>12578182</td>
      <td>Show HN: A simple library for complicated anim...</td>
      <td>https://christinecha.github.io/choreographer-js/</td>
      <td>1</td>
      <td>0</td>
      <td>christinecha</td>
      <td>2016-09-26 00:01:00</td>
      <td>Show HN</td>
      <td>00:00</td>
      <td>08:00</td>
    </tr>
    <tr>
      <th>64</th>
      <td>12578098</td>
      <td>Show HN: WebGL visualization of DNA sequences</td>
      <td>http://grondilu.github.io/dna.html</td>
      <td>1</td>
      <td>0</td>
      <td>grondilu</td>
      <td>2016-09-25 23:44:00</td>
      <td>Show HN</td>
      <td>23:00</td>
      <td>07:00</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Filter show_df to show only the top 5 hours discovered above</span>
<span class="n">show_df_top_hrs</span> <span class="o">=</span> <span class="n">show_df</span><span class="p">[</span><span class="n">show_df</span><span class="p">[</span><span class="s1">&#39;Hour&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">isin</span><span class="p">(</span><span class="n">avgP_by_hour</span><span class="p">[</span><span class="s1">&#39;num_points&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">index</span><span class="p">)]</span>
<span class="c1">#Sort by column &#39;Hour&#39;</span>
<span class="n">show_df_top_hrs</span> <span class="o">=</span> <span class="n">show_df_top_hrs</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;Hour&#39;</span><span class="p">)</span>
<span class="c1">#Display result</span>
<span class="n">show_df_top_hrs</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[14]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>title</th>
      <th>url</th>
      <th>num_points</th>
      <th>num_comments</th>
      <th>author</th>
      <th>created_at</th>
      <th>Category</th>
      <th>Hour</th>
      <th>Nairobi_Time</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>233400</th>
      <td>10613173</td>
      <td>Show HN: RC-455  A WebAudio Synthesizer</td>
      <td>http://barakchamo.github.io/rc455</td>
      <td>35</td>
      <td>20</td>
      <td>BarakChamo</td>
      <td>2015-11-23 06:24:00</td>
      <td>Show HN</td>
      <td>06:00</td>
      <td>14:00</td>
    </tr>
    <tr>
      <th>132131</th>
      <td>11428264</td>
      <td>Show HN: Module loader for chrome console</td>
      <td>https://chrome.google.com/webstore/detail/r42-...</td>
      <td>13</td>
      <td>3</td>
      <td>chadscira</td>
      <td>2016-04-05 06:23:00</td>
      <td>Show HN</td>
      <td>06:00</td>
      <td>14:00</td>
    </tr>
    <tr>
      <th>44905</th>
      <td>12178635</td>
      <td>Show HN: AtGet.rb v3.0  Apple Trailers Downloader</td>
      <td>https://github.com/tuxy/ruby/blob/master/atget.rb</td>
      <td>1</td>
      <td>0</td>
      <td>tux</td>
      <td>2016-07-28 06:05:00</td>
      <td>Show HN</td>
      <td>06:00</td>
      <td>14:00</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Plot:</span>
<span class="c1">#First make a list of labels for the x axis to show both Eastern Time and Nairobi Time:</span>
<span class="n">labels</span> <span class="o">=</span> <span class="p">[]</span>
<span class="c1">#sort times </span>
<span class="n">Etimes</span> <span class="o">=</span> <span class="n">show_df_top_hrs</span><span class="p">[</span><span class="s1">&#39;Hour&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">unique</span><span class="p">()</span>
<span class="n">Ntimes</span> <span class="o">=</span> <span class="n">show_df_top_hrs</span><span class="p">[</span><span class="s1">&#39;Nairobi_Time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">unique</span><span class="p">()</span>
<span class="c1">#append values to list</span>
<span class="k">for</span> <span class="n">h</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">avg_by_local_hour</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span><span class="o">.</span><span class="n">index</span><span class="p">)):</span>
    <span class="n">labels</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s1">&#39;</span><span class="si">{}</span><span class="s1"> ET</span><span class="se">\n</span><span class="si">{}</span><span class="s1"> NT&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">Etimes</span><span class="p">[</span><span class="n">h</span><span class="p">],</span>
                                        <span class="n">Ntimes</span><span class="p">[</span><span class="n">h</span><span class="p">]))</span>
<span class="c1">#Create plot</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">catplot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Hour&#39;</span><span class="p">,</span> 
                   <span class="n">y</span><span class="o">=</span><span class="s1">&#39;num_points&#39;</span><span class="p">,</span>
                   <span class="n">hue</span><span class="o">=</span><span class="s1">&#39;Hour&#39;</span><span class="p">,</span>
                   <span class="n">data</span><span class="o">=</span><span class="n">show_df_top_hrs</span><span class="p">,</span>
                   <span class="n">height</span><span class="o">=</span><span class="mf">5.5</span><span class="p">,</span><span class="n">aspect</span><span class="o">=</span><span class="mf">1.5</span><span class="p">,</span><span class="n">jitter</span><span class="o">=</span><span class="mf">0.3</span><span class="p">,</span><span class="n">palette</span><span class="o">=</span><span class="s1">&#39;Dark2_r&#39;</span><span class="p">)</span>
<span class="n">sns</span><span class="o">.</span><span class="n">despine</span><span class="p">(</span><span class="n">left</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span><span class="n">bottom</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_axis_labels</span><span class="p">(</span><span class="s1">&#39;Hour (24hr format) ET=Eastern Time,  NT=Nairobi Time&#39;</span><span class="p">,</span><span class="s1">&#39;Number of Points&#39;</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_xticklabels</span><span class="p">(</span><span class="n">labels</span><span class="p">)</span> <span class="c1">#pass the labels list with the two times</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">ChartTitle</span><span class="p">(</span><span class="s1">&#39;Number of Show HN Points in top 5 Hours&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">getTitle</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">tick_params</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">which</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span><span class="n">length</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Graph 4 above shows the hour of highest average points, 12:00 Eastern Time (20:00 Nairobi Time) as compared with the other top 5 hours. It can be seen that at hour 11:00 ET a single post obtained around 1,000 points.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Other-posts">Other posts<a class="anchor-link" href="#Other-posts">&#182;</a></h2><p>There are other types of posts in the Hacker News website which are not labeled as Ask HN or Show HN. To make this analysis complete, an exploration of the number of comments and number of points will be performed on the other posts.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">other_df</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="o">~</span><span class="n">ask_posts</span> <span class="o">|</span> <span class="o">~</span><span class="n">show_posts</span><span class="p">]</span> <span class="c1">#Use the ~ to indicate this variables are excluded</span>

<span class="c1">#Create a &#39;Category&#39; column were all comments are labeled as &#39;Other&#39;</span>
<span class="n">other_df</span><span class="p">[</span><span class="s1">&#39;Category&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="s1">&#39;Other&#39;</span>

<span class="c1">#Append this to the &#39;categorized_df&#39; dataframe created before</span>
<span class="n">new_categorized_df</span> <span class="o">=</span> <span class="n">categorized_df</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">other_df</span><span class="p">)</span>
<span class="c1">#Group by category and produce mean:</span>
<span class="n">mean</span> <span class="o">=</span> <span class="n">new_categorized_df</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Category&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Average comments:</span><span class="se">\n\n</span><span class="s1">&#39;</span><span class="p">,</span><span class="n">mean</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average comments:

 Category
Ask HN     10.393478
Other       6.525544
Show HN     4.886100
Name: num_comments, dtype: float64
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%</span><span class="k">matplotlib</span> inline

<span class="c1">#Use the melt() function to unpivot the dataframe and </span>
<span class="c1">#set the columns &#39;num_comments&#39; and &#39;num_points&#39; as values of a column named &#39;Variables&#39;</span>
<span class="n">plot_df</span> <span class="o">=</span> <span class="n">new_categorized_df</span><span class="o">.</span><span class="n">melt</span><span class="p">(</span><span class="s1">&#39;Category&#39;</span><span class="p">,</span> 
                                  <span class="n">value_vars</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;num_comments&#39;</span><span class="p">,</span><span class="s1">&#39;num_points&#39;</span><span class="p">],</span>
                                  <span class="n">var_name</span><span class="o">=</span><span class="s1">&#39;Variables&#39;</span><span class="p">,</span>  
                                  <span class="n">value_name</span><span class="o">=</span><span class="s1">&#39;Count&#39;</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mf">6.5</span><span class="p">,</span><span class="mi">4</span><span class="p">))</span>

<span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">pointplot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Category&#39;</span><span class="p">,</span> 
                   <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Count&#39;</span><span class="p">,</span>
                   <span class="n">hue</span><span class="o">=</span><span class="s1">&#39;Variables&#39;</span><span class="p">,</span>
                   <span class="n">data</span><span class="o">=</span><span class="n">plot_df</span><span class="p">,</span><span class="n">scale</span><span class="o">=</span><span class="mf">1.1</span><span class="p">)</span>
<span class="n">sns</span><span class="o">.</span><span class="n">despine</span><span class="p">(</span><span class="n">left</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span><span class="n">bottom</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">axes</span><span class="o">.</span><span class="n">set_ylim</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">18</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">xaxis</span><span class="o">.</span><span class="n">set_ticks_position</span><span class="p">(</span><span class="s1">&#39;none&#39;</span><span class="p">)</span> <span class="c1">#Remove x axis ticks</span>
<span class="n">ax</span><span class="o">.</span><span class="n">yaxis</span><span class="o">.</span><span class="n">set_ticks_position</span><span class="p">(</span><span class="s1">&#39;none&#39;</span><span class="p">)</span> <span class="c1">#Remove y axis ticks</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set</span><span class="p">(</span><span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;Post Category&#39;</span><span class="p">,</span><span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;Average Number&#39;</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">xaxis</span><span class="o">.</span><span class="n">labelpad</span> <span class="o">=</span> <span class="mi">15</span> <span class="c1">#Move the x axis label downward</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="n">ChartTitle</span><span class="p">(</span><span class="s1">&#39;Average Number of Comments</span><span class="se">\n</span><span class="s1">and Points per Category&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">getTitle</span><span class="p">())</span>
<span class="n">ax</span><span class="o">.</span><span class="n">legend</span><span class="p">(</span><span class="n">bbox_to_anchor</span><span class="o">=</span><span class="p">(</span><span class="mf">1.05</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span><span class="n">loc</span><span class="o">=</span><span class="s1">&#39;best&#39;</span><span class="p">,</span><span class="n">title</span><span class="o">=</span><span class="s1">&#39;Variables&#39;</span><span class="p">)</span> <span class="c1">#Move legend outside</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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88EHH8zu27fvoH79+g085JBD+tXkM67LIcFPAZ8A/cxspZldDDwI9AqHCT8NnK9HNyIiEq+IOy98sbJDVdvsKonYE58ti6u1ZPny5S2uuOKKdYsWLZrTunXrkkcffTS7qu0XLFjQ8oUXXljy+eef5/3ud7/LycjIiOTl5c095JBDtt97772VxjJx4sSel1566br58+fPnTZt2rxu3brtfvTRR9vMmjWrZV5e3pz33ntvwa9//esuy5YtawYwb968ln/7299W5OXlzXn++efbLViwoMWsWbPyzj333A133nlnx9Ljbt26Ne2TTz5ZcOutt64444wz+v785z9fu3Dhwjnz5s1r+Z///Kfl6tWr02655Zb9P/zwwwVz587NO+iggwp/85vfdCrdv3379sVz587Nu+iii9bfeuutnfr167frvPPOW3/ppZeunTdv3twTTzyx4NZbb93/nXfeWTB//vy5b7311qKafL511qfE3c+qZNU5dXVOERFpmnbsLrF1+TurnQRv8bqClvGcJycnZ+eoUaOKAIYPH164dOnS5lVtP2rUqPzs7OxIdnZ2JDMzs+S0007bAjBkyJDCmTNnZlS0z+bNm1PWrl2bft55520ByMjIcMA/+uijrNNPP31TWloaXbt2LR45cmTBxx9/nNG6devIkCFDtnfv3n03QLdu3XaOGzduK8DQoUOLpkyZklV67JNOOmlLSkoKBx10UGG7du12jxgxogggNze3aPHixc2XLVuWvnjx4hYjRozoD7B79247+OCDC0r3nzhx4maAESNGFL7yyisVJmSHHHJIwdlnn91jwoQJm88+++zNMX60gCbkExGRRiA9LcXTUsyLI17l/DsZzdPimpwuPT19T+t+amqqFxUVpaSlpXlJSXDYwsJCq2z7lJQUWrRo4aWvi4uLK4y1sgcIVT1YaN68eaXnKSkp2XOe0uWpqal7xVZcXGypqal+5JFHbnv11Ve/qug8pfunpaV5ZfE/+eSTy99///1Wr7zySuthw4YNmj59+pzOnTvH9LlrqJSISG1aPROm3A7v3gSznofinfUdUZOQlpLCqD7tt1S33bjBnavdpqa6du26c+rUqa0AnnjiiSof58Sibdu2kc6dO+967LHH2gAUFRVZfn5+ytFHH53//PPPty0uLmbVqlVpU6dOzTzqqKPiHvESbfTo0dunTZuW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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Graph 5 above shows that other posts don't receive a considerable amount of comments in average, but they do get slightly more points than the Show HN category and much more points than the Ask HN category.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Conclusion">Conclusion<a class="anchor-link" href="#Conclusion">&#182;</a></h2><p>Hacker News is a website where tech and startup stories are shared. As any other posting service, it enables the interaction among its users. The stories that get the most engagement (number of comments/points) aquire more visibility hence giving more attention to the author of the post. This small project was able to establish three things:</p>
<ul>
<li>What types of posts are found in Hacker News.com.</li>
<li>The average number of comments for each type of post.</li>
<li>The time of day in which a post is created may have incidence in the amount of points and comments it receives.</li>
</ul>

</div>
</div>
</div>
    </div>
  </div>
</body>

 


</html>

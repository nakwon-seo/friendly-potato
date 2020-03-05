# friendly-potato
learning Python and interested in data-visualisation and analytics

current Project with Python
Visualising GDP data of the World

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>DV5_GDP_world(box,scatter)</title>

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

<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[235]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[236]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%</span><span class="k">matplotlib</span> inline
<span class="kn">import</span> <span class="nn">matplotlib</span> <span class="k">as</span> <span class="nn">mpl</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[237]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="s2">&quot;http://api.worldbank.org/v2/en/indicator/NY.GDP.MKTP.CD?downloadformat=excel&quot;</span><span class="p">,</span><span class="n">skiprows</span><span class="o">=</span><span class="nb">range</span><span class="p">(</span><span class="mi">3</span><span class="p">))</span>
<span class="c1">#df_gdp.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[238]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">.</span><span class="n">shape</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[238]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>(264, 64)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[239]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;Country Code&#39;</span><span class="p">,</span><span class="s1">&#39;Indicator Name&#39;</span><span class="p">,</span><span class="s1">&#39;Indicator Code&#39;</span><span class="p">],</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_gdp</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s1">&#39;2019&#39;</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="c1">#df_gdp.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[240]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;Country Name&#39;</span><span class="p">:</span><span class="s1">&#39;Country&#39;</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="c1">#df_gdp.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[241]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">.</span><span class="n">set_index</span><span class="p">([</span><span class="s1">&#39;Country&#39;</span><span class="p">],</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="c1">#df_gdp.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[242]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">df_gdp</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span><span class="s1">&#39;1960&#39;</span><span class="p">:</span><span class="s1">&#39;1979&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">columns</span><span class="p">,</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="c1">#df_gdp.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[243]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;Arab World&#39;</span><span class="p">,</span><span class="s1">&#39;Central Europe and the Baltics&#39;</span><span class="p">,</span><span class="s1">&#39;East Asia &amp; Pacific (excluding high income)&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Early-demographic dividend&#39;</span><span class="p">,</span><span class="s1">&#39;East Asia &amp; Pacific&#39;</span><span class="p">,</span><span class="s1">&#39;Europe &amp; Central Asia (excluding high income)&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Europe &amp; Central Asia&#39;</span><span class="p">,</span><span class="s1">&#39;Euro area&#39;</span><span class="p">,</span><span class="s1">&#39;European Union&#39;</span><span class="p">,</span><span class="s1">&#39;Fragile and conflict affected situations&#39;</span><span class="p">,</span><span class="s1">&#39;High income&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Heavily indebted poor countries (HIPC)&#39;</span><span class="p">,</span><span class="s1">&#39;IBRD only&#39;</span><span class="p">,</span><span class="s1">&#39;IDA &amp; IBRD total&#39;</span><span class="p">,</span><span class="s1">&#39;IDA total&#39;</span><span class="p">,</span><span class="s1">&#39;IDA blend&#39;</span><span class="p">,</span><span class="s1">&#39;IDA only&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Latin America &amp; Caribbean (excluding high income)&#39;</span><span class="p">,</span><span class="s1">&#39;Lao PDR&#39;</span><span class="p">,</span><span class="s1">&#39;Latin America &amp; Caribbean&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Least developed countries: UN classification&#39;</span><span class="p">,</span><span class="s1">&#39;Low income&#39;</span><span class="p">,</span><span class="s1">&#39;Lower middle income&#39;</span><span class="p">,</span><span class="s1">&#39;Low &amp; middle income&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Late-demographic dividend&#39;</span><span class="p">,</span><span class="s1">&#39;Middle East &amp; North Africa&#39;</span><span class="p">,</span><span class="s1">&#39;Middle income&#39;</span><span class="p">,</span><span class="s1">&#39;Middle East &amp; North Africa (excluding high income)&#39;</span><span class="p">,</span>
             <span class="s1">&#39;OECD members&#39;</span><span class="p">,</span><span class="s1">&#39;Other small states&#39;</span><span class="p">,</span><span class="s1">&#39;Pre-demographic dividend&#39;</span><span class="p">,</span><span class="s1">&#39;West Bank and Gaza&#39;</span><span class="p">,</span><span class="s1">&#39;Pacific island small states&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Post-demographic dividend&#39;</span><span class="p">,</span><span class="s1">&#39;South Asia&#39;</span><span class="p">,</span><span class="s1">&#39;Sub-Saharan Africa (excluding high income)&#39;</span><span class="p">,</span><span class="s1">&#39;Small states&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Turks and Caicos Islands&#39;</span><span class="p">,</span><span class="s1">&#39;East Asia &amp; Pacific (IDA &amp; IBRD countries)&#39;</span><span class="p">,</span><span class="s1">&#39;Europe &amp; Central Asia (IDA &amp; IBRD countries)&#39;</span><span class="p">,</span>
             <span class="s1">&#39;Latin America &amp; the Caribbean (IDA &amp; IBRD countries)&#39;</span><span class="p">,</span><span class="s1">&#39;Middle East &amp; North Africa (IDA &amp; IBRD countries)&#39;</span><span class="p">,</span>
             <span class="s1">&#39;South Asia (IDA &amp; IBRD)&#39;</span><span class="p">,</span><span class="s1">&#39;Sub-Saharan Africa (IDA &amp; IBRD countries)&#39;</span><span class="p">,</span><span class="s1">&#39;Upper middle income&#39;</span><span class="p">,</span><span class="s1">&#39;World&#39;</span><span class="p">,</span><span class="s1">&#39;North America&#39;</span><span class="p">,</span><span class="s1">&#39;Sub-Saharan Africa&#39;</span><span class="p">],</span> 
            <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="c1">#df_gdp.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[244]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">all</span><span class="p">(</span><span class="nb">isinstance</span><span class="p">(</span><span class="n">column</span><span class="p">,</span> <span class="nb">str</span><span class="p">)</span> <span class="k">for</span> <span class="n">column</span> <span class="ow">in</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">columns</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[244]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>True</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[245]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">str</span><span class="p">,</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">columns</span><span class="p">))</span>
<span class="nb">all</span><span class="p">(</span><span class="nb">isinstance</span><span class="p">(</span><span class="n">column</span><span class="p">,</span> <span class="nb">str</span><span class="p">)</span> <span class="k">for</span> <span class="n">column</span> <span class="ow">in</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">columns</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[245]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>True</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[246]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span> <span class="p">(</span><span class="s1">&#39;data dimensions:&#39;</span><span class="p">,</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>data dimensions: (216, 39)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[247]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="o">.</span><span class="n">columns</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">str</span><span class="p">,</span><span class="n">df_gdp</span><span class="o">.</span><span class="n">columns</span><span class="p">))</span>
<span class="n">years</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">str</span><span class="p">,</span><span class="nb">range</span><span class="p">(</span><span class="mi">1980</span><span class="p">,</span><span class="mi">2019</span><span class="p">)))</span>
<span class="c1">#years</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[248]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span><span class="p">[</span><span class="s1">&#39;Total&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[249]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[250]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;2018&#39;</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[251]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#df_gdp.sort_values([&#39;Total&#39;], ascending=False)</span>

<span class="n">df_gdp_top15</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="p">[</span><span class="s1">&#39;2018&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">15</span><span class="p">)</span>
<span class="c1">#df_gdp_top15</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[252]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_top15</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="p">[</span><span class="n">years</span><span class="p">]</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">15</span><span class="p">)</span>
<span class="c1">#df_gdp_top15</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[253]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">years_80s</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">str</span><span class="p">,</span><span class="nb">range</span><span class="p">(</span><span class="mi">1980</span><span class="p">,</span><span class="mi">1990</span><span class="p">)))</span>
<span class="n">years_90s</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">str</span><span class="p">,</span><span class="nb">range</span><span class="p">(</span><span class="mi">1990</span><span class="p">,</span><span class="mi">2000</span><span class="p">)))</span>
<span class="n">years_00s</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">str</span><span class="p">,</span><span class="nb">range</span><span class="p">(</span><span class="mi">2000</span><span class="p">,</span><span class="mi">2010</span><span class="p">)))</span>
<span class="n">years_10s</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">str</span><span class="p">,</span><span class="nb">range</span><span class="p">(</span><span class="mi">2010</span><span class="p">,</span><span class="mi">2018</span><span class="p">)))</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[254]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_80s</span><span class="o">=</span><span class="n">df_gdp_top15</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span><span class="n">years_80s</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_90s</span><span class="o">=</span><span class="n">df_gdp_top15</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span><span class="n">years_90s</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_00s</span><span class="o">=</span><span class="n">df_gdp_top15</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span><span class="n">years_00s</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_10s</span><span class="o">=</span><span class="n">df_gdp_top15</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span><span class="n">years_10s</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>

<span class="n">new_df_gdp</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span><span class="s1">&#39;1980s&#39;</span><span class="p">:</span> <span class="n">df_80s</span><span class="p">,</span> <span class="s1">&#39;1990s&#39;</span><span class="p">:</span> <span class="n">df_90s</span><span class="p">,</span> <span class="s1">&#39;2000s&#39;</span><span class="p">:</span><span class="n">df_00s</span><span class="p">,</span><span class="s1">&#39;2010s&#39;</span><span class="p">:</span><span class="n">df_10s</span><span class="p">})</span> 
<span class="c1">#new_df_gdp.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[255]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">new_df_gdp</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[255]:</div>



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
      <th>1980s</th>
      <th>1990s</th>
      <th>2000s</th>
      <th>2010s</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>1.500000e+01</td>
      <td>1.500000e+01</td>
      <td>1.500000e+01</td>
      <td>1.500000e+01</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>7.296921e+11</td>
      <td>1.504947e+12</td>
      <td>2.393222e+12</td>
      <td>3.737991e+12</td>
    </tr>
    <tr>
      <td>std</td>
      <td>1.051871e+12</td>
      <td>1.974921e+12</td>
      <td>3.024871e+12</td>
      <td>4.299314e+12</td>
    </tr>
    <tr>
      <td>min</td>
      <td>1.061214e+11</td>
      <td>3.535083e+11</td>
      <td>6.541588e+11</td>
      <td>1.179324e+12</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>2.170417e+11</td>
      <td>4.366282e+11</td>
      <td>8.483836e+11</td>
      <td>1.538744e+12</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>2.733753e+11</td>
      <td>6.427365e+11</td>
      <td>1.102224e+12</td>
      <td>2.060247e+12</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>6.769944e+11</td>
      <td>1.378911e+12</td>
      <td>2.458038e+12</td>
      <td>3.171702e+12</td>
    </tr>
    <tr>
      <td>max</td>
      <td>4.173163e+12</td>
      <td>7.577130e+12</td>
      <td>1.259074e+13</td>
      <td>1.718126e+13</td>
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
<div class="prompt input_prompt">In&nbsp;[256]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">new_df_gdp</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;box&#39;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">6</span><span class="p">))</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;GDP from top 15 countries for decades 80s, 90s, 2000s and 2010s&#39;</span><span class="p">)</span>
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
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[257]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">new_df_gdp</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">15</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[257]:</div>



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
      <th>1980s</th>
      <th>1990s</th>
      <th>2000s</th>
      <th>2010s</th>
    </tr>
    <tr>
      <th>Country</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>United States</td>
      <td>4.173163e+12</td>
      <td>7.577130e+12</td>
      <td>1.259074e+13</td>
      <td>1.718126e+13</td>
    </tr>
    <tr>
      <td>China</td>
      <td>2.626079e+11</td>
      <td>6.863142e+11</td>
      <td>2.592138e+12</td>
      <td>9.559601e+12</td>
    </tr>
    <tr>
      <td>Japan</td>
      <td>1.815785e+12</td>
      <td>4.327938e+12</td>
      <td>4.663733e+12</td>
      <td>5.280374e+12</td>
    </tr>
    <tr>
      <td>Germany</td>
      <td>9.900306e+11</td>
      <td>2.177681e+12</td>
      <td>2.764824e+12</td>
      <td>3.596108e+12</td>
    </tr>
    <tr>
      <td>United Kingdom</td>
      <td>6.244775e+11</td>
      <td>1.326610e+12</td>
      <td>2.323938e+12</td>
      <td>2.747296e+12</td>
    </tr>
    <tr>
      <td>France</td>
      <td>7.295113e+11</td>
      <td>1.431213e+12</td>
      <td>2.096976e+12</td>
      <td>2.668358e+12</td>
    </tr>
    <tr>
      <td>India</td>
      <td>2.364114e+11</td>
      <td>3.535083e+11</td>
      <td>8.303781e+11</td>
      <td>2.033552e+12</td>
    </tr>
    <tr>
      <td>Italy</td>
      <td>5.934750e+11</td>
      <td>1.216282e+12</td>
      <td>1.756476e+12</td>
      <td>2.060247e+12</td>
    </tr>
    <tr>
      <td>Brazil</td>
      <td>2.733753e+11</td>
      <td>6.427365e+11</td>
      <td>9.709591e+11</td>
      <td>2.233893e+12</td>
    </tr>
    <tr>
      <td>Canada</td>
      <td>3.835417e+11</td>
      <td>6.145255e+11</td>
      <td>1.102224e+12</td>
      <td>1.699578e+12</td>
    </tr>
    <tr>
      <td>Russian Federation</td>
      <td>1.061214e+11</td>
      <td>3.984282e+11</td>
      <td>7.870291e+11</td>
      <td>1.796111e+12</td>
    </tr>
    <tr>
      <td>Korea, Rep.</td>
      <td>1.201236e+11</td>
      <td>4.368263e+11</td>
      <td>8.085874e+11</td>
      <td>1.320629e+12</td>
    </tr>
    <tr>
      <td>Australia</td>
      <td>1.976719e+11</td>
      <td>3.584317e+11</td>
      <td>6.541588e+11</td>
      <td>1.377911e+12</td>
    </tr>
    <tr>
      <td>Spain</td>
      <td>2.516406e+11</td>
      <td>5.901462e+11</td>
      <td>1.089771e+12</td>
      <td>1.335622e+12</td>
    </tr>
    <tr>
      <td>Mexico</td>
      <td>1.874451e+11</td>
      <td>4.364301e+11</td>
      <td>8.663890e+11</td>
      <td>1.179324e+12</td>
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
<div class="prompt input_prompt">In&nbsp;[386]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#&#39;Scatter plots&#39;</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[387]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_tal</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">df_gdp</span><span class="p">[</span><span class="n">years</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">))</span>

<span class="n">df_gdp_tal</span><span class="o">.</span><span class="n">index</span> <span class="o">=</span> <span class="nb">map</span><span class="p">(</span><span class="nb">int</span><span class="p">,</span> <span class="n">df_gdp_tal</span><span class="o">.</span><span class="n">index</span><span class="p">)</span>

<span class="n">df_gdp_tal</span><span class="o">.</span><span class="n">reset_index</span><span class="p">(</span><span class="n">inplace</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>

<span class="n">df_gdp_tal</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="s1">&#39;total&#39;</span><span class="p">]</span>

<span class="n">df_gdp_tal</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[387]:</div>



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
      <th>year</th>
      <th>total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1980</td>
      <td>1.069390e+13</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1981</td>
      <td>1.107674e+13</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1982</td>
      <td>1.097108e+13</td>
    </tr>
    <tr>
      <td>3</td>
      <td>1983</td>
      <td>1.118908e+13</td>
    </tr>
    <tr>
      <td>4</td>
      <td>1984</td>
      <td>1.159689e+13</td>
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
<div class="prompt input_prompt">In&nbsp;[388]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_tal</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;total&#39;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">6</span><span class="p">),</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;#800000&#39;</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;World GDP from 1980 - 2018&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Year&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;GDP(current US$)&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[388]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0, 0.5, &#39;GDP(current US$)&#39;)</pre>
</div>

</div>

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
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[389]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_top3</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">loc</span><span class="p">[[</span><span class="s1">&#39;United States&#39;</span><span class="p">,</span><span class="s1">&#39;Japan&#39;</span><span class="p">,</span><span class="s1">&#39;China&#39;</span><span class="p">],</span> <span class="n">years</span><span class="p">]</span><span class="o">.</span><span class="n">transpose</span><span class="p">()</span>
<span class="c1">#df_gdp_top3.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[390]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_tal2</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">df_gdp_top3</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
<span class="n">df_gdp_tal2</span><span class="o">.</span><span class="n">reset_index</span><span class="p">(</span><span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="n">df_gdp_tal2</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="s1">&#39;total&#39;</span><span class="p">]</span>
<span class="n">df_gdp_tal2</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_gdp_tal2</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>

<span class="c1">#df_gdp_tal2.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[391]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_mi3</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">loc</span><span class="p">[[</span><span class="s1">&#39;India&#39;</span><span class="p">,</span><span class="s1">&#39;Italy&#39;</span><span class="p">,</span><span class="s1">&#39;Brazil&#39;</span><span class="p">],</span> <span class="n">years</span><span class="p">]</span><span class="o">.</span><span class="n">transpose</span><span class="p">()</span>
<span class="c1">#df_gdp_mi3.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[392]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_tal3</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">df_gdp_mi3</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
<span class="n">df_gdp_tal3</span> <span class="o">=</span> <span class="n">df_gdp_tal3</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>

<span class="n">df_gdp_tal3</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="s1">&#39;total&#39;</span><span class="p">]</span>
<span class="n">df_gdp_tal3</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_gdp_tal3</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>

<span class="c1">#df_gdp_tal3.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[393]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_least3</span> <span class="o">=</span> <span class="n">df_gdp</span><span class="o">.</span><span class="n">loc</span><span class="p">[[</span><span class="s1">&#39;Australia&#39;</span><span class="p">,</span><span class="s1">&#39;Spain&#39;</span><span class="p">,</span><span class="s1">&#39;Mexico&#39;</span><span class="p">],</span> <span class="n">years</span><span class="p">]</span><span class="o">.</span><span class="n">transpose</span><span class="p">()</span>
<span class="c1">#df_gdp_least3.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[394]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_gdp_tal4</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">df_gdp_least3</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
<span class="n">df_gdp_tal4</span> <span class="o">=</span> <span class="n">df_gdp_tal4</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>

<span class="n">df_gdp_tal4</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="s1">&#39;total&#39;</span><span class="p">]</span>
<span class="n">df_gdp_tal4</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_gdp_tal4</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>

<span class="c1">#df_gdp_tal4.head()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[395]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;fig = plt.figure()</span>

<span class="sd">ax0 = fig.add_subplot(2, 2, 1)</span>
<span class="sd">ax1 = fig.add_subplot(2, 2, 2)</span>
<span class="sd">ax2 = fig.add_subplot(2, 2, 3)</span>
<span class="sd">ax3 = fig.add_subplot(2, 2, 4)</span>




<span class="sd">df_gdp_tal.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;#800000&#39;, ax=ax0)</span>
<span class="sd">ax0.set_title(&#39;Total GDP from 1980 - 2018&#39;)</span>
<span class="sd">ax0.set_xlabel(&#39;Year&#39;)</span>
<span class="sd">ax0.set_ylabel(&#39;GDP(current US$)&#39;)</span>

<span class="sd">df_gdp_tal2.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;#00CED1&#39;, ax=ax1)</span>
<span class="sd">ax1.set_title (&#39;GDP from United States, Japan and China from 1980-2018&#39;)</span>
<span class="sd">ax1.set_ylabel(&#39;GDP(current US$)&#39;)</span>
<span class="sd">ax1.set_xlabel(&#39;Year&#39;)</span>

<span class="sd">df_gdp_tal3.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;pink&#39;, ax=ax2)</span>
<span class="sd">ax2.set_title (&#39;GDP from India, Italy and Brazil from 1980-2018&#39;)</span>
<span class="sd">ax2.set_xlabel(&#39;Year&#39;)</span>
<span class="sd">ax2.set_ylabel(&#39;GDP(current US$)&#39;)</span>

<span class="sd">df_gdp_tal4.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;#90EE90&#39;, ax=ax3)</span>
<span class="sd">ax3.set_title (&#39;GDP from Australia, Spain and Mexico from 1980-2018&#39;)</span>
<span class="sd">ax3.set_xlabel(&#39;Year&#39;)</span>
<span class="sd">ax3.set_ylabel(&#39;GDP(current US$)&#39;)</span>

<span class="sd">plt.show()&#39;&#39;&#39;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[395]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&#34;fig = plt.figure()\n\nax0 = fig.add_subplot(2, 2, 1)\nax1 = fig.add_subplot(2, 2, 2)\nax2 = fig.add_subplot(2, 2, 3)\nax3 = fig.add_subplot(2, 2, 4)\n\n\n\n\ndf_gdp_tal.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;#800000&#39;, ax=ax0)\nax0.set_title(&#39;Total GDP from 1980 - 2018&#39;)\nax0.set_xlabel(&#39;Year&#39;)\nax0.set_ylabel(&#39;GDP(current US$)&#39;)\n\ndf_gdp_tal2.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;#00CED1&#39;, ax=ax1)\nax1.set_title (&#39;GDP from United States, Japan and China from 1980-2018&#39;)\nax1.set_ylabel(&#39;GDP(current US$)&#39;)\nax1.set_xlabel(&#39;Year&#39;)\n\ndf_gdp_tal3.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;pink&#39;, ax=ax2)\nax2.set_title (&#39;GDP from India, Italy and Brazil from 1980-2018&#39;)\nax2.set_xlabel(&#39;Year&#39;)\nax2.set_ylabel(&#39;GDP(current US$)&#39;)\n\ndf_gdp_tal4.plot(kind=&#39;scatter&#39;, x=&#39;year&#39;, y=&#39;total&#39;, figsize=(20, 15), color=&#39;#90EE90&#39;, ax=ax3)\nax3.set_title (&#39;GDP from Australia, Spain and Mexico from 1980-2018&#39;)\nax3.set_xlabel(&#39;Year&#39;)\nax3.set_ylabel(&#39;GDP(current US$)&#39;)\n\nplt.show()&#34;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[406]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pylab</span> <span class="k">as</span> <span class="nn">plt</span>

<span class="sd">&#39;&#39;&#39;x = np.random.randint(low=1,high=5,size=50)</span>
<span class="sd">y = np.random.randint(low=0,high=2,size=50)</span>
<span class="sd">jittered_y = y + 0.1 * np.random.rand(len(y)) -0.08</span>
<span class="sd">jittered_x = x + 0.1 * np.random.rand(len(x)) -0.08&#39;&#39;&#39;</span>

<span class="n">fig</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">()</span>

<span class="n">ax0</span> <span class="o">=</span> <span class="n">fig</span><span class="o">.</span><span class="n">add_subplot</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="sd">&#39;&#39;&#39;ax1 = fig.add_subplot(2, 2, 2)</span>
<span class="sd">ax2 = fig.add_subplot(2, 2, 2)</span>
<span class="sd">ax3 = fig.add_subplot(2, 2, 2)&#39;&#39;&#39;</span>

<span class="n">df_gdp_tal</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;total&#39;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">25</span><span class="p">,</span> <span class="mi">20</span><span class="p">),</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;darkblue&#39;</span><span class="p">,</span><span class="n">alpha</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span> <span class="n">ax</span><span class="o">=</span><span class="n">ax0</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Total GDP from 1980 - 2018&#39;</span><span class="p">)</span>
<span class="n">ax0</span><span class="o">.</span><span class="n">set_xlabel</span><span class="p">(</span><span class="s1">&#39;Year&#39;</span><span class="p">)</span>
<span class="n">ax0</span><span class="o">.</span><span class="n">set_ylabel</span><span class="p">(</span><span class="s1">&#39;GDP(current US$)&#39;</span><span class="p">)</span>

<span class="n">df_gdp_tal2</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;total&#39;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">25</span><span class="p">,</span> <span class="mi">20</span><span class="p">),</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;#00CED1&#39;</span><span class="p">,</span><span class="n">alpha</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span> <span class="n">ax</span><span class="o">=</span><span class="n">ax0</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;GDP from United States, Japan and China&#39;</span><span class="p">)</span>

<span class="n">df_gdp_tal3</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;total&#39;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">25</span><span class="p">,</span> <span class="mi">20</span><span class="p">),</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;firebrick&#39;</span><span class="p">,</span><span class="n">alpha</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span><span class="n">ax</span><span class="o">=</span><span class="n">ax0</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;GDP from India, Italy and Brazil&#39;</span><span class="p">)</span>

<span class="n">df_gdp_tal4</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;year&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;total&#39;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">25</span><span class="p">,</span> <span class="mi">20</span><span class="p">),</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;darkgreen&#39;</span><span class="p">,</span><span class="n">alpha</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span> <span class="n">ax</span><span class="o">=</span><span class="n">ax0</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;GDP from Australia, Spain and Mexico&#39;</span><span class="p">)</span>
<span class="n">ax0</span><span class="o">.</span><span class="n">set_title</span> <span class="p">(</span><span class="s1">&#39;Comparism total gdp and Top rankings of countries&#39;</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">(</span><span class="n">loc</span><span class="o">=</span><span class="s1">&#39;upper left&#39;</span><span class="p">);</span>

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
<img src="data:image/png;base64,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jbvuuou33norFN779OnDJ598AkB2djaXX355lfWLjo6mefPmREVF4XK5ahTIRUREJDLV60kKjsbpjCUjowszZuSSn1+IwxFNRkYXnM4TP2187bXX8v7775OcnEzTpk156623aNasGfv27SM9PZ2pU6fSokULUlJSSEpKqrasxx9/nIceeoh+/frhcrlo2bIl3bp1Y//+/eTk5JCamkpJSUloTOqJmDx5MldccQVg90jGxR1bkH/hhRd466232Lt3Lz/++CN/+tOfeP3113nrrbdwOBxMnToVYww33XQTo0ePZv78+ZSUlDB79mxiY2O59957cbvdNGrUKDTm9mgmTZrErl27GD16NGDffaBnz56cccYZ9O/fn/POO49HHnkEgIceeogPP/wQy7L47rvvmDp1Ko8//jhDhw4lOjqaSy+9lB49ehzTcxYREZHIYWrS83aq9OjRw/r8889Djzdu3MjFF1981P0KCorw+QqJj487KcFVJNLU9LMiIiJSV4wxX1iWdcI9TBHd81rK6YxVaBURERFpACJ6zKuIiIiINCwKryIiIiISMRReRURERBqAE52RtL44Lca8ioiIiEjV8vJ2kZWVSyBQEro7U6dOLeu6WsdFPa9Bq1evZsCAAaSkpOB2u3nvvfcAGDt2LD179mTQoEGkpaXx5ZdfAuDxeEhISMDtdjNw4EB2795dprzs7Gy6du0auun+yTJnzhxeeeWV0OOJEyfi8Xiq3P43v/lNqL7HcvP+Pn36VFg2YcIELr/8cpKSknj88cdD9SkqqvobXG5uLp999lmNj1uVLVu2kJ6efsLl1JbRo0ezZcuWMssOHz7MPffcQ//+/enbty+PPfYYQKW38pozZw5r1649FVUVEZEGpjZnJK0Lp0XPa0HJEXwlJcRHR+OMPvY8vmfPHu666y6WLl1Kq1atCAQChN+ya/bs2SQmJvL9998zcuTIUFgcNWoU06ZNIzMzk1dffZVHH300tM+iRYt444036Nq1a2jZkSNHykwocCq8+uqrgB1ee/TowYUXXnhc5fzjH//g+++/Z/Xq1QDk5+cDduhKT0+vckrW3Nxc/H4/vXr1Oq7jRrKnn36aVq1aMX36dABWrFhR5bZjx449RbUSEZGG5ucZSZsA9oyk+fmF+HyFEXm3pojvec07eIjx27Yz6ccdjN+2nQ0HK067ejRLlixhxIgRtGrVCgCHw1HpxAPt2rVj2LBh/PWvfy2zPDExkR9++CH0OCcnhw8++IDbb7+dJUuWkJKSwvjx47niiisoLi5mzJgxuN1u0tLS2Lt3L1u2bCEpKYn09HQuueQSFi1axMiRI+ncuTMbN26s0XPweDwMHTqUq6++mssuu4wNGzYAdi/foUOHmDNnDg8//DC33HILlmVxzz33MGDAAAYPHhyq+zPPPENSUhJ33313aCaxUo0aNWLz5s18/fXXgD1969q1a8nNzeWKK67gpZdeYtmyZaSmptKrVy+mTJkCwMyZM3nppZdCEyc888wzuN1ukpOT2bBhA0VFRVx55ZWhZYcPHz7qc33++edJTU2le/fuLFu2DLDD3x133EFqaio333wzABs2bCA1NZW+ffty9913V9tOpXbu3MmgQYNITk4mPT2dkpIStmzZQt++fUlPT6dz584sX74csGdA69q1K+np6ezcubNCPd977z3Gjx8fejxgwADA/hJz55130rt379BsY0888QQffvhhlceq7DmLiIjURG3OSFoXIjq8FpQcIWv3HlxRUSTEOnBFRTFj9x4KSo4cUzk//vhjKLjm5OSQkpLC8OHDK922devWbN++vcyyVatWhaZMBUhNTWXo0KHMnj2bYcOGAZCWlkZ2djaLFy+mbdu2eL1eRo0aFeqVy8/PZ8GCBUyfPp3JkyezcOFCnn766RrPUgUQCAT44IMPmDZtGrNnzw4tb9y4MWPHjuXZZ59l9uzZLFmyhBYtWrBixQqmTJnClClT2LFjB9nZ2axZs4Z7772XPXv2lCn7ggsuYOLEidxxxx107NiR//3f/yUpKYkuXbrw8ccfc99993H55ZeTk5PDunXreP/99zl06BB33nkn9913Hx9//DEbNmzg66+/xuv18s477zBp0iS2bt1Ko0aN8Hq9eL3e0PSw1cnIyCAnJ4fs7GyeeeaZ0PJu3bqRk5NDXFwcHo+H9u3b8+mnn7JmzRq2b9/Ot99+W207gR3Kly5dysqVK2nbti05OTmA3Ts/f/583nvvPbKysgB7ZrBPP/2UefPm8f3331eoZ2FhYaUznPl8PiZOnMjatWuZP39+hfWVHauq5ywiInI0pTOS+v3FbN16AL+/+KTNSFoXInrYgK+khIBl4QoOFXBFR5FfUoKvpOSYhg+0bt06FGxSU1NJTU2tcorR7du3h8aDLliwgPXr19OuXTsefvjhao/Rs2dPADZv3hz6vXfv3qGetUsvvZTo6GjatGlDYmIiUVFRtGnTJnR6vlSjRo3KBMvDhw/TuHFjDh06RJcuXQBISEiosF+4f/7znyxevJiVK1diWRYJCQls2bKFzp07Y4zhwgsvpHnz5hX2u/7667n++uvZuXMngwcP5qqrriqz/quvvuLxxx8nEAjw3Xff8dNPP5VZv3HjRtasWUNKSgoA0dHRXHDBBbjdbsaOHUubNm146qmniI6OrrYt582bx5tvvklUVBQ7duwILe/evXvo382bN3P22Wfz4IMPcvDgQf7973+HvnRU10579+7ljjvuID8/nx9//JHLLruMDh06kJiYSExMTJl9SkpKOOOMMwC47LLLKtQzLi6u0gDbokUL2rVrB9hfLMqr7FhVPWcREZGa6NSpJZmZ7tNiRtKI7nmNj47GYQz+YE+rv+QIDmOIP0r4KS8tLY3FixeHwk35U+altm7dypIlS+jfvz9gj3n1er28+eabOJ3Oao9ROta1ffv2rF+/HoB169bRoUMHAIwxoW3Dfy8/fW9iYmJo2EJJSQlffPFFpWWU38/hcISe10UXXcT111+Px+PB6/Uye/ZszjvvPP7+979jWRabNm1i3759Zfbfu3dvKDTHx8fjcDgqlDtlyhRefvllVqxYQdu2bbEsq8Jx3W43Ho8Hj8fD0qVLKSwsJCMjgzlz5rBr1y5Wr17NoUOHKvT8hps2bRorVqxg4cKFZZZ/9dVXoX8vuOACsrKyuOeee/B6vfTo0SPUJtW107x58xgyZAher5crr7yy2n2io6PJz8+nqKiIvLy8CvVMT08nMzMz9Njr9VYoqzKVHauq5ywiIlJTTmcsbdo0jejgChHe8+qMjiLjrDOZsXsP+SUlOIwh46wzj/mirTPPPJNZs2YxZswYjDHExMRw//33h9bfcsstNG/eHIfDwaxZs2jatOlx1/maa65h0aJFJCcn43Q6mTdvHvv376/x/omJiXTp0oV+/fpx5MgRbrvttlDvX3VSU1P53e9+h9frJTMzk5ycnNAYzBtuuIFbb72VwYMHk5SURLdu3TjzzDPL7L9v3z5uvvlmLMuiuLiYiRMnAjB8+PBQj+y1117LqFGj6NSpUyjMJyUlcdNNN/H5558zd+5cOnTogNvtJioqisGDB5Oens6tt97KkSNHaNasGd26dWP16tV4vV6efvrp0PEtywr1yA4YMID+/fvTu3dvmjVrFtrms88+Y968ebRt25aUlBSKiop44IEHeP3116v8QlLewIEDufHGG8nOzsbpdNK5c+cqt33qqacYOHAg5513HgkJCRXWP/bYY0yYMIHk5GSOHDlCamoqbre7RvUor6rnLCIi0tCY8j1PdalHjx5W+FX+Gzdu5OKLLz7qfid6twGpX6ZNm8ZVV11VZhyx1+tl8eLF/OEPf6h0n7FjxzJhwgQSExNPVTXrlZp+VkREROqKMeYLy7IqH5d5DCK650FYff8AACAASURBVLWUMzpKofU0MmHChDKPly5dyqRJkypcXCUiIiINz2kRXuX0NnToUIYOHVrtNnPmzDk1lREREZE6pe5KEREREYkYCq8iIiIiEjEUXkVEREQkYii8Bq1evZoBAwaQkpKC2+3mvffeA+yr2Hv27MmgQYNIS0vjyy+/BOxpRhMSEnC73QwcOJDdu3eXKS87O5uuXbvywgsvnNR6ejyeChc0VWXWrFnMmTOHHTt28Pjjjx/3cf74xz9Wu23p1Ka14fDhw6FJDcI1bdqUlJQUevbseUJtvHTpUhYvXgxQ5cQUIiIiUn+cFuG1+OBBDu3YQfHBg8e1/549e7jrrrt4++238Xg8LF++nNatW4fWz549m+XLlzNz5kzGjRvHgQMHgJ8nKUhLS+PVV18tU+aiRYt44403ePDBB0PLjhw5tmlrT5ZzzjmHJ5988rj3P1p4rQsdO3bE4/Gwbt06Zs+eXeE+rjVt66FDhzJixIjaqKKIiIjUgogPr/v+9S/+8cwzfP2HP/CPZ55h39dfH3MZS5YsYcSIEbRq1QqwZ41KSkqqsF27du0YNmxYaIarUomJifzwww+hxzk5OXzwwQfcfvvtLFmyhJSUFMaPH88VV1xBcXExY8aMwe12k5aWxt69e9myZQtJSUmkp6dzySWXsGjRIkaOHEnnzp3ZuHFjlfXu1q0bd955J7179+bZZ58F4D//+Q/9+vUjLS2NlStXArBlyxbS09MBeP7550lNTaV79+4sW7bsqG2zePFivv76a1JSUliwYAFz585l4MCBdOvWjblz55bZ9sUXX+TPf/4zYN93dOzYsWXWV7bvE088wa9//WuuuOIKkpOTORj8ApKRkYHb7T5qj3FRUREOh4OoqCjmzJnDqFGjGDZsGMuXL2fChAmkpKTQq1cvcnNzKSkpISUlhZSUFC666CLGjx/PnDlzeOWVV47aDiIiIlI/RHR4LT54kC1vvUWM00njVq2IcTrZMnfuMffA/vjjj6HgmpOTQ0pKCsOHD69029atW4emkS21atWqMjfUT01NZejQocyePZthw4YB9hS02dnZLF68mLZt2+L1ehk1ahTTp08HID8/nwULFjB9+nQmT57MwoULefrppysExHA+n4+JEyeydu1a5s+fD8DUqVOZNGkSH330UaXTkGZkZJCTk0N2djbPPPPMUdtmxIgRoV7OUaNGce211/Lpp5+ydu1aXn755TLbjhkzhgULFgDw1ltvccMNN5RZX9W+HTt25OOPP6Z///4sX76czz//nPz8fLxeL4MGDaq0XqWB+uKLL2bYsGGh5xobG8uSJUsYMmQITz31FB6Ph9dee43nn3+e6OhoPB4P77//Pq1ateKBBx446vMXERGR+iWi7/Ma2L8fq7iYmCZNAIhp0oTAvn0E9u8PLauJ1q1b8+233wJ28ExNTa1y/OP27dvp06cPAAsWLGD9+vW0a9eOhx9+uNpj9OzZE4DNmzeHfu/duzfLly8H4NJLLyU6Opo2bdqQmJhIVFQUbdq0IT8/v8oyW7RoQbt27QBo3LgxAJs2baJ79+4A9OrVq8I+8+bN48033yQqKoodO3ZUW+fKLFu2LDTG9Jtvvimz7uyzzwbgp59+wuPxlJnetbp9u3btCkBCQgL5+fkcPHiw2ucAPw8bOHLkCCNGjOD7778Hfm5ngMzMTLKzs4mKigpNLVtSUsLNN9/Mc889x7nnnnvMz19ERETqVkT3vDqaNcPExIR6WosPHsTExOA4xrnf09LSWLx4cahHtfz4yVJbt25lyZIl9O/fH/h5zOubb76J0+ms9hhRUXZTt2/fnvXr1wOwbt06OnToAFCmlzT89+qm762sZ7V9+/Z89dVXAIRPtVtq2rRprFixgoULF4aWHThwgH379tXoOE8++SR/+ctfyM7OxuVyVdj2v/7rv7jvvvvo27dv6Dkfbd/yz/dozyFcVFQULpcLn88Xegz2OOYPP/yQVatW8corr4Ta8f7772f06NFVhmIRERGp3yK65zWmSRPOu/FGtsydS2DfPkxMDOfdeOMx9boCnHnmmcyaNYsxY8ZgjCEmJob7778/tP6WW26hefPmOBwOZs2aRdOmTY+7ztdccw2LFi0iOTkZp9PJvHnz2L9//3GXV95DDz3EmDFjmDZtGvHx8RXWDxgwgP79+9O7d2+aBUP+ggULMMZw6623VlrmgAEDGD58OOPGjePaa69lwIABdO3alRYtWlTY9uqrr+Y3v/kNXq+3wrqj7VuqR48eNGvWjOTkZHr37l3pNqXDBkpKSujUqROXXXZZKPCC3St99tlnM2DAAPr27QvYXz5mz57Nhg0bePXVV0lPT680gIuIiEj9Zarr2Tvhwo15ALgNsIANwC2WZR2uavsePXpY4T1tGzdu5OKLLz7qcYoPHiSwfz+OZs2OObiKHXgffvjhagNlTR0+fJihQ4fi8XhOvGJSYzX9rIiIiNQVY8wXlmWd8H0pa23YgDGmDXAv0MOyrEQgGhhdG8eKadKExueco+B6nKZOnXpSguu3337L4MGDuffee09CrUREREQqqu1hAzFAY2NMAGgCbD/K9hLBOnTowKpVq+q6GiIiIqetgoIifL5C4uPjcDpj67o6daLWwqtlWduMMdOA/wCHgE8sy/qk/HbGmNuB2wHatm1bW9URERERiWh5ebvIysolECjB4YgmI6MLnTq1rOtqnXK1OWygBXA1cD7QGnAaY24ov51lWX+0LKuHZVk9WrZseC+AiIiIyNEUFBSRlZWLyxVDQkJTXK4YZszIpaCgqK6rdsrV5q2yBgH/tixrl2VZAWAR0LcWjyciIiJyWvL5CgkESnC57KECLlcsgUAJPl9hHdfs1KvN8PofoI8xpomxb+Q5EKh6rtM6tnr1agYMGEBKSgput5v33nsPgLFjx9KzZ08GDRpEWloaX375JQAej4eEhATcbjcDBw5k9+7dZcrLzs6ma9euoZvyn0yWZXHuueeGpmI9Fn/84x+PafvSyRqmTJnCv//972Pa98UXX6RPnz5cfvnl3H777ce0b25uLjNnzjymfY7F0qVLeeKJJ8os83g8REVFhZ7njh07iImJ4cMPPzymsn/zm9+crGqKiIgAEB8fh8MRjd9v97T6/UU4HNHEx8fVcc1OvVoLr5ZlrQMWAl9i3yYrCji25FRDBYUFbMvfRkFhwXHtv2fPHu666y7efvttPB4Py5cvp3Xr1qH1s2fPZvny5cycOZNx48Zx4MAB4OdJCtLS0nj11VfLlLlo0SLeeOMNHnzwwdCyI0eOHFf9ylu9enVoYoVjVVl4tSyr2skQACZOnMj5559f4+McOHCABQsWsHbtWlavXs1zzz13TPXs0qULd9555zHtczJ079499MVl0aJFdOvW7ZjLKP9eEBGR+qegoIht2w5EzGl3pzOWjIwu+P3FbN16AL+/mIyMLg3yoq1anWHLsqzHLcu6yLKsRMuybrQs66T3bedtzWP8O+OZ9MEkxr8zng0/bDjmMpYsWcKIESNo1aoVAA6Hg6SkpArbtWvXjmHDhvHXv/61zPLExER++OGH0OOcnBw++OADbr/9dpYsWUJKSgrjx4/niiuuoLi4mDFjxuB2u0lLS2Pv3r1s2bKFpKQk0tPTueSSS1i0aBEjR46kc+fObNxYsbP63Xff5b777qOwsBC/3w/YPcR///vfATtoejwe1q5dS69evXC73UyaNInFixeHbu6/YMECxo4dy5133smgQYPYu3cvQ4YMISUlhcGDB1eYOKG0/J07dzJo0CCSk5NJT0+vcjayqKgo9uzZQ25uLpZlhW7FNXbsWO644w5SU1O5+eabAdiwYQOpqan07duXu+++G7B7QSdMmABAt27duPPOO+nduzfPPvtshWNNmDCBlJQUevXqRW5uLgApKSncf//9JCcnc9dddwHg8/kYMmQIQ4cO5d1336203v379w+9vsuXL2fQoEGhdc888wxut5vk5GQ2bNjAwYMH6devH7t37yY7O5tx48YBP/dWb9q0iYEDB+J2u/ntb38L2DOcJSUl0bdvX7744otK6yAiIrUrL28X48d7mTRpNePHe9mwYVddV6lGOnVqSWamm6eeupzMTHeDvFgLInx62ILCArI8WbgauUg4IwFXIxczVsw45h7YH3/8MRRcc3JySElJYfjw4ZVu27p169A0sqVWrVpFx44dQ49TU1MZOnQos2fPZtiwYYA9BW12djaLFy+mbdu2eL1eRo0axfTp0wHIz89nwYIFTJ8+ncmTJ7Nw4UKefvpp5s6dW+ZYlmXx9ddfc+mll3LNNdewZMmSKp/XRx99xKRJk/B6vTzxxBOMGDGCjh074vF4GDVqFGAHrU8//ZQzzzyTDz74AI/Hw1VXXcWCBQsqLbNFixYsXbqUlStX0rZtW3Jycirdzul0MnPmTB599FHat2/Pa6+9FlrXrVs3cnJyiIuLw+Px0L59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DRsQERGROhFpp9B1wVX9oJ5XERERqTORdAo9EnuLT0fqeRURERGpoUjrLT4dKbyKiIjICSkoKGpQYc7pjG0Qz7O+UngVERGR49bQJhqQuqcxryIiInJcInmiAYlcCq8iIiJyXHTrKKkLCq8iIiJyXCJxogGJfAqvIiIiclx06yipC7pgS0RERI6bbh0lp5rCq4iIiJwQ3TpKTiUNGxARERGRiKHwKiIiIiIRQ+FVRERERCKGwquIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiIhIxFB4FREREZGIofAqIiIiIhFD4VVEREREIobCq4iIiIhEDIVXEREREYkYCq8iIiIiEjEUXkVEREQkYii8ioiIiEjEUHgVERERkYih8CoiIiIiEUPhVUREREQihsKriIiIiEQMhVcRERERiRgKryIiIiISMRReRURERCRiKLyKiIiISMRQeBURERGRiKHwKiIiIiIRQ+FVRERERCKGwquIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiAgFBUVs23aAgoKiuq6KSLVi6roCIiIiUrfy8naRlZVLIFCCwxFNRkYXOnVqWdfVEqmUel5FREQasIKCIrKycnG5YkhIaIrLFcOMGbnqgZV6S+FVRESkAfP5CgkESnC5YgFwuWIJBErw+QrruGYilVN4FRERacDi4+NwOKLx++2eVr+/CIcjmvj4uDqumUjlFF5FREQaMKczloyMLvj9xWzdegC/v5iMjC44nbF1XTWRSumCLRERkQauU6eWZGa68fkKiY+PU3CVek3hVURERHA6YxVaJSJo2ICIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiNQjBQVFbNt2QDNciVRBdxsQERGpJ/LydpGVlUsgUILDEU1GRhc6dWpZ19USqVfU8yoiIlIPFBQUkZWVi8sVQ0JCU1yuGGbMyFUPrEg5Cq8iIiL1gM9XSCBQgstl32vV5YolECjB5yus45qJ1C8KryIiIvVAfHwcDkc0fr/d0+r3F+FwRBMfH1fHNROpXxReRURE6gGnM5aMjC74/cVs3XoAv7+YjIwumvVKpBxdsCUiIlJPdOrUksxMNz5fIfHxcQquIpVQeBUREalHnM5YhVaRamjYgIiIiIhEDIVXEREREYkYCq8iIiIiEjEUXkVEREQkYii8ioiIiEjEUHgVERERkYih8CoiIiIiEUPhVUREREQihsKriIiIiESMWg2vxph4Y8xCY8y/jDEbjTFJtXk8ERERETm91fb0sC8BSy3LSjfGxAJNavl4IiIiDVZBQRE+XyHx8XGaYlZOW7UWXo0xzYBkYCyAZVlFQFFtHU9ERKQhy8vbRVZWLoFACQ5HNBkZXejUqWVdV0vkpKvNYQO/BHYBs40xXxljXjPGOMtvZIy53RjzuTHm8127dtVidURERE5PBQVFZGXl4nLFkJDQFJcrhhkzcikoUJ+RnH5qM7zGAN2AmZZldQUKgInlN7Is64+WZfWwLKtHy5b6higiInKsfL5CAoESXC57qIDLFUsgUILPV1jHNRM5+WozvP4A/GBZ1rrg44XYYVZEREROovj4OByOaPx+u6fV7y/C4YgmPj6ujmsmcvLVWni1LGsHsNUY0zG4aCDwz9o6noiISEPldMaSkdEFv7+YrVsP4PcXk5HRRRdtyWmptu82cA8wL3inge+AW2r5eCIiIg1Sp04tycx0624Dctqr1fBqWVYu0KM2jyEiIiI2pzNWoVVOe5phS0REREQihsKriIiIiEQMhVcRERERiRgKryIiIiISMRReRURETrKCgiK2bTugGa5EakFt3ypLRESkQcnL20VWVi6BQAkORzQZGV3o1EkzSIqcLOp5FREROUkKCorIysrF5YohIaEpLlcMM2bkqgdW5CRSeBURETlJfL5CAoESXC77XqsuVyyBQAk+X2Ed10zk9KHwKiIicpLEx8fhcETj99s9rX5/EQ5HNPHxcXVcM5HTh8KriIjISeJ0xpKR0QW/v5itWw/g9xeTkdFFs16JnES6YEtEROQk6tSpJZmZbny+QuLj4xRcRU4yhVcREZGTzOmMVWgVqSUaNiAiIiIiEUPhVUREREQihsKriIiIiEQMhVcRERERiRgKryIiIiISMRReRURERCRiKLyKiIiISMRQeBURERGRiKHwKiIiIiIRQ+FVRERERCKGwquIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiIhIxFB4FREREZGIofAqIiIiIhFD4VVEREREIobCq4iIiIhEDIVXEREREYkYCq8iIiIiEjEUXkVEREQkYii8ioiIiEjEUHgVERERkYih8CoiIiIiEUPhVUREREQi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
"
>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>

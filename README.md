SaarLK
======

A jQuery plugin for a interactive maps of Saarland. Every Landkreis (district) can be highlited with a color, stroke etc. Based on an SVG from wikimedia.

## Usage

Once included into head:

````javascript
<script src="path/to/jquery-version.min.js"> </script>
<script src="path/to/jquery.saarlk.js"> </script>
````

put the function calls into the body (bottom) or in a _$(document.)ready()_ in the head of the page.

## Examples

````javascript 
$('div').SaarLK({'fill': '#22DD88'});
$('div.SaarLK.1').data('SaarLK').hov(['SLS', 'MZG']);
$('div.SaarLK.2').data('SaarLK').hov('HOM', {'fill': '#dd9933', stroke: '#dd4422', "stroke-width": 5});
$('section').SaarLK();
$('section.SaarLK.1').data('SaarLK').hov('SB');
$('#map').SaarLK();
$('#map').data('SaarLK').hov('NK');

````

[Online demo](http://jsfiddle.net/RobertKolatzek/dqJd6/embedded/result/)

## Documentation

````javascript
$(selector).SaarLK(options);
````

**SaarLK** - initialize given elements: Puts SVG into it and creates jQuery objects with options.

**options** - a string literal with css attributes for SVG (not HTML!) _fill_ **not** _background-color_, _stroke_ **not** _border-color_, _'stroke-line'_ **not** _border-width._. Colors as hex values, not names.

Defaut options are:

````css
fill: '#ffbb99',
stroke: '#646464',
"stroke-width": 1.5
````

On initialization every element from *selector* will get css class **SaarLK** and a number (sequence number of actual selection) as css class. 

````javascript
$(selector+'.SaarLK.'+el_seq_num).data('SaarLK').hov(landkreise, options);
````

**hov** - function to highlight given landkreise with given options on selected map.

To get the jQuery objects with settings, it is necessary, to use **.data('SaarLK')** between selector and hov.

**landkreise** - a string or array of strings with district part of car registration number. Uppercase.

**options** - svg style setting for this call only.

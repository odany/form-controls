# form-controls

Dette er et CSS/JS bibliotek for styling av checkboxer, radioknapper og inputfelter.
Samt for å formattere og begrense hvilke tegn som skal tillates i inputfelter.

Biblioteket bruker [jQuery](https://jquery.com/), Igor Escobars jQuery Mask Plugin [jQuery Mask Plugin](https://igorescobar.github.io/jQuery-Mask-Plugin/) og webshims polyfill [webshims polyfill](https://afarkas.github.io/webshim/demos/)

## Bruk
For å bruke biblioteket må filene:
* **form-controls.js**
* **form-controls.css**
* **jquery.mask.min.js**

Og mappen
* **js-webshim**

Legges inn i en mappe som heter **form-controls** på serveren.

For å kunne bruke det i digiforms må du deretter inkludere (Document settings > Includes):
* **form-controls/form-controls.js**
* **form-controls/form-controls.css**

JQuery må også være inkludert.

## Demo
[https://dev4.digiforms.no/digiforms/htmlViewer?documentName=form-controls-demo](https://dev4.digiforms.no/digiforms/htmlViewer?documentName=form-controls-demo)

## Checkboxer og radioknapper
* Klassene styler checkboxene/radioknappene sånn at de blir litt penere, og ser like ut i alle browsere
* De er har også en større "click area" som gjør det litt lettere å treffe de med musepekeren

### Checkboxer
* Groupboxen (div rundt fieldset) rundt må ha klassen **checkbox-container**
* div rundt checkbox og label må ha klassen **control-row**

#### Hvordan plassere klassene
![Figur som viser hvordan klassene for checkboxer skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-checkbox-new.png)

#### HTML
```html
<div id="id-5d6d17f0-02c4be20" class="checkbox-container">
	<fieldset>
		<legend id="id-5d6d17f0-02c4be20_legend" class="checkbox-container_legend">Checkboxer</legend>
		<div id="id-5d6d17f0-02c4be20_content" class="checkbox-container_content">
			<div id="id-5d6d425c-02c23a10" class="control-row">
				<div id="id-5d6d425c-02c23a10_control" class="label_control checked">
					<input type="hidden" name="85a33aad006a46376f7f49375f2cbfd3" value="">
					<input type="checkbox" id="id-5d6d425c-02c31cb0" name="85a33aad006a46376f7f49375f2cbfd3" value="yes">
				</div>
				<div id="id-5d6d425c-02c23a10_text" class="label_text">
					<label for="id-5d6d425c-02c31cb0">checkbox</label>
				</div>
			</div>
			<div id="id-5d6d05b0-02c23990" class="control-row checkbox"> ... </div>
			<div id="id-5d6d3721-02c23a10" class="control-row checkbox"> ... </div>
		</div>
	</fieldset>
</div>
```
![Figur som viser hvordan checkboxer blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-checkboxes.PNG)

### Radioknapper
* Groupboxen (div rundt fieldset) rundt må ha klassen **radio-container**
* div rundt radioknapp og label må ha klassen **control-row**

#### Hvordan plassere klassene
![Figur som viser hvordan klassene for radioknapper skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-radio-new.png)

#### HTML
``` html
<div id="id-5d6d5d94-02c4c360" class="radio-container">
	<fieldset>
	 <legend id="id-5d6d5d94-02c4c360_legend" class="radio-container_legend">Radioknapper</legend>
		<div id="id-5d6d5d94-02c4c360_content" class="radio-container_content">
			<div id="id-5d6d7320-02c23a10" class="control-row"> ... </div>
			<div id="id-5d6d6cf6-02c22b10" class="control-row">
				<div id="id-5d6d6cf6-02c22b10_control" class="label_control checked">
					<input type="radio" id="id-5d6d6cf6-02c321b0" name="05ec796a9303eae972e7cf170de72aeb" value="'first'">
				</div>
				<div id="id-5d6d6cf6-02c22b10_text" class="label_text">
					<label for="id-5d6d6cf6-02c321b0">radiobutton</label>
				</div>
			</div>
			<div id="id-5d6d7320-02c23a10" class="control-row radio"> ... </div>
		</div>
	</fieldset>
</div>
```
#### Screen shot
![Figur som viser hvordan radioknapper blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-radios.PNG)

## Inputfelter

### Dropdowns (select)
* Må ligge inne i en div med klassen: **select-container**. Pass på at det ikke ligger noen andre elementer inne i **select-container** enn selve dropdownen (+ tilhørende label og containeren rundt disse). Den må heller ikke ha noen margin eller padding.
* Bruk klassen **input-field** på selve input-feltet. Det gir en *grunnleggende styling* som gjør at den ser lik ut i forskjellige browsere.

#### Hvordan plassere klasser på en dropdown (select)
![Figur som viser hvordan klassene for inputfelter skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-select.svg)

#### HTML
``` html
<div id="id-5dfa6e11-08afa040" class="select-container">
	<div id="id-5df3910c-07042470">
		<div id="id-5df3910c-07042470_text" class="label_text">
			<label for="id-5df3910c-04ba77e0">Dropdown</label>
		</div>
		<div id="id-5df3910c-07042470_control" class="label_control">
			<select id="id-5df3910c-04ba77e0" class="input-field" name="85a33aad006a46376f7f49375f2cbfd3"></select>
		</div>
	</div>
</div>
```

#### Screen shot
![Figur som viser hvordan dropdowns blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-select.PNG)


### Input-elementer (input)
* Bruk klassen **input-field** for *grunnleggende styling* av inputfelter.
* Bruk forskjellige andre klasser (f.eks. **numeric-text**) og kombinasjoner av [klasser](#klasser), for å *styre formatteringen og hvilke tegn som skal tillates* (se [demo](https://dev4.digiforms.no/digiforms/htmlViewer?documentName=form-controls-demo))

#### Hvordan plassere klasser på en input
![Figur som viser hvordan klassene for inputfelter skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-input-plain.svg)

#### HTML
``` html
<input type="text" id="id-5d93ad80-02c0cc20" class="input-field" name="85a33aad006a46376f7f49375f2cbfd3" placeholder="Hvilke som helst tegn ..." value="">
```

#### Screen shot
![Figur som viser hvordan inputfelter blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-input-regular.PNG)

#### Hvordan plassere klasser for en input som kun aksepterer siffer.
![Figur som viser hvordan klassene for inputfelter som kun aksepterer visse tegn skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-input-numeric.svg)

#### HTML
``` html
<input type="text" id="id-5d972d02-02c0cfb0" class="input-field numeric-text" name="85a33aad006a46376f7f49375f2cbfd3" placeholder="kun siffer, ingen formattering" value="" inputmode="numeric" pattern="[0-9]*">
```

#### Screen shot
![Figur som viser hvordan inputfelter som kun aksepterer visse tegn blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-input-numeric.PNG)


#### Hvordan plassere klasser for en input med formattering, f.eks. organisasjonsnummer.
![Figur som viser hvordan klassene for inputfelter med formattering skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-input-formatted.svg)

#### HTML
``` html
<input type="text" id="id-5d982482-02c0cfb0" class="input-field numeric-text org-number-mask" name="85a33aad006a46376f7f49375f2cbfd3" placeholder="xxx xxx xxx" value="" inputmode="numeric" pattern="[0-9]*" maxlength="11">
```

#### Screen shot
![Figur som viser hvordan  med formattering blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-input-formatted.PNG)

#### Hvordan plassere klasser for en input som kun aksepterer siffer.
![Figur som viser hvordan klassene for inputfelter som kun aksepterer visse tegn skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-input-numeric.svg)

### Floating labels
* Bruk klassene **label-float** og **hidden** på containeren rundt label og input.
* Bruk klassen **input-field-alt** på input-elementet for å fjerne *default digiforms styling*.

#### Hvordan plassere klasser på en input
![Figur som viser hvordan klassene for inputfelter skal brukes](https://rawgit.com/MetafocusAS/form-controls/master/images/drawing-floating-labels.svg)

#### HTML
``` html
<div id="id-054e784f-02ba5590" class="label-float">
	<div id="id-054e784f-02ba5590_text" class="label_text">
		<label for="id-054e784f-02b8d6d0">Floating label</label>
	</div>
	<div id="id-054e784f-02ba5590_control" class="label_control">
		<input type="text" id="id-054e784f-02b8d6d0" class="input-field-alt" name="85a33aad006a46376f7f49375f2cbfd3" placeholder="Floating label" value="">
	</div>
</div>
```

#### Screen shot
![Figur som viser hvordan inputfelter med floating labels blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-floating-labels.PNG)
![Figur som viser hvordan inputfelter med floating labels blir seendes ut](https://rawgit.com/MetafocusAS/form-controls/master/images/screenshot-floating-labels2.PNG)

## Klasser
* **account-mask** - gir et inputfelt formatet XXXX XX XXXXX, f.eks. 1234 56 78901
* **checkbox** - brukes i kombinasjon med **control** for å style checkboxer. Må ligge i en groupbox som har klassen **control-container**
* **control** - brukes for å style checkboxer og radio-knapper
* **control-container** - brukes på groupbox for å style checkboxer og radio-knapper inne i groupboxen
* **date-mask** - gir et inputfelt formatet DD.MM.YYYY, f.eks. 01.03.2018
* **input-field** - brukes for å style inputfelter og dropdowns (input og select)
* **letteral-text** - gjør at det kun er mulig å skrive inn tekst i inputfeltet
* **numeric-decimal** - gjør at det kun er mulig å skrive tall i inputfeltet, desimaler er tillatt. Type må være satt til "number"
* **numeric-positive** - gjør at det kun går å skrive inn positive tall i input-feltet. Type må være satt til "number".
* **numeric-text** - gjør at det kun går å skrive inn tall i input-feltet, og at numerisk keypad vises på iOS mobile
* **org-number-mask** - gir et inputfelt formatet XXX XXX XXX, f.eks. 123 456 789
* **percentage** - setter max="100" og min="0" for inputfeltet. Type må være satt til "number"
* **phone** - gir et format som passer for alle generelle telefonnummer med landkode. F.eks. +47 123 45 678
* **prevent-select-on-tab** - hindrer at data i input-feltet markeres ved tab inn i feltet. Funker ikke i firefox.
* **radio** - brukes i kombinasjon med **control** for å style radioknapper. Må ligge i en groupbox som har klassen **control-container**
* **vps-account-mask** - gir et inputfelt formatet XXXXX XXXXXXX, f.eks. 12345 6789012

## Tilpasse CSS
### Endre farge på border på element som har fokus
Endre farge på border-color her (checkboxer/radioknapper):
```css
.focused {
	border-color: #f35b1c !important;
}
```

Og her (inputfelter/dropdowns):
```css
.input-field:focus {
	padding: 11px !important;
	border: 2px solid #f35b1c !important;
}
```

### Endre farge checkboxer/radioknapper som er "checked"
Endre farge på border-color og background-color her:
```css
.control .label_text.checked label::before {
	border-color: #257886 !important;
	background-color: #257886 !important;
}
```

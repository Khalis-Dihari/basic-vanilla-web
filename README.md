# Basic Web Using Vanilla

## what inside

this project meant purely for learning purposes. this is where I start to make a website.  
In this readme is a journey how I manage creativity idea for this website, since I have no idea what web is this gonna be. Tho if I have no idea, I just writedown journey of my learning.
So in this section the pre-requisite only basic of HTML, if you want to learn from my journal make sure you have the basic for HTML. Because this journal start form CSS basic.

## Basic Vanilla Learning journey
---
<strong>The First Step</strong>
First step of learning. based on module in codepolitan kelas fullstack.  
in this step the main accomplishment is to learn CSS and HTML basic, also some of the GIT usage.

<details>
<summary><strong>30 June 2026</strong></summary>

## Aplying my GIT knowledge

First thing that I learned to using git. The thing that I learned:

- After I create branch `css-basic` I can push directly to main.  
  So after acknowledge that I can push from branch directly to main, I need more CAREFUL for push the progress that I made in branch

- Some commit rule from https://www.conventionalcommits.org  
  before this I am using `fix(README.md): bla.. bla..` for changing inside of the content of the readme and or even `fix(CSS)`. The format should be `chore(README.md)`.

Example of using commit format:

```bash
feat(queue): tambah QR scanner untuk user
fix(timer): countdown tidak berhenti saat status selesai
refactor(firebase): pindahkan query ke repository
docs: update struktur database Firebase
test(login): tambah test validasi email
perf(image): kurangi ukuran upload QR code
build: update dependency ZXing
ci: tambah workflow build Android
```

<br>

---
## Learning Basic CSS


About 2 years ago actually I have learn about HTML and CSS basic. Althogh I haven't applied it yet so I think I am gonna re-learn from zero.

Here some stuff that I learn:

- Three way for using CSS

  1. Inline Style  
     set CSS attribute directly in tag property

  2. style element  
     creating style tag on the head tag

  3. External stylesheet  
     adding new `style.css` file outside html file, so it can be used by another html page by using link tag

- CSS rules

```css
selector {
    property: value;
}
```

note that every CSS property using by semi colon `;` as separator for each property

**Jangan lupa titik koma**  
dont forget semi colon

- Font

user agent stylesheet sample (default style) for `h1` on chrome

```css
h1 {
    display: block; /*make h1 as block level for html*/
    font-size: 2em; /*Relative size 'em': for responsive page*/
    margin-block-start: 0.67em;
    margin-block-end: 0.67em;
    margin-inline-start: 0px; /*absolute size using px*/
    margin-inline-end: 0px;
    font-weight: bold;
    unicode-bidi: isolate;
}
```

<br>

---

## Review about HTML

after progressing about 1 hour on learning CSS, I forgot how to use HTML properly

here some stuff I reviewed:

1. type of HTML element

   - block level  
     taking every space in the line of the tag. you can wrap the content as `<div>`

   - inline element  
     only the content of tag, so it can placed in parallel of the paragraph. you can wrap the content using `<span>`

</details>

---

<strong>Selector and The Boxes</strong>
In this section will be covering some of the modules

- Selector And how it works
- Box Model CSS

<details>
<summary><strong>02 July 2026</strong></summary>

<details style="margin-left: 20px;">
<summary><strong>Selector And how it works</strong></summary>

the selector used to "select" wich one tag that going to be used as CSS property

1. <strong>for universal and grouped tag selector can be used as:</strong>

   - Universal Selector

```css
* { /* this selector are the universal selector in CSS */
    property : value;
}
```

- Grouped Tag Selector

```css
h1, h2, h3 { /*this selector can be used for gouping selector*/
    property: value;
}
```

2. <strong>ID attribute</strong>
ID from html must be unique, it means one tag one ID.<br>
example in html:

```html
<h1> This is first h1 </h1>
<h1 id="secondHeader"> The Second h1 that have ID <h1>
```
it can be used for css

```css
#secondHeader { /*this is selector based from ID using " # "*/
    property: attribute
}
```
based on that the CSS only give attribute to the second h1

3.  <strong>Class Attribute</strong>
Because ID should be unique from one tag to another. When you try to use the same CSS property to another specific tag, you can use class.
Example for html:

```html
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem odio necessitatibus distinctio <span class="mark2">nisi sint perferendis illo architecto magnam,</span> exercitationem modi, <span class="mark1">esse perspiciatis id minima corrupti provident reiciendis,</span> inventore incidunt vero?</p>
<p>Lorem ipsum dolor <span class="mark1">sit amet consectetur adipisicing elit. Voluptatem odio necessitatibus</span> distinctio nisi sint perferendis illo architecto magnam, exercitationem modi, esse perspiciatis id minima corrupti provident reiciendis, <span class="mark2">inventore incidunt vero?</span></p>
```
in the `<p>` i have some words that i want to mark by `<span>` for two color different color mark
in CSS you can use:

```css
.mark1 { /*for using selecting class using " . "*/
    background-color: yellow;
}
.mark2{ /*different span taht using another  selector for class*/
    background-color: lightgreen;
}
```
so it mark everyy tag based on it's CSS property

4.  <strong>Descendent Selector</strong>
-   <strong>Descendant</strong>
Descendant in CSS where you  are changing CSS property based on html structure you have. It can be tag inside a tag or using id or class.
example:

```css
div h2 { 
    color: blue;
}
```
then you have html with two h2 like this

```html
<h2> this h2 outside div <h2>
<div>
    <h2>this h2 inside div</h2>
</div>
```
the selector from css only changes for h2 inside div based on descendent selector.
-   <strong>Direct Descendent</strong>
there is a case when you have more html structure, here some example:
```html
<h1>header 1</h1>

<div>
    <h1> h1 inside div</h1> <!-- Only this will changes -->
    <div> 
        <h1>header 1 inside div, that inside div</h1>
    </div>
    <h1> h1 inside div, below another div inside same div</h1> <!-- also this will changes -->
</div>
```
in case you want to specific to change of property h1 inside dif you can use direct descendant

```css
div > h1 {
    color: blue;
}
```
it will only changes for only h1 directly inside div, so the h1 inside the div, that inside div again, will not changes.

-   <strong>Attribute Selector</strong>
attribute selector is where you want to select tag that have specific attribute that it have example in html you have:

```html
<input type="text" placeholder="Input text">
    <input type="password" placeholder="Input password">
```
than you want to only changes for input that have attribute `type`

```css
input[type="text"]
```
it only changes the input that have attribut `type="text"`

there is another attribute selector documentation you can check on [AttributeSelector] (https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Attribute_selectors)

-   <strong>Pseudo Classes</strong>
pseudo classes is a keyword to a selector where it specified for special state for example I am using pseudo class `:hover` for:

```html
<button>Tombol</button>
```
in css i can use special state to change css property:

```css
button:hover{
    background-color: blue;
}
```
or if i have html with many header

```html
<h1>First</h1>
<h1>Second</h1>
<h1>Third</h1>
<h1>Fourth</h1>
<h1>Fifth</h1>
```
you can use pseudo class selector for every h1 on the order multiply of 2

```css
h1:nth-last-child(2){
    color: gray;
}
```

-   <strong>Pseudo Elements</strong>
A CSS pseudo-element is a keyword added to a selector that allows you to style a specific part of an HTML element. 
example you have many `h3`

```html
<h1>First</h1>
<h1>Second</h1>
<h1>Third</h1>
<h1>Fourth</h1>
<h1>Fifth</h1>
```
you want to change the first letter of each h3 to bold

```css
h3::first-letter{
    font-weight: Bold;
}
```
the result will be
<strong>F</strong>irst
<strong>S</strong>econd
<strong>T</strong>hird
<strong>F</strong>ourth
<strong>F</strong>ifth

there are many more CSS selector type, you can see the documentation on [CSS-SelectorDocumentation] (https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Selectors)

</details>

<details style="margin-left: 20px;">
<summary><strong>Box Model CSS</strong></summary>



</details>

</details>
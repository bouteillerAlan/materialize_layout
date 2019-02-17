# materialize_layout
>**it's a WIP**

Twig layout for materialize framework.

## HTML input

### @form
`<form>` is contained in a `<div class="row">`

### @row
Any line in form is contained in a `<div class="input-field">`

### @input field

#### icon prefix
Icon prefix is available via `form_row(form.input, {'prefix': 'value'})`

`value` is equal to a name of a [_Material Design Icons_](https://materializecss.com/icons.html)

#### Custom error, success, help message
Icon prefix is available via `form_row(form.input, {'type': 'value'})`

* `type` is 'help_error', 'help_success' or 'help'
* `value` is a simple string

This element makes a `<span class="helper-text">` with a `data-error`, `data-success` and _helper text_ in function of your choice.

Example : 
`form_row(form.input, {'help_error': 'error message', 'help': 'help message'})` make `<span class="helper-text" data-error="error message">help message</span>`

#### placeholder

The _placeholder_ is available via `form_row(form.input, {'attr': {'placeholder': 'message'}})`

### @textarea
#### icon prefix
Icon prefix is available via `form_row(form.input, {'prefix': 'value'})`

`value` is equal to a name of a [_Material Design Icons_](https://materializecss.com/icons.html)

#### ckeditor 4 (or something else)
if you use this just add `'label' : false` for a good ui

### @file input
The text in the button is defined by the label

If you use `{'type': 'file'}` the content of your row is replace by the right code

## materialize components
### @character counter
[If you need to activate them](https://materializecss.com/text-inputs.html)

Actually it's equal to `attr.maxlength` 

Example : 

in my validator i have : 
```twig
-length:
    max: 50 
    min: 4
```
the character counter is up to max = 50
### @range input
Actually the min and max value is given via `'attr': {'type': 'value'}`, in the future I would want to make it automatically via the _validator_

The label row is generated with a class and the range too (if you need to ajust them) :
```html
<div class="range_label">
    _label_
</div>
<div class="range_content">
    _range_
</div>
```
## TODO
* switches
* radio
* select
* date/time pickers
* Autocomplete
* buttons
* chips?

## Need to update?
[Just push your's code like this](https://chris.beams.io/posts/git-commit/)
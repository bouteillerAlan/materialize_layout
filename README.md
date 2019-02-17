# materialize_layout
>**It's a WIP, *John Doe***

Twig layout for [materialize framework](https://materializecss.com/) based on a [form_div_layout.html.twig](https://github.com/symfony/symfony/blob/master/src/Symfony/Bridge/Twig/Resources/views/Form/form_div_layout.html.twig) of [symfony](https://symfony.com/).

## Structure

### @form
`<form>` is contained in a `<div class="row">`

### @row
Any line in form is contained in a `<div class="input-field">`

## HTML input

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
### @autocomplete
[If you need to activate them](https://materializecss.com/autocomplete.html)

Autocomplete is available via `form_row(form.input, {'autocomplete': 'true'})`

## TODO
* switches
* radio
* select
* date/time pickers
* buttons
* chips?

## Need to update?
Thanks for taking the time to contribute.
* Fork and clone
```
# Clone your fork of the repo into the current directory
git clone https://github.com/<your-username>/materialize_layout.git
# Navigate to the newly cloned directory
cd materialize_layout
# Assign the original repo to a remote
git remote add trackedStream https://github.com/bouteillerAlan/materialize_layout.git
```
* Checkout 
```
git checkout master
git pull trackedStream master
```
* Create a new topic branch
```
git checkout -b <branch>
```
* Code, coffee, commit

[a good commit](https://chris.beams.io/posts/git-commit/)

[a good coffee](https://coffeeordie.com/good-coffee-bad-places-evan-hafer/)

[a good code](https://idratherbewriting.com/images/rtfmtractor.jpg)
* Merge/Rebase the trackedStream dev branch in the topic branch
```
git pull [--rebase] trackedStream master
```
* Push
```
git push origin <branch>
```
* Open a pull request with a clear title and description

[Like this](https://help.github.com/articles/about-pull-requests/)
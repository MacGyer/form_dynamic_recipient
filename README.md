# Form Dynamic Recipient for EXT:form / TYPO3 10.4 - 11.5

This extension adds simple database records, that can be used to generate a select field in the frontend.
The selected option can be accessed with an assigned alias and thus be used as a dynamic recipient, e.g. in the _Recipient address_ field.

## Installation
Clone to typo3conf/ext/form_dynamic_recipient
```
git clone https://github.com/extrameile/form_dynamic_recipient.git
```

or install via composer
```
composer require extrameile/form-dynamic-recipient
```

## Configuration

* Create database records with a label and target email address
* add a select field of type _Selectable recipient_ to the form, configure the page to load the values from and the variable to fill with the selected value, e.g. `dynamicRecipient`
* Configure the _Email to receiver_ finisher with `{dynamicRecipient.email}` and `{dynamicRecipient.label}` - set the form field to required, if you use {dynamicRecipient.email} as the target email address.

# Running phpstan

## 10.4
```
composer update --prefer-lowest -W
composer run phpstan
```

## 11.5
```
composer update -W
composer run phpstan
```

## ToDos

* validate submitted option to contain a uid from the records of the configured storage page


## Resources
* https://daniel-siepmann.de/Posts/2017/2017-09-07-typo3-form-select-with-db-values.html
* https://github.com/tritum/form_element_linked_checkbox



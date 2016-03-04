# meg-simpletable

> Simple JQuery plugin to generate tables of data capture

## Dependencies

* JQuery
* Bootstrap 3.x

## Soported input types

* text
* date
* time
* email
* tel
* number 

## Setting the plugin

```js
defaultPluginOptions = {	
  // Array of column options
  columns: [],

  // Mode visualize table [edit|show]
  mode: 'edit',

  //Data to load by default  
  data: [],

  // Text showed in add button
  btAddText: 'Add row',

  // Icon displayed in button remove row (FontAwesome icon)
  btRemoveIcon: 'fa fa-trash-o',

  // Icon displayed in button add row (FontAwesome icon)
  btAddIcon: 'fa fa-plus',

  // Class to add in add button
  btAddClass: 'btn btn-success',

  // Class to add in table
  tableClasses: 'table table-responsive',

  // Text showed in first empty option
  textEmptyOptionCombo: '[No elements]',

  // If true all fields in the row must be completed
  fillAllRow: false
}
$('#divMyTable').MEGSimpleTable(defaultPluginOptions)
```

## Usage


### Html

```html
<div id="divMyTable"></div>
```

### Javascript

**Example mode 'edit'**
```js
options = {
  fillAllRow: true,
  data:[],
  columns: [
    {
      name: 'name',
      display: 'Name',
      type: 'text',
	  placeholder:'Name and last name'
    }, {
      name: 'addres',
      display: 'Address',
      type: 'text'
    }, {
      name: 'age',
      display: 'Age',
      type: 'number'
    }, {
      name: 'email',
      display: 'Email',
      type: 'email'
    }, {
      name: 'sex',
      display: 'Sex',
      type: 'select',
      keyId: 'id',
      keyText: 'text',
      options: [
        {
          id: 'm',
          text: 'Male'
        }, {
          id: 'f',
          text: 'Female'
        }
      ]
    }
  ]
};

$('#divMyTable').MEGSimpleTable(options);
```

The result table would look like:

<img src="https://raw.github.com/jonathanferreyra/meg-simpletable/master/example_mode_edit.png" />

**Example mode 'show' with data loaded**

```js
options = {
  fillAllRow: true,
  mode: 'show',
  data: [
    {
      "name": "John",
      "addres": "Murray",
      "age": "35",
      "sex": "f"
    }, {
      "name": "Julia",
      "addres": "Stevens",
      "age": "28",
      "sex": "m"
    }
  ]
  columns: [
    {
      name: 'name',
      display: 'Name',
      type: 'text',
      placeholder: 'Name and last name'
    }, {
      name: 'addres',
      display: 'Address',
      type: 'text'
    }, {
      name: 'age',
      display: 'Age',
      type: 'number'
    }, {
      name: 'sex',
      display: 'Sex',
      type: 'select',
      keyId: 'id',
      keyText: 'text',
      options: [
        {
          id: 'm',
          text: 'Male'
        }, {
          id: 'f',
          text: 'Female'
        }
      ]
    }
  ]
};

$('#divMyTable').MEGSimpleTable(options);
```

The result table would look like

<img src="https://raw.github.com/jonathanferreyra/meg-simpletable/master/example_mode_show.png" />
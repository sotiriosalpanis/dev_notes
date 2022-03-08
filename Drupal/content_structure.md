# Setting up content structure

## Adding a content type

1. *Structure > Content types* and click *Add content type*
2. fill in *Name* and *Descrption*
3. *Submission form settings* configure the form that is used for creating/editing content of this type

## Deleting a content type

1. *Structure > Content types*
2. Click *Delete* in the dropdown for the content type you'd like to delete

## Adding basic fields to a content type

1. *Structure > Content types* click *Manage fields* in select content type
2. click *Add field* and either create new field type or use an existing one
3. Update the form
4. Rinse and repeat for each field

## Reference fields

- represents a relationship between an entity and one or more other entities
- three most commonly-used reference fields are:
  1. Content reference e.g. group together - 'submitted by'
  2. Taxonomy reference e.g. connect recipes to their ingredients
  3. User reference e.g. recipes to their chefs

## Taxonomy

- used to classify website content e.g. classify posts in a blog website
- individual items = 'term' and a group of terms is a 'vocabulary'
- can be flat or hierarchical
- users can enter terms in two ways:
  1. **Free tagging**
  2. **Fixed list of items**

### Setting up  a taxonomy

1. *Structure > Taxonomy* click *Add vocabulary*

2. add some terms

3. Go to Content Types, click *Manage fields* and then *Add field*

4. Select 'Taxonomy term' and then fill out details

## Adding a reference field

1. *Structure > Content types* Click *Manage fields* for a content type
2. *Add field* and choose *Reference > Content* type
3. Add details

## Forms and widgets

- content on Drupal site is edited through forms
- when creating a form, each field can have one or more widgets assigned to it.
  - example widget might be autocomplete, or a select list

### Changing content entry forms

1. *Structure > Content Types* click 'Manage form display' on dropdown.
2. Update the widget type for each field e.g. 'Autocomplete (tags style)'

## View Modes and Formatters

- a view is how an entity (i.e. content) is displayed, the view mode is contextual
- a field formatter is setting for displaying the field values

## Changing content display

1. some content doesn't require it's label (e.g. a profile image) *Structure > Content types* click *Manage display* in dropdown and select 'hidden' in the *Label* column
2. the wheel icon offers further customisation e.g. open a URL in a new window

## Image Styles

- allows the same image to be displayed in different ways
- *Configuration > Media > Image styles* to see default image styles

### Setting up an image style

1. *Configuration > Media > Image styles* click *Add image style*
2. Give the effect a name e.g. 'Extra medium (300x200)'
3. configure image effect by adding steps. Click 'Save'
4. *Structure > Content Types* select *Manage display* from dropdown
5. wheel icon for an image field to select the image style. Click *Update* and then *Save*

## Configuring Text Formats and Editors

1. *Configuration > Content authoring > Text formats and editors*
2. Configure a text format:
  i. *CKEditor* allows the editor's toolbar to be configured
  ii. change the *Filter* processing order
  iii. *Limit allowed html tags* allows control over what an editor can add

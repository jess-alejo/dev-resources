### HTML Forms

The `name` attributes of an input element is used to submit data.

```html
<form>
  <input type="text" name="username" />
</form>
```

<br>

Use `fieldset` to group related input elements

```html
<form>
  <fieldset>
    <legend>Address</legend>
    <input type="text" name="address1"/>
    <input type="text" name="address2"/>
    <input type="text" name="city"/>
    <input type="text" name="state"/>
  </fielset>
</form>
```

<br>

Do not use `hidden` fields to hide sensitive information.

```html
<input type="hidden" name="user_id" value="1" />
```

<br>

We can filter files in the `file` input tag.

```html
<!-- select only jpg images' -->
<input type="file" accept=".jpg" placeholder="select an image" />

<!-- select audo files -->
<input type="file" accept="audio/*" />
```

<br>

Use `datalist` to provide a lookup for an input field

```html
<input type="text" id="pet" list="pets" />
<datalist id="pets">
  <option value="cat" />
  <option value="dog" />
  <option value="bird" />
</datalist>
```

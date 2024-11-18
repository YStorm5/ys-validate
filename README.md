# ys-validate

A simple JavaScript validation library for form inputs.

## Validation Rules

Add these classes to your input fields:

- `val-empty`: Input cannot be empty.
- `val-number`: Input must be a number.
- `val-string`: Input must be a string.
- `val-length-*`: Input length must be greater than `*` (replace `*` with a number).
- `val-email`: Input must be a valid email address.
- `val-pattern`: Input must match a custom regex pattern.

### Example

```html
<input class="val-empty" placeholder="Cannot be empty" />
<input class="val-number" placeholder="Must be a number" />
<input class="val-email" placeholder="Must be a valid email" />
```

## How to Use

1. Create an instance of the `Validator` class.
2. Call the `validate()` method. It returns `true` if all validations pass, otherwise `false`.

### Example

```javascript
const validator = new Validator();

function onSubmit() {
  if (validator.validate()) {
    console.log("Validation passed");
  } else {
    console.log("Validation failed");
  }
}
```

## Notes

- Use `val-length-*` by replacing `*` with the required length (e.g., `val-length-5`).
- For `val-pattern`, define your regex in a custom data attribute, e.g., `data-pattern="^[A-Za-z]+$"`, for custom validations.
- To set custom validation error messages, pass an error object to the `Validator` class:

```javascript
const validator = new Validator({
  empty: "Please fill out this field",
  email: "Invalid email format",
});
```

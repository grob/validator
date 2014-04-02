validator
=========

A validator for RingoJS

## Example

In a Web application you can use the validator to validate the submitted data:

```javascript
var validator = new Validator(req.postParams);
validator.validate("username")
   .isDefined("Username is missing!")
   .minLength(3, "Username is too short!"),
   .maxLength(255, "Username is too long!");

validator.validate("email")
   .isDefined("Email address is missing!")
   .isEmail("Invalid email address!");

if (validator.hasErrors()) {
   // Display errors
   return respone.html(
      validator.errorMessages().join("<br>")
   );
}
```


![Codeship Status](https://www.codeship.io/projects/b77d7cf0-9c82-0131-4c86-5af6bd151f39/status)

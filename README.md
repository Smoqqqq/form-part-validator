# FORM PART VALIDATOR

The validator allows you to specify easily what each input should contain to be valid
you can then watch for errors :

```javascript
import Validator from "./validator.js";

const validator = new Validator();
validator.watch(document.querySelectorAll("input"));
```

you simply add a keyword to it's `data-form-constraints` attribute, separated by spaces :

```html
<input type="text" name="foo" data-form-constraints="length:0:38 nodot nowhitespace nonumber">
```

this will, when using the `watch` function, produce an error badge when the input doesn't match it's constraints

# CONSTRAINTS

| name              | function                                              | usage                     |
|-------------------|-------------------------------------------------------|---------------------------|
| length            | assert length between min and max                     | length:min:max            |
| minLength         | assert minimum length                                 | minLength:min             |
| maxLength         | assert maximum length                                 | maxLength:max             |
| text              | assert value contains some text                       | text                      |
| uppercase         | assert value is uppercase                             | uppercase                 |
| lowercase         | assert value is lowercase                             | lowercase                 |
| number            | assert value is numbers                               | number                    |
| nodot             | assert value has not dots                             | nodot                     |
| nowhitespace      | assert value whitspace                                | nowhitespace              |
| nonumber          | assert value contains no numbers                      | nonumber                  |
| email             | assert value looks like an email                      | email                     |
| dateInPast        | assert the date is x years:months:days in the past    | dateInPast:year:month:day |
| dateInFuture      | assert the date is x years:months:days in the future  | dateInPast:year:month:day |

## MUST HAVE
the `name` attribute is necessary for error messages to work properly
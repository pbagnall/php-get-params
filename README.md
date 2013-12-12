php-get-params
==============

GET/POST/REQUEST/COOKIE parameter validation functions for PHP. These are designed primarily to ensure only safe
values are seen by the rest of the code.

Calls take the form...

    getGetValue('paramName', 'validatorFunction', ...);

A real example would be...

    getPostValue('number', 'Integer', 100, 200, 100);

In this case validation is passed to a function called validateInteger, and it is passed 4 parameters. The raw input
from the $_POST array, and the remaining three parameters to the getPostValue call. These are the min acceptable
value, the max acceptable value and a default in case the provided parameter is invalid or does not exist.

The validation functions are...

    Integer($param, $min, $max, $default)
    Enumeration($param, $arrayOfAllowedValues, $default)
    Array($param, $validatorForArrayElements, $defaultArray, $subValidatorParams, ...)

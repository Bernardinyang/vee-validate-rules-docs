# Validation Rules Documentation

Welcome to the Validation Rules Documentation! This guide provides detailed information on various validation rules, including their titles, descriptions, and examples of how to use them in your schema.

## Table of Contents
1. [confirmed](#confirmed)
2. [accepted](#accepted)
3. [strong_password](#strong_password)
4. [nigerian_number](#nigerian_number)
5. [boolean](#boolean)
6. [date](#date)
7. [after](#after)
8. [after_or_equal](#after_or_equal)
9. [date_equals](#date_equals)
10. [date_format](#date_format)
11. [before](#before)
12. [before_or_equal](#before_or_equal)
13. [digits](#digits)
14. [state_exists](#state_exists)
15. [city_exists](#city_exists)
16. [string](#string)
17. [active_url](#active_url)
18. [array](#array)
19. [ascii](#ascii)
20. [contains](#contains)
21. [decimal](#decimal)
22. [declined](#declined)
23. [declined_if](#declined_if)
24. [different](#different)
25. [digits_between](#digits_between)
26. [email](#email)
27. [exists](#exists)
28. [file](#file)
29. [filled](#filled)
30. [greater_than](#greater_than)
31. [greater_than_or_equal](#greater_than_or_equal)
32. [in](#in)
33. [integer](#integer)
34. [ip](#ip)
35. [json](#json)
36. [less_than](#less_than)
37. [less_than_or_equal](#less_than_or_equal)
38. [max](#max)
39. [mimes](#mimes)
40. [min](#min)
41. [numeric](#numeric)
42. [present](#present)
43. [prohibited](#prohibited)
44. [required_if](#required_if)
45. [required_unless](#required_unless)
46. [required_with](#required_with)
47. [required_with_all](#required_with_all)
48. [required_without](#required_without)
49. [required_without_all](#required_without_all)
50. [same](#same)
51. [size](#size)
52. [starts_with](#starts_with)
53. [uuid](#uuid)
54. [uppercase](#uppercase)
55. [url](#url)
56. [timezone](#timezone)
57. [file_size](#file_size)

## Rules

### 1. `confirmed`

**Description**: Checks if the value matches the target confirmation field.

**Rule**: `confirmed:target_field`

**Validation Schema**:

```javascript
const schema = {
    password: 'required|confirmed:password_confirmation'
};
```

---

### 2. `accepted`

**Description**: Validates that the value is `true`, usually for checkboxes or acceptance fields.

**Rule**: `accepted`

**Validation Schema**:

```javascript
const schema = {
    terms: 'accepted'
};
```

---

### 3. `strong_password`

**Description**: Ensures the password is at least 8 characters long and includes uppercase, lowercase, a number, and a special character.

**Rule**: `strong_password`

**Validation Schema**:

```javascript
const schema = {
    password: 'required|strong_password'
};
```

---

### 4. `nigerian_number`

**Description**: Validates Nigerian phone numbers starting with +234 followed by 10 digits.

**Rule**: `nigerian_number`

**Validation Schema**:

```javascript
const schema = {
    phone: 'required|nigerian_number'
};
```

---

### 5. `boolean`

**Description**: Ensures the value is of boolean type (`true` or `false`).

**Rule**: `boolean`

**Validation Schema**:

```javascript
const schema = {
    flag: 'boolean'
};
```

---

### 6. `date`

**Description**: Checks if the value is a valid date.

**Rule**: `date`

**Validation Schema**:

```javascript
const schema = {
    birthdate: 'required|date'
};
```

---

### 7. `after`

**Description**: Ensures a date is after a specified target date.

**Rule**: `after:target_date`

**Validation Schema**:

```javascript
const schema = {
    start_date: 'required|date|after:2024-01-01'
};
```

---

### 8. `after_or_equal`

**Description**: Ensures a date is after or equal to a specified target date.

**Rule**: `after_or_equal:target_date`

**Validation Schema**:

```javascript
const schema = {
    start_date: 'required|date|after_or_equal:2024-01-01'
};
```

---

### 9. `date_equals`

**Description**: Checks if the date matches a specific target date.

**Rule**: `date_equals:target_date`

**Validation Schema**:

```javascript
const schema = {
    birthdate: 'required|date_equals:2024-08-29'
};
```

---

### 10. `date_format`

**Description**: Validates that the date matches a specified format.

**Rule**: `date_format:format`

**Validation Schema**:

```javascript
const schema = {
    birthdate: 'required|date_format:YYYY-MM-DD'
};
```

---

### 11. `before`

**Description**: Ensures a date is before a specified target date.

**Rule**: `before:target_date`

**Validation Schema**:

```javascript
const schema = {
    end_date: 'required|date|before:2024-12-31'
};
```

---

### 12. `before_or_equal`

**Description**: Ensures a date is before or equal to a specified target date.

**Rule**: `before_or_equal:target_date`

**Validation Schema**:

```javascript
const schema = {
    end_date: 'required|date|before_or_equal:2024-12-31'
};
```

---

### 13. `digits`

**Description**: Ensures the length of the value matches the specified number of digits.

**Rule**: `digits:number`

**Validation Schema**:

```javascript
const schema = {
    code: 'required|digits:6'
};
```

---

### 14. `state_exists`

**Description**: Checks if the state is a valid state in Nigeria.

**Rule**: `state_exists`

**Validation Schema**:

```javascript
const schema = {
    state: 'required|state_exists'
};
```

---

### 15. `city_exists`

**Description**: Validates if the city is a valid city or Local Government Area (LGA) in the specified state.

**Rule**: `city_exists:state`

**Validation Schema**:

```javascript
const schema = {
    city: 'required|city_exists:state'
};
```

---

### 16. `string`

**Description**: Ensures the value is a string.

**Rule**: `string`

**Validation Schema**:

```javascript
const schema = {
    name: 'required|string'
};
```

---

### 17. `active_url`

**Description**: Checks if the URL is active (i.e., responds with a successful status).

**Rule**: `active_url`

**Validation Schema**:

```javascript
const schema = {
    website: 'required|active_url'
};
```

---

### 18. `array`

**Description**: Validates that the value is an array.

**Rule**: `array`

**Validation Schema**:

```javascript
const schema = {
    items: 'required|array'
};
```

---

### 19. `ascii`

**Description**: Ensures the value contains only ASCII characters.

**Rule**: `ascii`

**Validation Schema**:

```javascript
const schema = {
    text: 'required|ascii'
};
```

---

### 20. `contains`

**Description**: Checks if the value contains a specified substring.

**Rule**: `contains:substring`

**Validation Schema**:

```javascript
const schema = {
    comment: 'required|contains:example'
};
```

---

### 21. `decimal`

**Description**: Validates that the value is a decimal number with up to a specified number of decimal places.

**Rule**: `decimal:places`

**Validation Schema**:

```javascript
const schema = {
    price: 'required|decimal:2'
};
```

---

### 22. `declined`

**Description**: Ensures the value is `false`, usually for decline fields.

**Rule**: `declined`

**Validation Schema**:

```javascript
const schema = {
    declined_field: 'declined'
};
```

---

### 23. `declined_if`

**Description**: Validates a decline based on a condition.

**Rule**: `declined_if:field,value`

**Validation Schema**:

```javascript
const schema = {
    field: 'required|declined_if:another_field,value'
};
```

---

### 24. `different`

**Description**: Ensures the value is different from the target field.

**Rule**: `different:target_field`

**Validation Schema**:

```javascript
const schema = {
    field1: 'required|different:field2'
};
```

---

### 25. `digits_between`

**Description**: Ensures the value has a number of digits within a specified range.

**Rule**: `digits_between:min,max`

**Validation Schema**:

```javascript
const schema = {
    code: 'required|digits_between:4,6'
};
```

---

### 26. `email`

**Description**: Validates that the value is a valid email address.

**Rule**: `email`

**Validation Schema**:

```javascript
const schema = {
    email: 'required|email'
};
```

---

### 27. `exists`

**Description**: Checks if a value exists in the specified database table and column.

**Rule**: `exists:table,column`

**Validation Schema**:

```javascript
const schema = {
    user_id: 'required|exists:users,id'
};
```

---

### 28. `file`

**Description**: Ensures the value is a file.

**Rule**: `file`

**Validation Schema**:

```javascript
const schema = {
    document: 'required|file'
};
```

---

### 29. `filled`

**Description**: Ensures the field is filled if present.

**Rule**: `filled`

**Validation Schema**:

```javascript
const schema = {
    optional_field: 'filled'
};
```

---

### 30. `greater_than`

**Description**: Ensures the value is greater than the target value.

**Rule**: `greater_than:value`

**Validation Schema**:

```javascript
const schema = {
    number: 'required|greater_than:10'
};
```

---

### 31. `greater_than_or_equal`

**Description**: Ensures the value is greater than or equal to the target value.

**Rule**: `greater_than_or_equal:value`

**Validation Schema**:

```javascript
const schema = {
    number: 'required|greater_than_or_equal:10'
};
```

---

### 32. `in`

**Description**: Validates that the value is in a specified set of values.

**Rule**: `in:value1,value2,...`

**Validation Schema**:

```javascript
const schema = {
    status: 'required|in:active,inactive'
};
```

---

### 33. `integer`

**Description**: Ensures the value is an integer.

**Rule**: `integer`

**Validation Schema**:

```javascript
const schema = {
    age: 'required|integer'
};
```

---

### 34. `ip`

**Description**: Validates

that the value is a valid IP address.

**Rule**: `ip`

**Validation Schema**:

```javascript
const schema = {
    ip_address: 'required|ip'
};
```

---

### 35. `json`

**Description**: Ensures the value is a valid JSON string.

**Rule**: `json`

**Validation Schema**:

```javascript
const schema = {
    data: 'required|json'
};
```

---

### 36. `less_than`

**Description**: Ensures the value is less than the target value.

**Rule**: `less_than:value`

**Validation Schema**:

```javascript
const schema = {
    number: 'required|less_than:100'
};
```

---

### 37. `less_than_or_equal`

**Description**: Ensures the value is less than or equal to the target value.

**Rule**: `less_than_or_equal:value`

**Validation Schema**:

```javascript
const schema = {
    number: 'required|less_than_or_equal:100'
};
```

---

### 38. `max`

**Description**: Validates that the value does not exceed a specified maximum length.

**Rule**: `max:value`

**Validation Schema**:

```javascript
const schema = {
    description: 'required|max:255'
};
```

---

### 39. `mimes`

**Description**: Ensures the file is of a specified MIME type.

**Rule**: `mimes:type1,type2,...`

**Validation Schema**:

```javascript
const schema = {
    file: 'required|mimes:jpeg,png,pdf'
};
```

---

### 40. `min`

**Description**: Validates that the value meets a minimum length requirement.

**Rule**: `min:value`

**Validation Schema**:

```javascript
const schema = {
    description: 'required|min:10'
};
```

---

### 41. `numeric`

**Description**: Ensures the value is numeric.

**Rule**: `numeric`

**Validation Schema**:

```javascript
const schema = {
    quantity: 'required|numeric'
};
```

---

### 42. `present`

**Description**: Ensures the field is present, but it can be empty.

**Rule**: `present`

**Validation Schema**:

```javascript
const schema = {
    optional_field: 'present'
};
```

---

### 43. `prohibited`

**Description**: Validates that the field is prohibited.

**Rule**: `prohibited`

**Validation Schema**:

```javascript
const schema = {
    forbidden_field: 'prohibited'
};
```

---

### 44. `required_if`

**Description**: Ensures the field is required based on a condition.

**Rule**: `required_if:another_field,value`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_if:another_field,value'
};
```

---

### 45. `required_unless`

**Description**: Validates that the field is required unless a condition is met.

**Rule**: `required_unless:another_field,value`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_unless:another_field,value'
};
```

---

### 46. `required_with`

**Description**: Ensures the field is required if another field is present.

**Rule**: `required_with:another_field`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_with:another_field'
};
```

---

### 47. `required_with_all`

**Description**: Validates that the field is required if all specified fields are present.

**Rule**: `required_with_all:field1,field2,...`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_with_all:field1,field2'
};
```

---

### 48. `required_without`

**Description**: Ensures the field is required if another field is not present.

**Rule**: `required_without:another_field`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_without:another_field'
};
```

---

### 49. `required_without_all`

**Description**: Validates that the field is required if none of the specified fields are present.

**Rule**: `required_without_all:field1,field2,...`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_without_all:field1,field2'
};
```

---

### 50. `same`

**Description**: Ensures the value matches the value of another field.

**Rule**: `same:confirm_field`

**Validation Schema**:

```javascript
const schema = {
    field: 'required|same:confirm_field'
};
```

---

### 51. `size`

**Description**: Validates that the value has a specific size (for strings, arrays, etc.).

**Rule**: `size:value`

**Validation Schema**:

```javascript
const schema = {
    field: 'required|size:10'
};
```

---

### 52. `starts_with`

**Description**: Ensures the value starts with a specified string.

**Rule**: `starts_with:prefix`

**Validation Schema**:

```javascript
const schema = {
    field: 'required|starts_with:prefix'
};
```

---

### 53. `uuid`

**Description**: Checks if the value is a valid UUID.

**Rule**: `uuid`

**Validation Schema**:

```javascript
const schema = {
    uuid: 'required|uuid'
};
```

---

### 54. `uppercase`

**Description**: Validates that the value is in uppercase.

**Rule**: `uppercase`

**Validation Schema**:

```javascript
const schema = {
    text: 'required|uppercase'
};
```
---

### 55. `url`

**Description**: Validates that the value is a valid URL.

**Rule**: `url`

**Validation Schema**:

```javascript
const schema = {
    website: 'required|url'
};
```

---

### 56. `uuid`

**Description**: Checks if the value is a valid UUID.

**Rule**: `uuid`

**Validation Schema**:

```javascript
const schema = {
    identifier: 'required|uuid'
};
```

---

### 57. `timezone`

**Description**: Ensures the value is a valid timezone.

**Rule**: `timezone`

**Validation Schema**:

```javascript
const schema = {
    timezone: 'required|timezone'
};
```

---

### 58. `file_size`

**Description**: Validates the size of a file, ensuring it does not exceed a specified limit.

**Rule**: `file_size:max`

**Validation Schema**:

```javascript
const schema = {
    file: 'required|file|file_size:2048'  // size in kilobytes
};
```

---

### 59. `integer`

**Description**: Ensures the value is an integer.

**Rule**: `integer`

**Validation Schema**:

```javascript
const schema = {
    age: 'required|integer'
};
```

---

### 60. `less_than`

**Description**: Ensures the value is less than a specified value.

**Rule**: `less_than:value`

**Validation Schema**:

```javascript
const schema = {
    quantity: 'required|less_than:100'
};
```

---

### 61. `less_than_or_equal`

**Description**: Ensures the value is less than or equal to a specified value.

**Rule**: `less_than_or_equal:value`

**Validation Schema**:

```javascript
const schema = {
    quantity: 'required|less_than_or_equal:100'
};
```

---

### 62. `max`

**Description**: Validates that the value does not exceed a specified maximum length.

**Rule**: `max:value`

**Validation Schema**:

```javascript
const schema = {
    description: 'required|max:255'
};
```

---

### 63. `min`

**Description**: Ensures the value meets a minimum length requirement.

**Rule**: `min:value`

**Validation Schema**:

```javascript
const schema = {
    description: 'required|min:10'
};
```

---

### 64. `mimes`

**Description**: Ensures the file is of a specified MIME type.

**Rule**: `mimes:type1,type2,...`

**Validation Schema**:

```javascript
const schema = {
    file: 'required|mimes:jpeg,png,pdf'
};
```

---

### 65. `numeric`

**Description**: Ensures the value is numeric.

**Rule**: `numeric`

**Validation Schema**:

```javascript
const schema = {
    price: 'required|numeric'
};
```

---

### 66. `present`

**Description**: Ensures the field is present, but it can be empty.

**Rule**: `present`

**Validation Schema**:

```javascript
const schema = {
    optional_field: 'present'
};
```

---

### 67. `prohibited`

**Description**: Validates that the field is prohibited.

**Rule**: `prohibited`

**Validation Schema**:

```javascript
const schema = {
    forbidden_field: 'prohibited'
};
```

---

### 68. `required_if`

**Description**: Ensures the field is required based on a condition.

**Rule**: `required_if:another_field,value`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_if:another_field,value'
};
```

---

### 69. `required_unless`

**Description**: Validates that the field is required unless a condition is met.

**Rule**: `required_unless:another_field,value`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_unless:another_field,value'
};
```

---

### 70. `required_with`

**Description**: Ensures the field is required if another field is present.

**Rule**: `required_with:another_field`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_with:another_field'
};
```

---

### 71. `required_with_all`

**Description**: Validates that the field is required if all specified fields are present.

**Rule**: `required_with_all:field1,field2,...`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_with_all:field1,field2'
};
```

---

### 72. `required_without`

**Description**: Ensures the field is required if another field is not present.

**Rule**: `required_without:another_field`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_without:another_field'
};
```

---

### 73. `required_without_all`

**Description**: Validates that the field is required if none of the specified fields are present.

**Rule**: `required_without_all:field1,field2,...`

**Validation Schema**:

```javascript
const schema = {
    field: 'required_without_all:field1,field2'
};
```

---

### 74. `same`

**Description**: Ensures the value matches the value of another field.

**Rule**: `same:confirm_field`

**Validation Schema**:

```javascript
const schema = {
    password: 'required|same:password_confirmation'
};
```

---

### 75. `size`

**Description**: Validates that the value has a specific size (for strings, arrays, etc.).

**Rule**: `size:value`

**Validation Schema**:

```javascript
const schema = {
    field: 'required|size:10'
};
```

---

### 76. `starts_with`

**Description**: Ensures the value starts with a specified string.

**Rule**: `starts_with:prefix`

**Validation Schema**:

```javascript
const schema = {
    field: 'required|starts_with:prefix'
};
```

---

### 77. `uuid`

**Description**: Checks if the value is a valid UUID.

**Rule**: `uuid`

**Validation Schema**:

```javascript
const schema = {
    identifier: 'required|uuid'
};
```

---

### 78. `uppercase`

**Description**: Validates that the value is in uppercase.

**Rule**: `uppercase`

**Validation Schema**:

```javascript
const schema = {
    text: 'required|uppercase'
};
```

---

### 79. `url`

**Description**: Validates that the value is a valid URL.

**Rule**: `url`

**Validation Schema**:

```javascript
const schema = {
    website: 'required|url'
};
```

---

### 80. `timezone`

**Description**: Ensures the value is a valid timezone.

**Rule**: `timezone`

**Validation Schema**:

```javascript
const schema = {
    timezone: 'required|timezone'
};
```

---

### 81. `file_size`

**Description**: Validates the size of a file, ensuring it does not exceed a specified limit.

**Rule**: `file_size:max`

**Validation Schema**:

```javascript
const schema = {
    file: 'required|file|file_size:2048'  // size in kilobytes
};
```

---

## Conclusion

This documentation provides a comprehensive overview of validation rules, including their descriptions, rules, and example validation schemas. Use these schemas as a basis to ensure your data meets the required validation criteria.
```

This should cover all the rules. Feel free to adjust the Markdown content to better fit your needs or specific validation requirements.
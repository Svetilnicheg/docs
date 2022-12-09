# condition.schema

Allows validating data using [JSON Schema](https://json-schema.org/learn/getting-started-step-by-step.html). This is a special format for describing data in JSON format.

For example, you can describe the data type, the minimum and maximum values, and specify that all values must be unique.

This component is useful in the following cases:

- If [available components](index.md) don't provide everything you need to configure validation.
- If you already have a prepared JSON Schema configuration for the check and you want to use it.

Here is the [usage example](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE05gAFkTABrAEYQAHgFoEAJwgBXJsJVK83AIbmdmkIDoIIAMIIDMIIB8IIDcIGGATCBhgFwgbtSqeBBMdHDQsihYCkmqynn5tN6+3P6AeCCA-CCAYiCAHCCA8iBYAIyJRWJ4+F7cTqzZHV09LSDuqgC+IoVKVG00nj5+fSBVdY0ATK0z7AO9FP3dROvDk2LjI1NnySAlC7tLNQ1YAMwbM3s9-p37z0czoxdYAF0JkU8LovHQvGxpm08OodrQwRDOM46EwnIIQMCYSAmODDP5cXR8T98qdjlteIiMlAof8cLDmPC8JAoLoJNTOHwjNJIZi6QjwbyKNDXvRGf5jNwWPZkeYAFYmOirIhQOj2YhZLGixFCgqbWZijSLHXI9FojFazZ4QnE242vD8nB-clOy2XLnGKS6kXYuH+Lz2exeBgvbFSOBQACSkhkbHWLqwZNFhgjGNugBwQWqAXhBaoAeEEAwiC5rCHf7OsbuAGKZ2jTEgCPmlBoGujIA). 

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.schema" | Set component type ||
|| `data` | _any_ | Data that should be checked. ||
|| `hint` | _string_ | Validation error message that a Toloker will see ||
|| `schema` | _JSON Schema draft 7_ | The schema for validating data. ||
|#

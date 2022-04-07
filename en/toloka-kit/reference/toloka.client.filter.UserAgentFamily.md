# UserAgentFamily
`toloka.client.filter.UserAgentFamily` | [Source code](https://github.com/Toloka/toloka-kit/blob/v0.1.24/src/client/filter.py#L573)

```python
UserAgentFamily(
    self,
    operator: IdentityOperator,
    value: Union[UserAgentFamily, str]
)
```

Use to select users by user agent family.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>Comparison operator in the condition. For example, for a condition &quot;The user must be 18 years old or older» used date of birth and operator GTE («Greater than or equal»). Possible key values operator depends on the data type in the field value</p>
`value`|**[UserAgentFamily](toloka.client.filter.UserAgentFamily.UserAgentFamily.md)**|<p>User agent family.</p>

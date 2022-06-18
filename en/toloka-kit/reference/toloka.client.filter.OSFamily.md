# OSFamily
`toloka.client.filter.OSFamily` | [Source code](https://github.com/Toloka/toloka-kit/blob/v0.1.26/src/client/filter.py#L467)

```python
OSFamily(
    self,
    operator: IdentityOperator,
    value: Union[OSFamily, str]
)
```

Use to select users by their OS family.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>Comparison operator in the condition. For example, for a condition &quot;The user must be 18 years old or older» used date of birth and operator GTE («Greater than or equal»). Possible key values operator depends on the data type in the field value</p>
`value`|**[OSFamily](toloka.client.filter.OSFamily.OSFamily.md)**|<p>The operating system family.</p>

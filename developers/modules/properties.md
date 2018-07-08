# Properties

Module properties are settings that can be changed by the user from the administration area.

A property must be in **camelCase**. They must be assigned a `type`, and optionally a `default` value and `enum` list.

### Property Types

Only the following types are allowed:

* String
* Number
* Boolean

### Example

```javascript
{
    exampleProperty: String,
    anotherProperty: Number,
    propertyWithDefault: {
        type: String,
        default: 'abc'
    },
    propertyWithEnumList: {
        type: String,
        default: 'first',
        enum: ['first', 'second', 'third']
    }
}
```

### Options

#### type

The type is **required**. It can be either the property direct value or as an object property named `type`. Must be one of the allowed types listed [above](properties.md#property-types).

#### default

The default value is **optional**. If omitted, the type default value will be inferred:

* String: `""` _\(empty string\)_
* Number: `0`
* Boolean: `false`

#### enum

The enum value is **optional**. If provided, it must be an **array of strings**. A dropdown select will be presented to the user with the values of the array as possible choices. When using enum, the `default` value must be provided as well.


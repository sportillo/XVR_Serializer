# XVR Object Serializer
Object serializer and deserializer for XVR Application.

An object (an instance of a class) is serialized in (encoded) JSON-like string.
### Serialization
```javascript
var object_to_be_serialized = TestObj();
var child_obj = ChildObj();
object_to_be_serialized.id = 1;
object_to_be_serialized.name = "Father";
object_to_be_serialized.arr = {true, 2, "Lorem"};

child_obj.name = "Child";

object_to_be_serialized.child = child_obj;
  
var serializer = Serializer();
var serialized_obj = serializer.Serialize(object_to_be_serialized);
```

### Deserialization
```javascript
var serializer = Serializer();
var new_obj = TestObj();

new_obj = serializator.Deserialize(serialized_obj);
```

### Class Factory
A funciton *ClassName*_Factory is required in order to serialize instances of that class.

The function must return an array containing an instance of the class and an array of attributes to serialize.

```javascript
function TestObj_Factory() {
  return {TestObj(), {"name", "id", "arr"}};
}
```

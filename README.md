# XVR Object Serializer
Object serializer and deserializer for XVR Application.

An object (an instance of a class) is serialized in (encoded) JSON-like string.
### Serialization
```javascript
var object_to_be_serialized = TestObj();
object_to_be_serialized.id = 1;
object_to_be_serialized.name = "Some";
object_to_be_serialized.arr = {true, 2, "Lorem"};
  
var serializer = Serializer();
serializer.RegisterAttribute({"name", "id", "arr"});
  
var serialized_obj = serializer.Serialize(object_to_be_serialized);
```

### Deserialization
```javascript
  var serializer = Serializer();
  var new_obj = TestObj();
  
  new_obj = serializator.Deserialize(new_obj, serialied_obj);
```

### node-opencv
---
https://github.com/peterbraden/node-opencv

```cc
// test/nativemat.cc
#include <nan.h>
#include <Matrix.h>

void Size(const Nan::FunctionCallbackInfo<v8::Value>& info) {
 cv::Mat mat = Nan::ObjectWrap::Unwarp<node_opencv::Matrix>(info[0]->ToObject())->mat;
 
  v8::Local < v8::Array > arr = Nan::New<v8::Array>(2);
  arr->Set(0, Nan::New<v8::Number>(mat.size().height));
  arr->Set(1, Nan::New<v8::Number>(mat.size().width));

  info.GetReturnValue().Set(arr);
}

void Init(v8::Local<v8::Object> exports) {
  exports->Set(Nan::New("size").ToLocalChecked(),
    Nan::New<v8::FunctionTemplate>(Size)->GetFunction());
}

NODE_MODULE(test_nativemat, Init)

```

```
```

```
```



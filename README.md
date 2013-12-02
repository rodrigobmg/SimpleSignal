# High performance C++11 signals
See [erformance of a C++11 Signal System](http://www.testbit.eu/2013/cpp11-signal-system-performance/) for
the original source code, as well as performance measurements compared to other signalling systems.

## Declare a signal
This example declares a signal 'sig' that takes three arguments and returns a char.
```c++
Simple::Signal<char (float, int, std::string)> sig;
```
## Connect to a signal
This exampple connects to a static function.
It is also possible to connect to member functions or lambda functions.
```c++
static char float_callback (float f, int, std::string) {
  // ...
  return 0;
}

void Init() {
  sig.connect(float_callback);
}
```

# Fire a signal
```c++
void func() {
  // ...
  sig.emit(1.0f, 7, "xxxx");
}
```

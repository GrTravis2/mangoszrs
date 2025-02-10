# The Plan

I think we should go module by module converting the C++ code to rust, and work our way backward from there. There are
some interop capabilities between Rust and C++ working through the C FFI, but I haven't used CMake in a long time and it
might be difficult trying to figure out how to hook that into the base mango zero project.

The code ported to Rust should conform to Rust best practices, and not C++. Here are a few examples:

* Try and make variables immutable whenever possible, and functions have as few side effects/state mutation as possible.
* Try and represent certain properties in the types themselves rather than in the code, for example how Option<T> can be
  used instead of nullptr to represent an absent value.

I'm going to start working on the src/Common package and see what can be ported over easily.

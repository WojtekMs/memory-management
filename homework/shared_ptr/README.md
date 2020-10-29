### `weak_ptr`

Implementation of my own `weak_ptr`

* Proper cooperation with `shared_ptr`
  * weak_ptr can be created from shared_ptr
  * weak_ptr c-tor increments weak_ref count
  * weak_ptr d-tor:
    * decrements weak_ref count
    * releases controlBlock if weak_ref count == 0 && shared_ref count == 0 
* Member functions: `use_count()`, `expired()`, `lock()`, `reset()`

### Some of `shared_ptr` and `weak_ptr` features are not implemented on this branch. To see the full implementation go here:
[complete implementation](https://github.com/WojtekMs/memory-management/tree/make_shared/homework/shared_ptr)

#### `weak_ptr`:
* Proper cooperation with `shared_ptr`
  * weak_ptr can be created from shared_ptr
  * weak_ptr c-tor increments weak_ref count
  * weak_ptr d-tor:
    * decrements weak_ref count
    * releases controlBlock if weak_ref count == 0 && shared_ref count == 0 
* Member functions: `use_count()`, `expired()`, `lock()`, `reset()`

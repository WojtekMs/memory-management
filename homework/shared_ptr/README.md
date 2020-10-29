### On this branch shared_ptr is a standalone class and there is no support for weak_ptr implemented. To see full implementation of of my shared_ptr cooperating with weak_ptr go here:
[complete implementation](https://github.com/WojtekMs/memory-management/tree/make_shared/homework/shared_ptr)



`shared_ptr` is a RAII class:

* Holds a pointer to managed object (template class)
* Holds a pointer to shared control block with 2 counters and a deleter:
  * shared_refs count (as `std::atomic<size_t>`)
  * weak_refs count (as `std::atomic<size_t>`)
  * deleter (function pointer)
* Constructor copies a pointer and allocates the control block
* Destructor decreases shared_refs and:
  * if shared_refs == 0 -> releases the managed object
  * if shared_refs == 0 and weak_refs == 0 -> releases the control block
* Copying is allowed - it increments shared_refs
* Moving is allowed and it means:
  * Copying original pointers to a new object
  * Setting source pointer to nullptr
* Member functions: `operator*()`, `operator->()`, `get()`, `reset()`, `use_count()`, `operator bool()`

Additionally there is CI - UT + Valgrind

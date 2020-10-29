# `unique_ptr`

My own unique_ptr (simplified).

unique_ptr is a RAII class:

* Holds a pointer to managed object (template class)
* Constructor copies a pointer
* Destructor releases memory
* Copying is not allowed
* Moving is allowed and it means:
  * Copying original pointer to a new object
  * Setting source pointer to nullptr
* Member functions: operator*(), operator->(), get(), release(), reset()

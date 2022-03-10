💙 C++ Smart Pointers 💙

Smart pointers implement explicit memory management according to RAII idiom.

When they go out of scope, their resources are automatically released.

There are 3 types of smart pointers:

▶ unique_ptr
▶ shared_ptr
▶ weak_ptr

🧵 ⇊

#cpp #cplusplus

What RAII means ?

It's an acronym for Resource Acquisition Is Initialization.

The acquisition and release of a resource by a smart pointer are bound to its lifetime.

https://twitter.com/Franc0Fernand0/status/1480475521729318921?s=20&t=wUtTLoeMZXaddLg-JvLeNw

The resource memory is allocated in the constructor and deallocated in the destructor. unique_ptr

▶ owns exclusively a resource

▶ automatically releases the resource if it goes out of scope

▶ can’t be copied

▶ can be used in STL containers and algorithms



shared_ptr

▶ share the ownership of a resource

▶ keep 2 handler: for the resource and for its reference counter

▶ increase the counter +1 for every copy and

▶ decrease the counter -1 if the pointer goes out of scope

▶ release the resource when the counter is 0



weak_ptr

▶ not a real smart pointer

▶ borrows a resource from a shared_ptr withou increasing its reference counter

▶ useful mainly to break a cycle of shared_ptr


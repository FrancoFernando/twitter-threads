ð C++ Smart Pointers ð

Smart pointers implement explicit memory management according to RAII idiom.

When they go out of scope, their resources are automatically released.

There are 3 types of smart pointers:

â¶ unique_ptr
â¶ shared_ptr
â¶ weak_ptr

ð§µ â

#cpp #cplusplus

What RAII means ?

It's an acronym for Resource Acquisition Is Initialization.

The acquisition and release of a resource by a smart pointer are bound to its lifetime.

https://twitter.com/Franc0Fernand0/status/1480475521729318921?s=20&t=wUtTLoeMZXaddLg-JvLeNw

The resource memory is allocated in the constructor and deallocated in the destructor. unique_ptr

â¶ owns exclusively a resource

â¶ automatically releases the resource if it goes out of scope

â¶ canât be copied

â¶ can be used in STL containers and algorithms



shared_ptr

â¶ share the ownership of a resource

â¶ keep 2 handler: for the resource and for its reference counter

â¶ increase the counter +1 for every copy and

â¶ decrease the counter -1 if the pointer goes out of scope

â¶ release the resource when the counter is 0



weak_ptr

â¶ not a real smart pointer

â¶ borrows a resource from a shared_ptr withou increasing its reference counter

â¶ useful mainly to break a cycle of shared_ptr


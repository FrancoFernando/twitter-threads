C# provides many collection interfaces:

• IEnumerable
• ICollection
• IList

All can hold a list of items, but which one should you use and when ?

// Thread // ↓

#csharp #dotnet

IEnumerable

It is the most basic interface:

🗸 allow iteration over the items
🗸 fully supports LINQ
✗ doesn't hold the count of the items

ICollection

It derives from IEnumerable, extending its functionality to add, remove and update items.

It holds the count of elements that can be retrieved in O(1) time. IList

It derives from ICollection adding a little more functionality like the idea of an order.

This means that IList supports inserting and removing of items in a specific position. You should always use the simplest interface implementing what you need.

1. IEnumerable if you need only to iterate and query over collections.

2. ICollection if you need also to add, remove, count the items.

3. IList if you need your collection to be in a defined order.

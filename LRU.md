# Design LRU cache

* [146. LRU Cache](https://leetcode-cn.com/problems/lru-cache/)

## Idea

* Requirement
  * **get(key), O(1) time** - Get the value (will always be positive) of the key if the key exists in the cache, otherwise return -1.
  * **put(key, value), O(1) time** - Set or insert the value if the key is not already present
    * When the cache reached its capacity, it should *invalidate the least recently used item* before inserting a new item.
* Solution
  * **hash table**
    * key: number
    * value: corresponding position/index in list
  * **doubly linked list**
    * position/index: recently accessed value should be put at head of list
    * value: number

## Implementation

```java

```

```cpp

```

```go
import "container/list"

type LRUCache struct {
	m          map[int]*list.Element
	accessTime *list.List
	capacity   int
}
type record struct {
	k int
	v int
}

func Constructor(capacity int) LRUCache {
	return LRUCache{make(map[int]*list.Element), list.New(), capacity}
}

func (this *LRUCache) Get(key int) int {
	if e, ok := this.m[key]; ok {
		this.accessTime.MoveToFront(e)
		if r, ok := e.Value.(*record); ok {
			return r.v
		}
	}
	return -1
}

func (this *LRUCache) Put(key int, value int) {
	// modify existing record
	if e, ok := this.m[key]; ok {
		this.accessTime.MoveToFront(e)
		if r, ok := e.Value.(*record); ok {
			// use pointer to modify element otherwise would modify copied element
			r.v = value
		}
		return
	}
	// pop out victim
	if this.accessTime.Len() == this.capacity {
		if target, ok := this.accessTime.Back().Value.(*record); ok {
			delete(this.m, target.k)
			this.accessTime.Remove(this.accessTime.Back())
		}
	}
	this.m[key] = this.accessTime.PushFront(&record{key, value})
}
```

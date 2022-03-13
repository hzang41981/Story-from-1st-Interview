LinkedHashMap = HashMap + Insertion Order
Used to solve: 1. [LRU cache](https://leetcode.com/problems/lru-cache/)

# Java
```java
public class LinkedHashMap<K,​V> extends HashMap<K,​V> implements Map<K,​V>

super.getOrDefault(key, -1)
super.put(key, value)
super.containsKey(key)
super.keySet()
super.entrySet()
super.values()

@Override
protected boolean removeEldestEntry(Map.Entry<Integer, Integer> eldest) {
    return size() > capacity; 
}

// For-each loop for traversal over Map
for (Map.Entry<Integer, String> mapElement : hm.entrySet()) { }
```

## Design
(Previous, Key, Value, Next)
Preious, Next are implemented through LinkedList;
Key, Value are inherited from HashMap;

## Synchronized Version
```java
Map m = Collections.synchronizedMap(new LinkedHashMap(...));
```

## Constructor
fillRatio: size is increased when 75% (default value) is full;
Order: True => last access order (least recently at the top ???, removed first); False => insertion order (first insert, first out)
```java
LinkedHashMap<K, V> lhm = new LinkedHashMap<K, V>(int capacity, float fillRatio, boolean Order);
```

## Override

### removeEldestEntry
``` java
LinkedHashMap<Integer, String> li_hash_map =
new LinkedHashMap<Integer, String>() {
    protected boolean removeEldestEntry(Map.Entry<Integer, String> eldest)
    {
        return size() > MAX;
    }
};
```
        

[reference 1](https://www.geeksforgeeks.org/linkedhashmap-class-in-java/)

[reference 2]https://www.geeksforgeeks.org/linkedhashmap-class-in-java/

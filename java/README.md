[Back](../README.md)

# Java questions

## Collections package


### How HashMap works

 - ``hashCode()`` / ``equals()`` contract
 - backet per ``hashCode``, backet stored in ``LinkedList<Map.Entry>``
 - bakets organised as an array of backets, and retrieved by index = ``hashCode()`` % initial map size

```HashMap``` is not thread safe. Use ``Collections.synchronizedMap()`` or ``java.util.concurrent.ConcurrentHashMap``

## Lanmda


## Inheritance / Incapsulation / Polymorphism


## Overloading / Overwriting

---
layout: page
title: "Arrays"
description: ""
---
{% include JB/setup %}

{% include menu/arrays.md %}

* * * 

## Facts


* Numeric keys, either auto assigned or assigned by you, are great when you don’t care how the data is indexed
* Associative arrays are frequently used with databases, or when there should be some key=>value association
* Multi-Dimensional arrays, or arrays of arrays, can contain a lot of data, but can also be complicated to access
* keys containing only digits are cast to integers
* array keys are case-sensitive, but type insensitive


* * *

## Iteration


* `foreach()` operates on a copy of the array
* `foreach($array AS &$value) { … }`
* `end()` – move pointer to last element
* `key()` - retreives key from current position
* `next()` – advances array pointer one spot then returns current value
* `prev()` – rewinds the array pointer one spot, then returns the current value
* `reset()` – resets the array pointer to the beginning of the array
* `each()` – returns the current key and value from the array, then iterates
* `current()`


* * *

## Sorting


* `bool sort ( array &$array [, int $sort_flags = SORT_REGULAR ] )`
   * `SORT_REGULAR`
   * `SORT_NUMERIC`
   * `SORT_STRING`
* `rsort()`like sort, but in reverse order (highest to lowest)
* `ksort()`sorts by key, maintaining key to data correlations. This is useful mainly for associative arrays.
* `asort()` sorts an array such that array indices maintain their correlation with the array elements they are associated with. This is used mainly when sorting associative arrays where the actual element order is significant.
* `usort (array &$array, callable $value_compare_func)`sorts an array by its values using a user-supplied comparison function. If the array you wish to sort needs to be sorted by some non-trivial criteria, you should use this function.
* `bool natsort ( array &$array )`implements a sort algorithm that orders alphanumeric strings in the way a human being would while maintaining key/value associations. This is described as a "natural ordering"
* `bool shuffle ( array &$array )`shuffles (randomizes the order of the elements in) an array.


* * *

## Stacks & Queues


* Stack, implementing LIFO (Last-In, First-Out)
   * `int array_push ( array &$array , mixed $var [, mixed $... ] )` treats array as a stack, and pushes the passed variables onto the end of array. The length of array increases by the number of variables pushed.
   * `mixed array_pop ( array &$array )` pops and returns the last value of the array, shortening the array by one element.
* FIFO (First-In, First-Out)
   * `int array_unshift ( array &$array , mixed $var [, mixed $... ] )` prepends passed elements to the front of the array. Note that the list of elements is prepended as a whole, so that the prepended elements stay in the same order. All numerical array keys will be modified to start counting from zero while literal keys won't be touched.
   * `mixed array_shift ( array &$array )` shifts the first value of the array off and returns it, shortening the array by one element and moving everything down. All numerical array keys will be modified to start counting from zero while literal keys won't be touched.


* * *

## Functions


[http://php.net/array/](http://php.net/array/)

* `bool array_walk ( array &$array , callback $funcname [, mixed $userdata ] )` Applies the user-defined callback function to each element of the array array. array_walk() is not affected by the internal array pointer of array. array_walk() will walk through the entire array regardless of pointer position.
* `bool array_walk_recursive ( array &$input , callback $funcname [, mixed $userdata ] )` Applies the user-defined callback function to each element of the array. This function will recurse into deeper arrays.
* `array array_keys ( array $input [, mixed $search_value [, bool $strict = false ]] )`  returns the keys, numeric and string, from the array. If the optional search_value is specified, then only the keys for that value are returned. Otherwise, all the keys from the array are returned.
* `array array_values ( array $input )` returns all the values from the array and indexes the array numerically.
* `array array_change_key_case ( array $input [, int $case = CASE_LOWER ] )` Returns an array with all keys from array lowercased or uppercased. Numbered indices are left as is.
* `array array_merge ( array $array1 [, array $array2 [, array $... ]] )`  Merges the elements of one or more arrays together so that the values of one are appended to the end of the previous one. It returns the resulting array. If the input arrays have the same string keys, then the later value for that key will overwrite the previous one. If, however, the arrays contain numeric keys, the later value will not overwrite the original value, but will be appended. Values in the input array with numeric keys will be renumbered with incrementing keys starting from zero in the result array.
* `array array_merge_recursive ( array $array1 [, array $... ] )` like array_merge, but If the input arrays have the same string keys, then the values for these keys are merged together into an array, and this is done recursively, so that if one of the values is an array itself, the function will merge it with a corresponding entry in another array too. If, however, the arrays have the same numeric key, the later value will not overwrite the original value, but will be appended.
* `array array_splice ( array &$input , int $offset [, int $length = 0 [, mixed $replacement ]] )` Removes the elements designated by offset and length from the input array, and replaces them with the elements of the replacement array, if supplied.
* `bool array_key_exists ( mixed $key , array $search )` returns TRUE if the given key is set in the array. key can be any value possible for an array index.
* `array array_flip ( array $trans )` returns an array in flip order, i.e. keys from array become values and values from array become keys. Note that the values of array need to be valid keys, i.e. they need to be either integer or string. A warning will be emitted if a value has the wrong type, and the key/value pair in question will not be included in the result. If a value has several occurrences, the latest key will be used as its value, and all others will be lost.
* `array array_reverse ( array $array [, bool $preserve_keys = false ] )` Takes an input array and returns a new array with the order of the elements reversed.
* `array array_combine ( array $keys , array $values )` Creates an array by using the values from the keys array as keys and the values from the values array as the corresponding values.
* `mixed array_rand ( array $input [, int $num_req = 1 ] )` Picks one or more random entries out of an array, and returns the key (or keys) of the random entries.
* `array array_diff ( array $array1 , array $array2 [, array $ ... ] )` Compares array1 against one or more other arrays and returns the values in array1 that are not present in any of the other arrays.
* `array array_intersect ( array $array1 , array $array2 [, array $ ... ] )` returns an array containing all the values of array1 that are present in all the arguments. Note that keys are preserved.
* `bool in_array ( mixed $needle , array $haystack [, bool $strict ] )` Searches haystack for needle using loose comparison unless strict is set.
* `array list ( mixed $varname [, mixed $... ] )` is used to assign a list of variables in one operation.
* `int count ( mixed $var [, int $mode = COUNT_NORMAL ] )` Counts all elements in an array, or something in an object.
* `int extract ( array $var_array [, int $extract_type = EXTR_OVERWRITE [, string $prefix ]] )` Import variables from an array into the current symbol table.


* * *

## SPL, Objects as arrays

* [http://www.php.net/manual/en/class.arrayobject.php](http://www.php.net/manual/en/class.arrayobject.php)
* [http://www.php.net/manual/en/class.arrayiterator.php](http://www.php.net/manual/en/class.arrayiterator.php)
* [http://www.php.net/manual/en/class.recursivearrayiterator.php](http://www.php.net/manual/en/class.recursivearrayiterator.php)


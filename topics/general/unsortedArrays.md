# Unsorted Arrays

## append(val)
```C
if (len_cur == len_max) {
  len_max *= 2;   // double len_max
}
arr[len_cur] = val;
++len_cur;

```

## insert(val, idx)
```C
if (len_cur == len_max) {
  len_max *= 2;   // double len_max
}
for (j = len_cur - 1; j >= idx; --j) {   // shift elements right
  array[j + 1] = arr[j];
}
arr[idx] = val;
++len_cur;

```

## remove(idx)
```C
// if empty, do nothing
// remove array[i]
for (j = idx + 1; j < len_cur; ++j) {   // shift elements left
  arr[j - 1] = arr[j];
}
--len_cur;

```

## min
```C
// if empty, do nothing
min = array[0];
for (i = 1; i < len_cur; ++i) {
  if (arr[i] < min) {
    min = arr[i];
  }
}
return min;

```

## quickselect(k)
Returns the `k`th smallest element.
```C
// if empty, do nothing
start_idx = 0;
end_idx = len_cur - 1;
while (start_idx < end_idx) {
  idx = partition(arr, 1, k);
  ???
```

## count(val)
Count the number of occurrences of `val`.
```C
// if empty, return 0
count = 0;
for (i = 0; i < len_cur; ++i) {
  if (arr[i] == len_curr) {
    ++count;
  }
}
return count;

```

## search(val)
```C
// if empty, return NOT_FOUND
idx = 0;   // set to another value to search from some value k
while (arr[idx] !== val) {
  ++idx;
  if (idx == len_max) {
    return NOT_FOUND;
  }
}
return idx;

```

## unique?(val) 
```C
// if empty, do nothing
occurrences = count(val);   // above function
if (occurrences == 0) {
  return NOT_FOUND;
} else if (occurrences == 1) {
  return true;
}
return false;   // can simplify to "return occurrences"

```

## removeDuplicates()
```C
// if empty, do nothing
// copy arr into cpy
// clear arr
fill_idx = 0;
for (i = 0; i < len_max; ++i) {
  // if cpy[i] is NOT in the REST of the array (search from i)
    arr[fill_idx] = cpy[i];
    ++fill_idx;
}
// delete cpy

```

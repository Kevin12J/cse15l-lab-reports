# Lab Report 3: Bugs and Commands
## Part 1: Bugs
### Failure inducing input (JUnit test)
```
@Test 
public void testReversedOneElement(){
  int[] input1={};
  assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
}
```
###  Input that doesn't induce failure (JUnit test)
```
@Test
public void testReversedMultipleElement() {
  int[] input1 = {1,2,3,4};
  assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input1));
}
```
### Symptom (running JUnit tests)
![image}(
### Method in ArrayExamples.java
```
// Changes the input array to be in reversed order
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```

### Bug

### input that doesn't induce a failure

## Part 2: Researching Commands

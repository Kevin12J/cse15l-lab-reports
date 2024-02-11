# Lab Report 3: Bugs and Commands
## Part 1: Bugs
### Failure inducing code
#### Junit test in ArrayTests.java
```
@Test 
public void testReverseInPlace() {
  int[] input1 = { 3 ,4};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{ 4,3 }, input1);
}
```
#### Method in ArrayExamples.java
```
// Changes the input array to be in reversed order
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```
#### Symptom

#### Bug

### input that doesn't induce a failure

## Part 2: Researching Commands

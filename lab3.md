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
![image](/tests.png)
### Bug
#### Code Before
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```
#### Code After
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```


## Part 2: Researching Commands

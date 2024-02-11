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
One of the bugs in the code was in the line `arr[i] = newArray[arr.length - i -1];` because it assigned the values in `newArray` which were all initialized to `0` in reversed order to `arr`. The second bug was in the line `return arr;` because the original array was being returned instead of a new array.
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
The first change was changing `arr[i] = newArray[arr.length - i -1];` to `newArray[i] = arr[arr.length - i - 1];`. This fixed the bug with the values in `newArray` being assigned to `arr` so now the values in `arr` get put into `newArray` in reversed order. The second change was changing `return arr;` to `return newArray`. This fixed the bug in which the wrong array was being returned so now the new array will be returned.

## Part 2: Researching Commands
### `grep` 
#### command-line option #1: `--invert-match`
#### command-line option #2: ` --exclude-dir`
#### command-line option #3: `-n`,`--line-number`
#### command-line option #4: `--colour=[when]`,`--color=[when]`


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
#### command-line option #1 `-r` (found using `man grep`)
##### calling `grep -r restaurant` in the `technical` directory
```
./government/About_LSC/commission_report.txt:restaurant work, and day labor. See April Testimony at 16
./government/Media/Legal-aid_chief.txt:Koch owns the Eustis Pool Hall, a local landmark and restaurant,
./government/Media/Workers_aid_center.txt:primarily in the garment, construction, restaurant and domestic
./government/Media/Working_for_Free.txt:matched wits with the partners over lunch at an upscale restaurant.
./biomed/1471-2458-3-2.txt:          outside the home (such as workplace or restaurants). They
./911report/chapter-13.4.txt:                At the time of the February 1, 2000, restaurant encounter, Bin Don, a U.S. citizen,
./911report/chapter-5.txt:                his faith; for example, he specifically avoided restaurants that cooked with or
./911report/chapter-7.txt:                Bayoumi and Caysan Bin Don at a halal food restaurant on Venice Boulevard in Culver
./911report/chapter-7.txt:                the restaurant but did not specify the address. They did not like Los Angeles and
./911report/chapter-7.txt:                then left the restaurant and went their separate ways.
./911report/chapter-7.txt:                mosque is close to the restaurant and Bayoumi had visited it, and the surrounding
./911report/chapter-9.txt:                World restaurant on the 106th floor, from which calls had been made to the PAPD
./911report/chapter-9.txt:                been taking shelter in the restaurant and assisted them in evacuating. Up above, at
```
The `-r` command line option allows us to use `grep` recurssively meaning that grep will search through each subdirectory in the working directory. For example calling `grep -r restaurant` in the `technical` directory will return the each line that contains `restaurant` in all the files in the `technical` directory. The output list the path to each file from the working directory followed by the line in the file containing the content that was being searched for. This command line option would be useful when trying to search for the occurences of a certain piece of content when there are multiple subdirectories because calling `grep` without this option only searched in the working directory.
#### calling `grep -r FBI` in the `technical/government` directory
```
./Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt:Investigation (FBI) and create a successful Department of Homeland
./Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt:Success, GAO-02-886T (Washington, D.C.: June 25, 2002) and FBI
./Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt:major transformation efforts, like the FBI, the Internal Revenue
./Gen_Account_Office/Oct15-2001_d0224.txt:with the Federal Bureau of Investigation's (FBI) National
./Gen_Account_Office/Oct15-2001_d0224.txt:Cleveland FBI Field Office to build a better relationship
./Gen_Account_Office/Oct15-2001_d0224.txt:between the FBI and the private sector in addressing cyber and
./Gen_Account_Office/Oct15-2001_d0224.txt:which is an interagency center housed at the FBI, in conjunction
./Gen_Account_Office/Oct15-2001_d0224.txt:development of local chapters associated with each of the FBI's 56
./Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt:Investigation (FBI), the U.S. Marshals Service, the Department of
./Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt:Administration (TSA), the DOD, the FBI, and the CIA. Congress
./Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt:Reorganization FBI Reorganization: Initial
./Media/Raising_the_Bar.txt:FBI
```
The `-r` command line option allows us to use `grep` recurssively meaning that grep will search through each subdirectory in the working directory. For example calling `grep -r FBI` in the `technical/government` directory will only return the lines containing `FBI` in the `technical/government` directory because that was the directory the command was called from. The output list the path to each file from the working directory followed by the line in the file containing the content that was being searched for. This command line option would be useful when trying to search for the occurences of a certain piece of content when there are multiple subdirectories, and this example demonstrates how you can change the current directory so control where `grep` recurssively searches.
##### callling `grep -r restaurant --exclude-dir 911report` in `technical` directory
```
./government/About_LSC/commission_report.txt:restaurant work, and day labor. See April Testimony at 16
./government/Media/Legal-aid_chief.txt:Koch owns the Eustis Pool Hall, a local landmark and restaurant,
./government/Media/Workers_aid_center.txt:primarily in the garment, construction, restaurant and domestic
./government/Media/Working_for_Free.txt:matched wits with the partners over lunch at an upscale restaurant.
./biomed/1471-2458-3-2.txt:          outside the home (such as workplace or restaurants). They
```
The `--exclude-dir` command line option is used alongside the `-r` command line argument and it makes `grep` avoid the specified directory when searching recurssively. For example, callling `grep -r restaurant --exclude-dir 911report` doesn't return the lines that contain `restaurant` in the `911report` directory even thought their are lines in that directory that contain `restaurant`. This command line option would be useful for when you want to search through all the subdirectories, but want to exclude a certain directory and its subdirectories if it has any.
##### calling `grep -r FBI --exclude-dir Gen_Account_Office` in `technical/government` directory
```
./Media/Raising_the_Bar.txt:FBI
```
The `--exclude-dir` command line option is used alongside the `-r` command line argument and it makes `grep` avoid the specified directory when searching recurssively. For example, calling `grep -r FBI --exclude-dir Gen_Account_Office` in the `technical/government` directory doesn't return the lines that contain `FBI` in the `Gen_Account_Offices` directory. This command line option would be useful for when you want to search through all the subdirectories, but want to exclude a certain directory and avoid going through a certain set of data such as the `Gen_Account_Offices` information.
#### command-line option #3: `-n`,`--line-number` (found using `man grep`)
##### calling `grep -n pineapple  *.txt ` in the `technical/biomed` directory
```
1472-6882-1-10.txt:192:          antibiotics and the ananase enzyme (from the pineapple 
gb-2002-3-10-research0053.txt:439:          in pineapple (~70% to 
```
##### calling `grep --line-number funding CONFIG_STANDARDS.txt` in `technical/government/About_LSC` directory
```
41:state bar association, state IOLTA funding entity, staffed legal
90:LSC operates under a statutory mandate to make funding decisions
214:within the state facilitate efforts to secure new funding for, and
215:where appropriate allocate current funding to new projects and
316:funding?
```
#### command-line option #4: `-m`,`--max-count` (found using `man grep`)
##### calling `grep -m 5 911 chapter-9.txt` in the `technical/911report` directory
```
                Twin Towers. The 911 emergency call system was overwhelmed. The general evacuation
                (which was not monitored by a dispatcher).17 The NYPD also supervised the city's 911
                of emergency response. When a 911 call concerned a fire, it was transferred to FDNY
                which had a center in each of the five boroughs. All 911 calls concerning fire
            Civilians, Fire Safety Personnel, and 911 Calls
```
##### calling `grep --max-count 5 911 *.txt` in the `technical/911report` directory
```
chapter-13.5.txt:                received by civilians in the towers based on (1) calls to NYPD 911 from or
chapter-13.5.txt:                September 11, 2001 (hereafter "Commission analysis of 911/PAPD calls"). Everyone
chapter-13.5.txt:                Commission analysis of 911/PAPD calls; Civilian interview 17 (May 11, 2004);
chapter-13.5.txt:                analysis of 911/PAPD calls; Port Authority transcripts of recorded Port Authority
chapter-13.5.txt:            32. Commission analysis of 911/PAPD calls.
chapter-9.txt:                Twin Towers. The 911 emergency call system was overwhelmed. The general evacuation
chapter-9.txt:                (which was not monitored by a dispatcher).17 The NYPD also supervised the city's 911
chapter-9.txt:                of emergency response. When a 911 call concerned a fire, it was transferred to FDNY
chapter-9.txt:                which had a center in each of the five boroughs. All 911 calls concerning fire
chapter-9.txt:            Civilians, Fire Safety Personnel, and 911 Calls
```



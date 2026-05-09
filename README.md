## My Understanding of Comparator & Functional Interfaces (Java 8)

### Step 1: Functional Interface
- A functional interface is an interface which has exactly one abstract method.
- It can have multiple default and static methods.


### Step 2: Old Approach (Before Java 8)
- In olden days, we used anonymous inner classes to provide implementation for functional interfaces.


### Step 3: Java 8 Feature
- In Java 8, we have lambda expressions (easy notation).
- Lambda expressions are used to implement functional interfaces in a shorter way.


### Step 4: Comparator
- Comparator is a functional interface.
- Main method: `compare(T o1, T o2)`
- Used for custom sorting


### Step 5: Example (Student Class)
- Student has:
  - id
  - name
  - marks


### Step 6: Sorting using Comparator

List<Student> studentList = new ArrayList<Student>();

studentList.stream().sorted((s1, s2) -> s1.getMarks() - s2.getMarks()); 

### Step 7: Other Functional Interfaces
- Predicate → method: test() → returns boolean
- Consumer → method: accept() → performs action (no return)
- Function → method: apply() → takes input and returns output

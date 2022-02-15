# Why these classes should use C

## What this is
The purpose of this is to express the need that this curriculum has for exploration of these lower level ideas. By teaching these options, we are limiting the knowledge of future generations.

### **Python (near useless for 'principles')**
```python
me = "Finn"

def say_hi(name):
    print("Hello, " + name + "!")

say_hi(me)
```
Pros:
- Easy to understand for dummies
- Package manager is dope (PIP)
- Monty Python references in documentation
  
Cons: 
- Lists are so, so, so dumb
- Confusing type System
- Many bad practices
- Too abstact for people to actually learn things

At a glance, nothing seems wrong with Python. And for many lower level developers it seems like a dream come true. However, Python is dangerously bad practice for beginners. Not only does the 'easy' style promote confusing messages about how computers really work, but Python itself actively tries to prevent users from accessing some of the lower level functionality that should be import to a 'principles' class.

Look at the type system for example, which is almost completely concealed from the user. The Python compiler (which is written in C by the way), parses over user code and allocates memory based on context clues. This is extremely unsafe, and often leads to slow programs and inept users.

Note: As of Python v3.5 typing 'hints' have been introduced, AKA optional typing to help the compiler if your code is really slow. This doesn't change my point, because by default Python is still very insecure, and these 'type hints' are inconvenient and still don't accurately reflect realistic data structures and are not actually in the curriculum at all.

### *Example of Python 'hint'*
```python
def greeting(name: str) -> str:
    return 'Hello ' + name
```

Python also includes some risky features like single  quoted strings (see above), and non explicit character typing. Single quoted strings breed bad practices because (according to almost universal norm), they should only be employed for single characters.

On a more positive note, the best feauture of Python is PIP, its package manager. Python has a massive ecosystem of modules (Python libraries) that are easily accessible via PIP. This is by far my favorite feature of Python, and some languages even do it better.

Now for perhaps the worst feature in Python: Lists. Lists are an unholy mashup of three completely seperate data types (scalar, vector, and array) and exist purely as syntax sugar.

### *Example of Python 'list'*
```python
list1 = ["abc", 34, True, 40, "human"]

print(list1[0:2])

for i in list1:
    print(i)
```
```cmd
OUTPUT:

abc
34
True
40
human
["abc", 34, True, 40]
```

Traditionally, arrays are a collection of the SAME datatype with fixed lengths. This isn't Python re-inventing the wheel, instead python creates an hash map for EACH ENTRY in the list in order to represent its 'index' or its datatype. Recall, this is just abstraction. Ultimately, Python is built on C.

The only habits Python builds are bad ones, and teachers should steer clear of it for their curriculum. I do however believe that Python can be a useful tool for experienced developers who want to save time, it is just not acceptable for beginners.

### **Java (syntax sugar overdose)**
```java
public class Main {
    static void say_hi(String name) {
        System.out.println("Hello, " + name + "!");
    }

    public static void main(String[] args) {
        String me = "Finn";

        say_hi(me);
    }
}
```
Immediately, one might notice what Java gets better and worse than Python.

Better:
- Clear entry point for the compiler!
- Types actually exist!
- Introduces some more advanced ideas!

Worse:
- So many worthless abstractions
- Java classes are the stupidest thing since Python lists
- Everything is an object just like Python, except somehow worse
- Package manager options suck (I'm looking at you Maven)
### **C (why this is better)**
```c
#include <stdio.h>

void say_hi(char* name) {
    printf("Hello, %s!", name);
}

int main(void) {
    char[] me = "Finn";

    say_hi(me);

    return 0;
}
```
# BONNIE (assemBler-Operation iN-ram iNstruction compIlEr)
## A simple RAM-compiled embedded programming language that allows you to write friendly, simple usercode for C++ programs. Rather like Lua, don't you think?
### It literally compiles the BONNIE code to a const char* on the heap with valid memory instructions, then provides function pointers. Simple!

The easiest use-case, with Inline Bonnie:

```c++
#include <bonnie.hpp>

Bonnie bn {
    "codespace 'main'\n"
    "> println 'Hello'\n"
};
// Load a Bonnie inline. The code is simple, and rather like Intel Assembly with more tricks:
// In this case, it begins a codespace (literally a memory address that points to code),
// calls it "main" (the main codespace is automatically made the b.main, which is a BonnieFunction),
// and adds the instructions. Every operation starts with a ">",
// and every compilation guide ends with just a newline. Logic (if/else/elif, for/while) ends with ":".
// Everything you do must end with a newline, so single-line bonnie is impossible.

int main(){=
    bn.main.execute();
}
```

# nero
A small DSL extension to add syntax sugar to your tests

May 27, 2017
lilsweetcaligula

Hello, welcome, and thank you for taking your time
to look at my code.

This is my wrapper around Criterion that I call `nero`.
The whole point of it is providing syntactic sugar for
neater-looking tests. Or so I thought...

Eitherway, if you like it, you're free to use it with
your code without any burden. Just copy, paste, tweak
it if you like and enjoy.

I haven't had much time to write documentation, since I
was originally writing this for my own use. So if you
have any questions, feel free to PM me.

This is how you bundle it with your code:
- copy/paste all the code, demarcated by 
 "BEGIN `nero`-specific stuff", ending with
 "END `nero`-specific stuff", - to "Preloaded".

- copy/paste the lines demarcated by 
 "BEGIN `nero`-specific stuff", ending with
 "END `nero`-specific stuff", - to 
 "Example Test Cases"/"Test Cases",

There's an important caveat to using it though. Which is
that the following format must be obeyed for `nero` to
work properly:

```

Test(TEST_NAME, DESCRIPTION, .init = setup, .fini = finish) {
   describe("my super awesome function") {
       context("when passed a NULL argument") {
           it("is sad") {
               ...tests
           }
       }

       context("when passed a string") {
           it("is happy") {
               ...tests
           }
       }
   }
}

// where TEST_NAME is any valid identifier you choose as test name for Criterion.
// where DESCRIPTION is any valid identifier you choose as description for Criterion.
```

Best Regards, 
lilsweetcaligula

### Updates

17 June 2017
siebenschlaefer reported a problem with the variable `_` being marked 
as unused when using the elevated warning reporting level in a compiler.
Resolved by adding: `(void)_` to the increment expression in the 
for-block. Thank you very much for letting me know, siebenschlaefer!

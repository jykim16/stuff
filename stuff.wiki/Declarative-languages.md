## Declarative languages

### tl;dr 

In "imperative" programming, you specify **how** to get what you want.

In "declarative" programming, you specify **what** you want. You don't know or care _how_ it will happen.

### Examples of declarative languages

* HTML
* SQL
* ORM's
* Functional languages

### HTML is a language?

Well, HTML doesn't have control flow or overt data processing and it's not [Turing complete](https://simple.wikipedia.org/wiki/Turing_complete), so sure, it can be a stretch to call it a full-blown language. But there's a reason why the "L" in "HTML" stands for "Language", right? It's a markup language, yes, so it's a limited domain-specific language, but it is a formally parse-able way of expressing the semantic and visual structure of a document.

There's a **lot** of imperative logic hidden behind HTML5 tags such as `<video>` or [form field constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms_in_HTML#Constraint_Validation).

More broadly, the way that HTML is rendered (in conjunction with CSS) is [fantastically complex](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/). As a programmer, you enjoy the benefit of an enormous amount of programming logic that resides behind this declarative markup language. 

### How is that different from just using an app like Word? 

A declarative language is still a language. Even though Word can visually style your document in a way that similar to HTML... you don't programmatically parse a Word doc to produce its result. Instead, you manipulate a GUI. It isn't a language.

### SQL is declarative?

A SQL statement can look like it's specifying imperative logic... do exactly this, then that, then this other thing:

```
SELECT * FROM books WHERE author = "George R.R. Martin";
```

That kinda looks like imperative logic...?

However it's not. You're really specifying _what_ you are looking for (including the location(s) of what you are looking for). You are delegating to the SQL engine the exact details of _how_ it is looked up.

To take a simple case, for the same query, the SQL engine might decide to perform a full table scan or it might choose to use an index (assuming the presence of a relevant index). You might think it would always use an index if it were available, but for very small tables it might not choose to do so.

You can see the "query plan" for a given query by executing `EXPLAIN PLAN`. 

Here's an example:

```
Rows      Execution Plan
--------  ----------------------------------------------------
      12  SORT AGGREGATE
       2   SORT GROUP BY
   76563    NESTED LOOPS
   76575     NESTED LOOPS
      19      TABLE ACCESS FULL CN_PAYRUNS_ALL
   76570      TABLE ACCESS BY INDEX ROWID CN_POSTING_DETAILS_ALL
   76570       INDEX RANGE SCAN (object id 178321)
   76563     TABLE ACCESS BY INDEX ROWID CN_PAYMENT_WORKSHEETS_ALL
11432983      INDEX RANGE SCAN (object id 186024)
```

As you can see, that looks pretty different from a SQL query. The step-by-step logic of _how_ to fetch the data is different from what the programmer specified originally.


#### Wait, how is that different from what an interpreter does?

You might say that any compiler or interpreter translates from your higher-level, imperative instructions into lower-level instructions that are harder for you to write or understand. Abstracting away that low-level complexity has been key to increasing programmer productivity for a long time. So -- how is this different from SQL, say?

The difference is that a declarative language gives you *no way* to write in the imperative style. You aren't asking the interpreter or engine to convert your imperative instructions into a lower-level imperative instructions. You're asking the engine to translate your declarations of what you want produced into _whatever happens_ to produce that output. 

### Functional languages?

Yes, functional languages can be considered to bea subset of declarative languages. 

In functional languages, you specify the output that you want from each function. You don't care about the implementation of those functions, as long as they reliably produce the same output for a given input. In that sense, functions are black boxes. 

As such, the implementation can be swapped out by the compiler/interpreter without you caring. 

This is similar to how you don't really care how SELECT is implemented in SQL, or how `<video>` is implemented in HTML5.


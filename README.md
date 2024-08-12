# Versus JS

There is a general conversation around jQuery that it is a "legacy" tool that has long since been replaced with ES6. This conversation seems to focus on features like ```document.querySelector()``` as "replacements" for what jQuery does. Many state that jQuery can be replaced by "four lines of utility code". 

Unfortunately, some believe these conversations appear to be poorly thought out. Most arguments ignore the two key features that make jQuery valuable:

- The ability to apply operations across many elements found by the selector
- The ability to chain these operations, leading to dense code

This project attempts to pit jQuery against ES6 to analyze if there is any merits to the arguments for or against jQuery.

## Approach

Three implementations of a simplified paged content screen have been created. One using jQuery and two others using ES6.

## Findings

| Technology | Total LOC | Javascript LOC | File Size | Total Download Size |
| ---------- | --------- | -------------- | --------- | ------------------- |
| jQuery     | 67        | 45             | 2,289 bytes | 72,553 bytes      |
| ES6        | 115       | 94             | 3,567 bytes | 3,567 bytes       |
| ES6 v2     | 46        | 24             | 1,620 bytes | 1,620 bytes       |

Using ES6 over jquery in this case results in 42% less Javascript and 98% smaller file size. The ES6 code achieves this through a much higher code density and using the latest ES6 features, as well as ES6's powerful array methods and Dom api functions.

ES6 is a clear winner in total download size, and in execution with jquery appearing with much more extraneous and superflous code than necessary.

## Analysis

While it might be tempting to give ES6 the win due to the smaller download, it is important to understand that this is a micro-benchmark. In real world deployments, the amount of Javascript used on an interactive site will quickly overwhelm the 70KB required by jQuery. This is especially meaningful for multipage applications where the jQuery library will be cached once and then continuously reused across numerous page downloads. SPAs tend to prefer larger downloads up-front, making the size something of a non-issue for performance.

More importantly, we know that more code means longer development times. As documented by Fred Brooks in his 1975 work *The Mythical Man Month*, the number of lines of code produced over a period of time tends to remain consistent.

## Conclusions

While this is a simple case, this is a strong case for ditching jquery and using javascript and especially making good design patterns within javascript and its dom api.

With that said, it is of importance that this is merely one example. An ideal comparison would be at scale in real-world applications. While my own experience lends credence to the idea that jQuery scales over ES6, this does not outright prove that. Thus I invite others to share their data and examples to see if we can find cases that demonstrate the opposite conclusions. 

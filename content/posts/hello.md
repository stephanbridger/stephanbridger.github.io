---
title: "Hello World"
date: 2025-08-02
Description: "A Hello World test metadescription"
tags: ["hugo", "blogging", "tutorial"]
---
## Heading II

Lorem ipsum dolor sit amet[^1], consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur, vel illum qui dolorem eum fugiat quo voluptas nulla pariatur?

### Heading III

Here's some LaTeX: 

$$
a_{0} + a_{0}a_{1} + a_{0}a_{1}a_{2} + \cdots + a_{0}a_{1}a_{2} \cdots a_{n} = \cfrac{a_{0}}{1 - \cfrac{a_{1}}{1 + a_{1} - \cfrac{a_{2}}{1 + a_{2} - \cfrac{\ddots}{\ddots \cfrac{a_{n-1}}{1 + a_{n-1} - \cfrac{a_{n}}{1 + a_{n}}}}}}}
$$


```lisp
(defun cont-frac (n d k)
  (labels ((iter (i result)
             (if (= i 0)
                 result
                 (iter (- i 1) (/ (funcall n i) (+ (funcall d i) result)))))) 
    (iter k 0))) 

(format t "~a" (cont-frac (lambda (i) 1.0) (lambda (i) 1.0) 10))
```

What if we also wanted some in-line LateX? We could write an inline equation: \(E = mc^2\). That's possible with `\(` delimiters. Or perhaps some inline code? Well, that is possible too, by using single backticks. Consider the above Lisp magic. We can explain how it works and use backticks to highlight its parts.

This Lisp code defines a function `cont-frac`, which computes a continued fraction. The function uses the helper `iter`, defined inside `cont-frac` using `labels` for local recursion to iterate and calculate the fraction.

We write a `lambda` function to handle the numerator and denominator values, which are then passed back as functions rather than values. The `iter` function is where the magic happens. It keeps calling itself with a reduced iteration count `(i - 1)`, counting down until `i` has reached `0`. And at each step, it computes a fraction. 

The program terminates and outputs our final value when the lamdba's index hits `0`. Basically the Lisp interpreter is being told, "hey, simulate 10 iterations of `1 / (1 + 1 / (1 + 1 /...))`" by the lambda function.

{{< img 
    url="/images/catherine.jpg" 
    class="centered-image"
    lightbox="true"
    scale="60"
    caption="Saint Catherine of Siena"
>}}

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,[^2] quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.[^3] Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

[^1]: This is the first footnote. You can put any Markdown content here, including **bold** or _italic_ text.
[^2]: You better believe this is the second footnote, referencing something mildly 
relevant. 
[^3]: And this is the third and final footnote, perhaps linking to [an external 
resource](https://example.com).



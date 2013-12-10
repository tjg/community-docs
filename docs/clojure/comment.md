---
layout: docs
title: Comment
permalink: /docs/clojure/comment/
level: easy
author: tjg
---

A comment tells Clojure to ignore some text or code. It can serve as
explanation, or to "hide" code from Clojure which you don't wish to
execute.

Semicolons are one way to start a comment.

```clojure
(+ 1 2)  ; This is a comment.

;; This is also a comment. For some reason, people like to use 2
;; semicolons for comments which take up full lines; but it's not
;; necessary.

"But this ; won't start a comment, because it's in a string."
```

A `(comment)` block is another way to prevent code from being
executed. The `comment` operator returns `nil` and doesn't cause code
inside it to be executed.

```clojure
(comment
  (System/exit 0))
```

Finally, if you precede one piece of code with #_, Clojure acts like
it didn't actually read it.

```clojure
[1 #_2 3]
=> [1 3]

[1 #_(+ 2 2) 3]
=> [1 3]
```
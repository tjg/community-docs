---
layout: docs
title: Comment
permalink: /docs/clojure/comment/
level: easy
author: tjg
---

A comment tells Clojure to ignore some text. It can serve as
documentation, or to "hide" some code from Clojure which you don't
feel is ready to be executed.

Semicolons start comments.

```clojure
;; This is a comment. Traditionally, people like to use 2 ;'s for
;; comments which take up full lines.

(+ 1 2)  ; People usually use 1 ; for comments sharing a line with code.

"But this ; won't start a comment, because it's in a string."
```

You can also surround code in a `(comment)` block. The `comment`
operator merely returns `nil`, no matter what code is inside.

```clojure
(comment
  (System/exit 0))
```

Finally, if you precede something with #_, Clojure acts like it never
read it.

```clojure
[1 #_2 3]
=> [1 3]

[1 #_(+ 1 2 3 4) 3]
=> [1 3]
```
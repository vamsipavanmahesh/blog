---
layout: post
title:  "Some ruby array quirks you may not know about"
date:   2020-10-28 11:39:40 +0530
categories: ruby
---

#### Array discards the splatted nil:

```ruby
irb > [1,2,3,*nil]
# => [1, 2, 3]
```
This knowledge comes in handy when you are splatting a variable which is intended to be an array, but returns `nil` as shown below:

```ruby
irb > foo = nil
=> nil
irb > [1,2,3,*foo]
=> [1, 2, 3]
```
#### Array treats empty expressions as nil:

```ruby
irb(main):005:0> [1,2,3,()]
=> [1, 2, 3, nil]
```

I honestly, don't know where this can be useful. But it's good to know this stuff right?

#### Fun Fact:

Empty expressions return `nil`, regardless of the context of arrays:

```ruby
irb > ()
=> nil
```
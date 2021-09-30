---
title: "Using GDB to debug rust code in neovim"
date: 2021-09-30
draft: false
---

I would love to start by giving a reference to this 
[great blog](https://togglebit.io/posts/debugging-rust-in-vim/).

It outlines only the necessary and **just works**.

However, one issue I faced during using `gdb` was figuring out how to display 
the value of different variables especially if they are vectors or slices.

For example, if an array of the following type `&[&str]` of length 10:
```dark
ins(gdb) print old
$23 = &[&str] {data_ptr: 0x555555626ba0, length: 15}
```

and I want to see the content of such an array. I have to use the following syntax:
```dark
print *old@10
```

I hope this helps out somebody.

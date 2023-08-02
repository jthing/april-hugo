---
title: "ANNAPL"
date: 2023-08-02T00:00:00+02:00
draft: false
---

## Artificial Neural Nets in APL {#artificial-neural-nets-in-apl}

[ANNAPL](<https://github.com/rodrigogiraoserrao/ANNAPL>) is a github cite with a example
neural net implementation in APL. In particular notice mnistdata.rar which is the
handwritten character data in 128x128 pixel gray-format encoded as a compressed CSV file.
I will need this data as the original data cite
[yann.lecun.com](<https://yann.lecun.com/exdb/mnist/>) is now password protected. Not sure
why, but I suspect the traffic given the recent influx in DNN's has become to great for
his server to handle.

His code uses :For :InEach several times. This is not implemented in April. I will try to
use the nest (⍣) operator instead. f⍣5 x ⟹ f(f(f(f(f x)))) so actionFn∘_F⍣≢layers or
something along those lines.

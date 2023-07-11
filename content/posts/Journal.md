---
title: "Journal"
date: 2023-02-23T00:00:00+01:00
draft: false
---

## 2023 {#2023}


### 2023-02 februar {#2023-02-februar}


#### 2023-02-23 torsdag {#2023-02-23-torsdag}

<!--list-separator-->

-  11:17  - april GPU <span class="tag"><span class="journal">journal</span></span>

    Research ways of letting APL run on a GPU. In paricular a april
    extension.
    (April is a APL library for Common Lisp wich extestions for Dylog APL
    but relies on CL for IO.)

    [APL to GPU slides](https://elsman.com/pdf/Dyalog17.pdf) for discussion on dylogs attempts.
    [Rapids](https://developer.nvidia.com/rapids) is a library for doing all calculation on the GPU.
    It contains cudf a library which is a drop in replacement for pandas
    but which performs the operation on the GPU. Pandas is in turn based
    on the J language which is derived from APL. It should thus be
    relatily easy to translate APLt to cudf calls and the run them on the
    GPU. To run on a GPU types must be known and this must be infered
    before the code can be compiled.


# Table of Contents

1.  [Codility](#orgdb38a81)
    1.  [Luyện thuật toán cùng Codility](#org820bbdb)
        1.  [Codility là gì](#orge64191c)
        2.  [Thuật toán và cách đo hiệu năng](#org79f5c13)
        3.  [Những điểu cần chú ý](#org983c1e1)
        4.  [Solution Codility](#orgf05566b)
        5.  [Viết UT](#orgc0744a0)
        6.  [Hướng giải quyết](#org8e5f391)
        7.  [Pseudo code](#org4d6a26f)
        8.  [Implement](#org506331c)
        9.  [Chạy UT](#orgaa0521c)
        10. [Các bước phân tích](#org21eb932)

&#x2014;
description: Những điểu cần biết về Codility
&#x2014;


<a id="orgdb38a81"></a>

# Codility


<a id="org820bbdb"></a>

## Luyện thuật toán cùng Codility


<a id="orge64191c"></a>

### Codility là gì


<a id="org79f5c13"></a>

### Thuật toán và cách đo hiệu năng


<a id="org983c1e1"></a>

### Những điểu cần chú ý


<a id="orgf05566b"></a>

### Solution Codility


<a id="orgc0744a0"></a>

### Viết UT


<a id="org8e5f391"></a>

### Hướng giải quyết


<a id="org4d6a26f"></a>

### Pseudo code


<a id="org506331c"></a>

### Implement


<a id="orgaa0521c"></a>

### Chạy UT


<a id="org21eb932"></a>

### Các bước phân tích

-   Problem: Peaks
-   PT:
    l = arr.length;
    getFactors l => [f1, &#x2026;.f2]
    peaks array => [false, true, &#x2026;.true, false];
    for each factor f1 (f1 > 1) => we have l / f1 blocks we can skip 1
    we have l / f1 blocks =>
    check if each block has a peak
    how to check for a slice (i, j) contains a block ?
    1.  loop i => j if peaks[k] = true => O(n)
    2.  use memorize to get O(i)


# Codility

## Table of Contents

1. [Codility](./#orgdb38a81)
   1. [Luyện thuật toán cùng Codility](./#org820bbdb)
      1. [Codility là gì](./#orge64191c)
      2. [Thuật toán và cách đo hiệu năng](./#org79f5c13)
      3. [Những điểu cần chú ý](./#org983c1e1)
      4. [Solution Codility](./#orgf05566b)
      5. [Viết UT](./#orgc0744a0)
      6. [Hướng giải quyết](./#org8e5f391)
      7. [Pseudo code](./#org4d6a26f)
      8. [Implement](./#org506331c)
      9. [Chạy UT](./#orgaa0521c)
      10. [Các bước phân tích](./#org21eb932)

— description: Những điểu cần biết về Codility —

## Codility

### Luyện thuật toán cùng Codility

#### Codility là gì

#### Thuật toán và cách đo hiệu năng

#### Những điểu cần chú ý

#### Solution Codility

#### Viết UT

#### Hướng giải quyết

#### Pseudo code

#### Implement

#### Chạy UT

#### Các bước phân tích

* Problem: Peaks
* PT:

  l = arr.length;

  getFactors l =&gt; \[f1, ….f2\]

  peaks array =&gt; \[false, true, ….true, false\];

  for each factor f1 \(f1 &gt; 1\) =&gt; we have l / f1 blocks we can skip 1

  we have l / f1 blocks =&gt;

  check if each block has a peak

  how to check for a slice \(i, j\) contains a block ?

  1. loop i =&gt; j if peaks\[k\] = true =&gt; O\(n\)
  2. use memorize to get O\(i\)


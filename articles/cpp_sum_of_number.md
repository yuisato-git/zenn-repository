---
title: "【C++】数値の各桁の和の求め方"
emoji: "☕️"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["cpp", "競プロ"]
published: true
---

## コード

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
  // 入力
  int n;
  cin >> n;

  // 各桁の和
  int sum = 0;
  while (n > 0) {
    sum += n % 10;
    n /= 10;
  }

  cout << sum << endl;
}
```

## 出力結果

```cpp
340
7

581
14

1
1
```

## 解説

数値を 10 で割った余りは 1 の位を返すので、取得した値以外の数字になるよう 10 で割って更新します。

例) 数値「643」の場合

```cpp
643 % 10 = 3   // 👈 1の位
643 / 10 = 64

64 % 10 = 4　   // 👈 10の位
64 / 10 = 6

6 % 10 = 6 　  　// 👈 100の位
```

そして一桁になった場合は 10 で割ると 0 になるので、ループを抜けて処理を終えます。

---
description: 詳細については、「コンパイラエラー C2357」を参照してください。
title: コンパイラ エラー C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: a58317fc4706d6385d3753a434c8e4fd80dc79b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276739"
---
# <a name="compiler-error-c2357"></a>コンパイラ エラー C2357

' identifier ': 型 ' type ' の関数でなければなりません

コード `atexit` で、コンパイラによって内部的に宣言されたバージョンと一致しないバージョンの関数が宣言されています。 次のように宣言 `atexit` します。

```
int __cdecl atexit(void (__cdecl *)());
```

詳細については、「 [init_seg](../../preprocessor/init-seg.md)」を参照してください。

次の例では、C2357 が生成されます。

```cpp
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```

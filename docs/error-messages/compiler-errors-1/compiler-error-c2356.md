---
description: 詳細については、「コンパイラエラー C2356」を参照してください。
title: コンパイラ エラー C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: c0e2d179bb41e6cbae674d92976674ab90f05c0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328324"
---
# <a name="compiler-error-c2356"></a>コンパイラ エラー C2356

翻訳単位で初期化セグメントを変更することはできません

次の原因が考えられます。

- `#pragma init_seg` 前にセグメント初期化コードを付ける

- `#pragma init_seg` 前に別の `#pragma init_seg`

解決するには、セグメントの初期化コードをモジュールの先頭に移動します。 複数の領域を初期化する必要がある場合は、それらを別々のモジュールに移動します。

次の例では、C2356 が生成されます。

```cpp
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```

---
title: コンパイラ エラー C3368
ms.date: 11/04/2016
f1_keywords:
- C3368
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
ms.openlocfilehash: f027e2707dc677d93567f91307e9dcfcb8dd682f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582313"
---
# <a name="compiler-error-c3368"></a>コンパイラ エラー C3368

'function declaration' : IDL の呼び出し規則が正しくありません

.idl ファイル内で使用できる呼び出し規則は [__stdcall](../../cpp/stdcall.md) または [__cdecl](../../cpp/cdecl.md) のみです。

次の例では C3368 が生成されます。

```
// C3368.cpp
// processor: x86
[idl_module(name="Name", dllname="Some.dll")];

[idl_module(name="Name")]
int __fastcall f1();   // C3368
```
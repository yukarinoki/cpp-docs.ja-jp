---
title: コンパイラ エラー C3368
ms.date: 11/04/2016
f1_keywords:
- C3368
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
ms.openlocfilehash: f027e2707dc677d93567f91307e9dcfcb8dd682f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300519"
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
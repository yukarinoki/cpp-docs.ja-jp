---
title: コンパイラ エラー C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 4356182758398fa7ed1ec6a069affa4bb99ace1a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188221"
---
# <a name="compiler-error-c2341"></a>コンパイラ エラー C2341

'section name' : segment must be defined using #pragma data_seg, code_seg or section prior to use

[割り当てる](../../cpp/allocate.md)ステートメントによって定義されていないセグメントを参照して[code_seg](../../preprocessor/code-seg.md)、 [data_seg](../../preprocessor/data-seg.md)、または[セクション](../../preprocessor/section.md)プラグマ。

次の例では、C2341 が生成されます。

```
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

考えられる解決方法:

```
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```
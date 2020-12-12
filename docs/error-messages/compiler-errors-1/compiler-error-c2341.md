---
description: 詳細については、「コンパイラエラー C2341」を参照してください。
title: コンパイラ エラー C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 47869b6534664358fa80a3ace89fc44fdceefb08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234788"
---
# <a name="compiler-error-c2341"></a>コンパイラ エラー C2341

' section name ': セグメントは、使用する前に #pragma data_seg、code_seg またはセクションを使用して定義する必要があります

[Allocate](../../cpp/allocate.md)ステートメントが、 [code_seg](../../preprocessor/code-seg.md)、 [data_seg](../../preprocessor/data-seg.md)、または[section](../../preprocessor/section.md)プラグマによってまだ定義されていないセグメントを参照しています。

次の例では、C2341 が生成されます。

```cpp
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

考えられる解決策:

```cpp
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```

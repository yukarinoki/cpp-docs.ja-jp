---
description: 詳細については、「コンパイラエラー C2718」を参照してください。
title: コンパイラエラー C2718
ms.date: 11/04/2016
f1_keywords:
- C2718
helpviewer_keywords:
- C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
ms.openlocfilehash: ab0ddd8f5afa8cc72259f527d0bb8731fa4e9a5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320786"
---
# <a name="compiler-error-c2718"></a>コンパイラエラー C2718

' parameter ': __declspec (align (' # ')) を持つ実際のパラメーターは配置されません

[Align](../../cpp/align-cpp.md) **`__declspec`** 修飾子は、関数パラメーターでは許可されていません。

次の例では、C2718 が生成されます。

```cpp
// C2718.cpp
typedef struct __declspec(align(32)) AlignedStruct  {
   int i;
} AlignedStruct;

void f2(int i, ...);

void f4() {
   AlignedStruct as;

   f2(0, as);   // C2718, actual parameter is aligned
}
```

---
description: 詳細については、「コンパイラエラー C3196」を参照してください。
title: コンパイラエラー C3196
ms.date: 11/04/2016
f1_keywords:
- C3196
helpviewer_keywords:
- C3196
ms.assetid: d9c38a13-191d-472d-aa2b-f61a6459d16c
ms.openlocfilehash: 02ace9096754548a6629d1a5b5a71060a847da06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241873"
---
# <a name="compiler-error-c3196"></a>コンパイラエラー C3196

' keyword ': 複数回使用されています

キーワードが複数回使用されました。

次の例では、C3196 が生成されます。

```cpp
// C3196.cpp
// compile with: /clr
ref struct R abstract abstract {};   // C3196
ref struct S abstract {};   // OK
```

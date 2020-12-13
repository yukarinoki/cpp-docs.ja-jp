---
description: 詳細については、「コンパイラエラー C2861」を参照してください。
title: コンパイラ エラー C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: 82a4ed7d4b157bc141e9d437fa0f1d575759b48e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151126"
---
# <a name="compiler-error-c2861"></a>コンパイラ エラー C2861

' function name ': インターフェイスメンバー関数を定義することはできません

コンパイラにより、インターフェイスキーワードが検出されたか、または構造体がインターフェイスとして推測されましたが、メンバー関数の定義が見つかりました。  インターフェイスにメンバー関数の定義を含めることはできません。

## <a name="example"></a>例

次の例では、C2861 が生成されます。

```cpp
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861
```

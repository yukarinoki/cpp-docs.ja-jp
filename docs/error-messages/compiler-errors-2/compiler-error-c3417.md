---
description: 詳細については、「コンパイラエラー C3417」を参照してください。
title: コンパイラ エラー C3417
ms.date: 11/04/2016
f1_keywords:
- C3417
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
ms.openlocfilehash: d51985f619c436a1dfd6af06b97c72c3d06c7967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321898"
---
# <a name="compiler-error-c3417"></a>コンパイラ エラー C3417

' member ': 値型は、ユーザー定義の特殊メンバー関数を含むことはできません

値型には、既定のインスタンスコンストラクター、デストラクター、コピーコンストラクターなどの関数を含めることはできません。

次の例では、C3517 が生成されます。

```cpp
// C3417.cpp
// compile with: /clr /c
value class VC {
   VC(){}   // C3417

   // OK
   static VC(){}
   VC(int i){}
};
```

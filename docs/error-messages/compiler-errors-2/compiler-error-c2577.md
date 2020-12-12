---
description: 詳細については、「コンパイラエラー C2577」を参照してください。
title: コンパイラ エラー C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 9e54791070401f334a4dc0650ca2b1bcee5f32a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208854"
---
# <a name="compiler-error-c2577"></a>コンパイラ エラー C2577

' member ': デストラクターまたはファイナライザーは戻り値の型を持つことはできません

デストラクターまたはファイナライザーは、 **`void`** または他の型の値を返すことはできません。 **`return`** デストラクター定義からステートメントを削除します。

## <a name="example"></a>例

次の例では、C2577 が生成されます。

```cpp
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```

---
title: コンパイラ エラー C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 0a7c711fa399c1bf31bc9de61f0b77ad19172a73
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206914"
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

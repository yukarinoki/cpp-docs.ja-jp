---
title: コンパイラ エラー C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: 6c6451d31da2bb708d3f233225be713981b062e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406757"
---
# <a name="compiler-error-c3069"></a>コンパイラ エラー C3069

'operator': 列挙型には使用できません

演算子は CLR 列挙体ではサポートされていません。  詳細については、「[方法 :定義および使用で列挙型C++/CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C3069 が生成されます。

```
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```
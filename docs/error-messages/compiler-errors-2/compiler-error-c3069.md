---
description: 詳細については、「コンパイラエラー C3069」を参照してください。
title: コンパイラ エラー C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: cc56ded4f14e137b9f5bf28681fb319a650f363a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341140"
---
# <a name="compiler-error-c3069"></a>コンパイラ エラー C3069

'operator': 列挙型には使用できません

演算子は CLR 列挙体ではサポートされていません。  詳細については、「 [方法: C++/cli で列挙型を定義および使用する](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C3069 が生成されます。

```cpp
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

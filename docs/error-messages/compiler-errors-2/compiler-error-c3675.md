---
description: 詳細については、「コンパイラエラー C3675」を参照してください。
title: コンパイラ エラー C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: 0e8ea8d3450cd7a145e596f7122a5d2cbb31c5fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228743"
---
# <a name="compiler-error-c3675"></a>コンパイラ エラー C3675

' function ': ' property ' が定義されているため、予約されています

単純なプロパティを宣言すると、コンパイラは get アクセサーメソッドと set アクセサーメソッドを生成し、これらの名前はプログラムのスコープ内に存在します。  コンパイラによって生成される名前は、get_ を付加し、プロパティ名に set_ することによって形成されます。  そのため、コンパイラによって生成されたアクセサーと同じ名前の関数を宣言することはできません。

詳細については、「 [property](../../extensions/property-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C3675 が生成されます。

```cpp
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```

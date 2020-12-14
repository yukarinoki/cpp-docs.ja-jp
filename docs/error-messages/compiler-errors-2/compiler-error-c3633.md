---
description: 詳細については、「コンパイラエラー C3633」を参照してください。
title: コンパイラ エラー C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: caf89e2297bb4e9d62be76699b153f013095fa34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239260"
---
# <a name="compiler-error-c3633"></a>コンパイラ エラー C3633

' member ' をマネージド ' type ' のメンバーとして定義することはできません

CLR 参照クラスのデータメンバーを非 POD C++ 型にすることはできません。  CLR 型では、POD ネイティブ型のみをインスタンス化できます。  たとえば、ポッド型にコピーコンストラクターまたは代入演算子を含めることはできません。

## <a name="example"></a>例

次の例では、C3633 が生成されます。

```cpp
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```

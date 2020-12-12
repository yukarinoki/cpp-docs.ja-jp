---
description: '詳細情報: コンパイラの警告 (レベル 3) C4522'
title: コンパイラの警告 (レベル 3) C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: 8663bf6ea70edd6612fd3d124989f6e657185947
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257967"
---
# <a name="compiler-warning-level-3-c4522"></a>コンパイラの警告 (レベル 3) C4522

' class ': 複数の代入演算子が指定されています。

クラスには、1つの型の複数の代入演算子があります。 この警告は情報提供を目的としています。コンストラクターは、プログラムで呼び出すことができます。

この警告を非表示にするには、 [warning](../../preprocessor/warning.md) プラグマを使用します。

## <a name="example"></a>例

次の例では、C4522 が生成されます。

```cpp
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```

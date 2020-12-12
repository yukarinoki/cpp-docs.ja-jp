---
description: 詳細については、「コンパイラエラー C2893」を参照してください。
title: コンパイラ エラー C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: 42e31327096a539feeb691c698b52f57ecb615a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278260"
---
# <a name="compiler-error-c2893"></a>コンパイラ エラー C2893

関数テンプレート ' template name ' を特殊化できませんでした

コンパイラは関数テンプレートを特殊化できませんでした。 このエラーには多くの原因が考えられます。

一般に、C2893 エラーを解決するには、関数のシグネチャを確認し、すべての型をインスタンス化できるようにします。

## <a name="example"></a>例

`f`のテンプレートパラメーター `T` はであると推測されますが `std::map<int,int>` 、 `std::map<int,int>` メンバーはありません `data_type` (を `T::data_type` 使用してインスタンス化することはできません)。そのため、 `T = std::map<int,int>` C2893 が発生します。 次の例では、C2893 が生成されます。

```cpp
// C2893.cpp
// compile with: /c /EHsc
#include<map>
using namespace std;
class MyClass {};

template<class T>
inline typename T::data_type
// try the following line instead
// inline typename  T::mapped_type
f(T const& p1, MyClass const& p2);

template<class T>
void bar(T const& p1) {
    MyClass r;
    f(p1,r);   // C2893
}

int main() {
   map<int,int> m;
   bar(m);
}
```

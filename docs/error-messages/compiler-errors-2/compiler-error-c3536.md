---
title: コンパイラ エラー C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: 2380a9d42525cfb662fa014b89751d6dc8b9f192
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508247"
---
# <a name="compiler-error-c3536"></a>コンパイラ エラー C3536

' symbol ': 初期化する前に使用することはできません

指定されたシンボルを初期化する前に使用することはできません。 実際には、変数はその変数自体を初期化するために使用できないことを意味します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 変数をそれ自体で初期化しないでください。

## <a name="example"></a>例

次の例では、各変数がそれ自体で初期化されるため、C3536 が生成されます。

```cpp
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-cpp.md)

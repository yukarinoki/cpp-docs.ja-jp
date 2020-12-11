---
description: 詳細については、「コンパイラエラー C3536」を参照してください。
title: コンパイラ エラー C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: 62bd8bb75adfbf0e21f150f4240bb5f4011f6382
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112506"
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

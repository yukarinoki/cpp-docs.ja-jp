---
title: コンパイル エラー C3487 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3487
dev_langs:
- C++
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acd0dad31a565b9e75741e3a66a5d48dfedec69f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087111"
---
# <a name="compiler-error-c3487"></a>コンパイル エラー C3487

'return type': すべての return 式で同じ型を推測する必要があります: 以前は 'return type' でした。

ラムダでは、1 つの return ステートメントを含む場合を除き、戻り値の型を指定する必要があります。 ラムダに複数の return ステートメントが含まれる場合は、すべて同じ型である必要があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- ラムダの後続の戻り値の型を指定します。 ラムダからのすべての戻り値が同じ型であるか、または戻り値の型に暗黙的に変換できることを確認します。

## <a name="example"></a>例

次の例では、ラムダの戻り値の型が一致しないため、C3487 が生成されます。

```
// C3487.cpp
// Compile by using: cl /c /W4 C3487.cpp

int* test(int* pi) {
   // To fix the error, uncomment the trailing return type below
   auto odd_pointer = [=]() /* -> int* */ {
      if (*pi % 2)
         return pi;
      return nullptr; // C3487 - nullptr is not an int* type
   };
   return odd_pointer();
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
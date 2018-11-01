---
title: コンパイラ エラー C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: c0075bf0e3749966a5e5b9fcd775b5d73171bf17
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599421"
---
# <a name="compiler-error-c3496"></a>コンパイラ エラー C3496

'this' は常に値によってキャプチャされます。'&' は無視されました

参照で`this` ポインターをキャプチャすることはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 値で `this` ポインターをキャプチャします。

## <a name="example"></a>例

次の例では、 `this` ポインターへの参照がラムダ式のキャプチャ リストにあるため、C3496 が生成されます。

```
// C3496.cpp
// compile with: /c

class C
{
   void f()
   {
      [&this] {}(); // C3496
   }
};
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
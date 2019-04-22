---
title: コンパイラ エラー C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 025498f3fe244916cd0a06e36feee6fdb532acc6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026697"
---
# <a name="compiler-error-c3496"></a>コンパイラ エラー C3496

'this' は常に値によってキャプチャされます。'&' は無視されました

参照で `this` ポインターをキャプチャすることはできません。

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
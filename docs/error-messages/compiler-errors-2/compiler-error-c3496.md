---
title: コンパイラ エラー C3496 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ec4602e6a0061f5eb750ab29587209a6c97985d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062294"
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
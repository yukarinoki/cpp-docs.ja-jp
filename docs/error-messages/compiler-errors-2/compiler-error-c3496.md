---
description: 詳細については、「コンパイラエラー C3496」を参照してください。
title: コンパイラ エラー C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: dc3160e1007b65b70ea952aeaee3c77ba8ab21e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315518"
---
# <a name="compiler-error-c3496"></a>コンパイラ エラー C3496

'this' は常に値によってキャプチャされます。'&' は無視されました

参照でポインターをキャプチャすることはできません **`this`** 。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- ポインターを **`this`** 値でキャプチャします。

## <a name="example"></a>例

次の例では、ポインターへの参照が **`this`** ラムダ式のキャプチャリストにあるため、C3496 が生成されます。

```cpp
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

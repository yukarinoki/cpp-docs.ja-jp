---
title: コンパイラ エラー C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 993d391f28a59afc8926748f2e6f34ab441657dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228857"
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

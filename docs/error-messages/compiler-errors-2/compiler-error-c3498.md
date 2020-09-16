---
title: コンパイラ エラー C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: f1b978a585f3404cd3a881f25d6ef6a0f66b212d
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686156"
---
# <a name="compiler-error-c3498"></a>コンパイラ エラー C3498

' var ': マネージまたは WinRTtype の変数をキャプチャすることはできません

ラムダで、マネージド型または Windows ランタイム型を持つ変数をキャプチャすることはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- マネージド変数または Windows ランタイム変数をラムダ式のパラメーター リストに渡します。

## <a name="examples"></a>例

次の例では、マネージド型を持つ変数がラムダ式のキャプチャ リストに表示されるため、C3498 が生成されます。

```cpp
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

次の例では、マネージド型の変数 `s` をラムダ式のパラメーター リストに渡すことにより、C3498 を解決します。

```cpp
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)

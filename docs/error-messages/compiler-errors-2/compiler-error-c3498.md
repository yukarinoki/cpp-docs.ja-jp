---
description: 詳細については、「コンパイラエラー C3498」を参照してください。
title: コンパイラ エラー C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: f4d4ccb67494eb2d2cab499c210d360415fa9779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113102"
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

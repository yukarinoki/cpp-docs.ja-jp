---
title: コンパイラ エラー C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: 463e210e5a1ac5eb6d197062ed8921f9bbae4ad2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037884"
---
# <a name="compiler-error-c3498"></a>コンパイラ エラー C3498

'var': 変数を持つマネージまたは WinRTtype をキャプチャすることはできません

ラムダで、マネージド型または Windows ランタイム型を持つ変数をキャプチャすることはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- マネージド変数または Windows ランタイム変数をラムダ式のパラメーター リストに渡します。

## <a name="example"></a>例

次の例では、マネージド型を持つ変数がラムダ式のキャプチャ リストに表示されるため、C3498 が生成されます。

```
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

## <a name="example"></a>例

次の例では、マネージド型の変数 `s` をラムダ式のパラメーター リストに渡すことにより、C3498 を解決します。

```
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
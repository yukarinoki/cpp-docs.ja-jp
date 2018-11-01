---
title: コンパイラ エラー C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: ca9e2d272a5e9ab8fd69094bc1633dbd6ea2c3e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624696"
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
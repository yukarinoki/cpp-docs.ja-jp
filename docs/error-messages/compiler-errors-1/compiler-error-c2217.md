---
title: コンパイラ エラー C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: b033d95b127a45451a776cdc336ea7d2649d3716
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209748"
---
# <a name="compiler-error-c2217"></a>コンパイラ エラー C2217

' attribute1 ' には ' attribute2 ' が必要です

最初の関数属性には2番目の属性が必要です。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. Interrupt ( `__interrupt` ) 関数がとして宣言さ `near` れています。 割り込み関数はである必要があり `far` ます。

1. 、、またはで宣言された割り込み関数 **`__stdcall`** **`__fastcall`** 。 割り込み関数では、C の呼び出し規約を使用する必要があります。

## <a name="example"></a>例

C2217 は、可変個の引数を受け取る CLR 関数にデリゲートをバインドしようとした場合にも発生する可能性があります。 関数に e param 配列のオーバーロードもある場合は、代わりにを使用します。 次の例では、C2217 が生成されます。

```cpp
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```

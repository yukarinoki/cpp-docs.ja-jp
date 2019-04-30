---
title: コンパイラ エラー C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: f178f969afa189910c9d23d70226ecc6c15876a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353541"
---
# <a name="compiler-error-c2217"></a>コンパイラ エラー C2217

'attribute1' が 'attribute2' が必要です。

関数の最初の属性には、2 つ目の属性が必要です。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 中断 (`__interrupt`) として宣言された関数`near`します。 割り込み関数である必要があります`far`します。

1. 宣言された関数を中断`__stdcall`、または`__fastcall`します。 割り込み関数呼び出し規約を C++ を使用する必要があります。

## <a name="example"></a>例

C2217 は、可変個の引数を受け取る CLR 関数にデリゲートをバインドしようとした場合にも発生します。 また、関数は、e param 配列のオーバー ロードの場合は、代わりに使用します。 次の例では、C2217 が生成されます。

```
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
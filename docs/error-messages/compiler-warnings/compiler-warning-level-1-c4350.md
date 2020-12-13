---
description: '詳細情報: コンパイラの警告 (レベル 1) C4350'
title: コンパイラの警告 (レベル 1) C4350
ms.date: 11/04/2016
f1_keywords:
- C4350
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
ms.openlocfilehash: 0626c9c8d0196396c0d13a0697df2dfc64061db0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339996"
---
# <a name="compiler-warning-level-1-c4350"></a>コンパイラの警告 (レベル 1) C4350

動作変更: 'member1' が 'member2' の代わりに呼び出されました。

右辺値を非定数参照にバインドすることはできません。 Visual Studio 2003 より前のバージョンの Visual C++ では、直接初期化で非定数参照に右辺値をバインドすることができました。 このコードでは、警告が返されるようになりました。

旧バージョンとの互換性のために、右辺値を非 const 参照にバインドすることもできますが、可能な限り標準変換をお勧めします。

この警告は、Visual C++ .NET 2002 コンパイラからの動作の変更を表します。 有効にすると、正しいコードに対してこの警告が示される可能性があります。 たとえば、 **std:: auto_ptr** クラステンプレートを使用するときに指定できます。

この警告が表示された場合は、コードを調べて、非 const 参照への右辺値のバインドに依存しているかどうかを確認します。 Const を参照に追加するか、追加の const 参照オーバーロードを指定すると、問題が解決する可能性があります。

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

次の例では、C4350 が生成されます。

```cpp
// C4350.cpp
// compile with: /W1
#pragma warning (default : 4350)
class A {};

class B
{
public:
   B(B&){}
   // try the following instead:
   // B(const B&){}

   B(A){}
   operator A(){ return A();}
};

B source() { return A(); }

int main()
{
   B ap(source());   // C4350
}
```

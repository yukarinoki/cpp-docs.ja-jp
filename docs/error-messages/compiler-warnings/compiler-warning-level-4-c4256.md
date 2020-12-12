---
description: '詳細情報: コンパイラの警告 (レベル 4) C4256'
title: コンパイラの警告 (レベル 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: 3ccd8447f930f40df5e488714cdcfb52e54d9928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189302"
---
# <a name="compiler-warning-level-4-c4256"></a>コンパイラの警告 (レベル 4) C4256

' function ': 仮想基底クラスのコンストラクターには '... ' が含まれています。呼び出しは、以前のバージョンのと互換性がない場合があり Visual C++

互換性がない可能性があります。

次のコード例について考えてみます。 コンストラクター S2:: S2 (int i,...) の定義が、バージョン7より前のバージョンの Microsoft C++ コンパイラを使用してコンパイルされたが、次の例は現在のバージョンを使用してコンパイルされている場合、S3 のコンストラクターの呼び出しは、特殊な呼び出し規約の変更によって正しく機能しません。 両方が Visual C++ 6.0 を使用してコンパイルされた場合、省略記号にパラメーターが渡されていない限り、呼び出しはまったく正しく機能しません。

この警告を解決するには、

1. コンストラクターでは省略記号を使用しないでください。

1. プロジェクト内のすべてのコンポーネントが現在のバージョン (このクラスを定義または参照できるライブラリを含む) でビルドされていることを確認し、 [警告](../../preprocessor/warning.md) プラグマを使用して警告を無効にします。

次の例では、C4256 が生成されます。

```cpp
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```

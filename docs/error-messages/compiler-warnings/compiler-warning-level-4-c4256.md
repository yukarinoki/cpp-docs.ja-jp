---
title: コンパイラの警告 (レベル 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: b1f7534098a04c7c65a380d302999260c960f284
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400961"
---
# <a name="compiler-warning-level-4-c4256"></a>コンパイラの警告 (レベル 4) C4256

'function': 仮想基底クラスのコンス トラクターが '…';呼び出しは Visual C の以前のバージョンと互換性がない可能性があります。

可能な互換性がないです。

次のコード例について考えます。 場合 S2::S2 コンス トラクターの定義 (int i,...) より前のバージョン 7、に、Visual C コンパイラのバージョンを使用してコンパイルされましたが、現在のバージョンを使用して次の例をコンパイルするのためのコンス トラクターの呼び出しを s3 の場合は正しく動作しません特殊な呼び出し規約の変更。 両方は、Visual C 6.0 を使用してコンパイルした場合、呼び出しは機能しませんうまくか、省略記号のパラメーターが渡されない場合を除き、します。

この警告を修正するには

1. コンス トラクターでは、省略記号を使用しないでください。

1. プロジェクト内のすべてのコンポーネントが (定義またはこのクラスを参照する可能性のあるすべてのライブラリを含む)、現在のバージョンで構築された後を使用して、警告を無効にするかどうかを確認、[警告](../../preprocessor/warning.md)プラグマ。

次の例では、C4256 が生成されます。

```
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
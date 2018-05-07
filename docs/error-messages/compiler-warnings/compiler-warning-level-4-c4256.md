---
title: コンパイラの警告 (レベル 4) C4256 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4256
dev_langs:
- C++
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed1a40f0da75460c4306f69da0f26eb0888bef66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4256"></a>コンパイラの警告 (レベル 4) C4256
'function': 仮想基底クラスのコンス トラクターが '…';呼び出しは古いバージョンの Visual C と互換性がない可能性があります。  
  
 可能な互換性がないです。  
  
 次のコード例について考えます。 場合 S2::S2 コンス トラクターの定義 (int i,...) バージョン 7 より前に、Visual C コンパイラのバージョンを使用してコンパイルされましたが、現在のバージョンを使用して次の例をコンパイルするのため S3 のコンス トラクターの呼び出しは正しく機能しません特別なケース呼び出し規約の変更。 両方は、Visual C 6.0 を使用してコンパイルされた場合、呼び出しは機能しませんうまくいずれか、または、省略記号のパラメーターが渡されない限り、します。  
  
 この警告を解決するには  
  
1.  コンス トラクターでは、省略記号ボタンを使用しないでください。  
  
2.  プロジェクト内のすべてのコンポーネント (を定義することがありますまたはこのクラスを参照するライブラリを含む)、現在のバージョンで構築された後に、あるを使用して、警告を無効にするかどうかを確認、[警告](../../preprocessor/warning.md)プラグマ。  
  
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
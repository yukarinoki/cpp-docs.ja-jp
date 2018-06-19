---
title: _ _Asm ブロックの C マクロとしての定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69e1e7f2d4b980045a4e8993e39a69fc353a4f39
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050494"
---
# <a name="defining-asm-blocks-as-c-macros"></a>__asm ブロックの C マクロとしての定義
**Microsoft 固有の仕様**  
  
 C マクロ アセンブリ コード、ソース コードに挿入する便利な方法が、マクロが 1 つの論理行に展開するために十分な注意が求められています。 スムーズなマクロを作成するには、これらの規則に従います。  
  
-   囲む、`__asm`中かっこでブロックされます。  
  
-   Put、`__asm`各アセンブリ命令の前にキーワード。  
  
-   旧スタイルの C コメントを使用して ( `/* comment */`) アセンブリ スタイルのコメントではなく ( `; comment`) または C の単一行コメント ( `// comment`)。  
  
 理解するには、次の例は、単純なマクロを定義します。  
  
```  
#define PORTIO __asm      \  
/* Port output */         \  
{                         \  
   __asm mov al, 2        \  
   __asm mov dx, 0xD007   \  
   __asm out dx, al       \  
}  
```  
  
 一見、最後の 3 つ`__asm`キーワードが余分ないないと思われます。 必要であれば、ただし、単一行に、マクロが拡張されているため。  
  
```  
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }  
```  
  
 3 番目と 4 番目`__asm`ステートメント区切り記号としてのキーワードが必要です。 唯一のステートメント区切り文字が認識される`__asm`ブロックは、改行文字と`__asm`キーワード。 各命令を区切る必要があります、マクロとして定義されているブロックが 1 つの論理行であるため`__asm`です。  
  
 中かっこは、同様に不可欠です。 これらを省略する場合、コンパイラはマクロ呼び出しの右側に同じ行の C または C++ ステートメントによって混同しないでくださいことができます。 コンパイラは、終わりかっこなしアセンブリ コードが停止して、その区別できません C または C++ ステートメントを表示した後、`__asm`アセンブリ命令としてブロックします。  
  
 セミコロンで始まるアセンブリ スタイルのコメント (**;**)、行の末尾まで続行します。 コンパイラは論理行の末尾まで、コメントの後にすべてのものを無視するためのマクロの問題が発生します。 単一行の C または C++ のコメントの場合も同様です ( `// comment`)。 エラーを回避するのに旧スタイルの C のコメントを使用して ( `/* comment */`) で`__asm`マクロとして定義されているブロックです。  
  
 `__asm`ブロックの C マクロが引数を受け取らないように書き込まれます。 通常 C マクロ、ただしとは異なり、`__asm`マクロが値を返すことはできません。 C または C++ の式でこのようなマクロは使用できません。  
  
 この型のマクロの呼び出しを無秩序しないように注意します。 インスタンスで宣言された関数で、アセンブリ言語マクロを呼び出し、`__fastcall`規約予期しない結果が発生する可能性があります。 (を参照してください[を使用して、インライン アセンブリでのレジスタの維持](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md))。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)
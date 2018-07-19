---
title: インライン アセンブラーの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31b0497f2fdc319115018a05618d3a16607dbef1
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049776"
---
# <a name="inline-assembler-overview"></a>インライン アセンブラーの概要
**Microsoft 固有の仕様**  
  
 インライン アセンブラーを使用して、アセンブリとリンクの追加手順なし C および C++ ソース プログラム内でアセンブリ言語命令を埋め込むことができます。 インライン アセンブラーは、コンパイラに組み込まれます。したがって、MASM (Microsoft Macro Assembler) などの別のアセンブラーは必要ではありません。  
  
 インライン アセンブラーは別のアセンブリとリンクの手順を必要としないので、別のアセンブラーより便利です。 インライン アセンブラー コードでは、任意 C または C++ 変数または関数の名前を簡単に、プログラムの C および C++ コードと統合するようにするために、スコープでを使用できます。 煩雑や C または C++ だけで不可能なタスクを実行できるため、C および C++ の各ステートメントは、アセンブリ コードを混在させることができます、します。  
  
 [_ _Asm](../../assembler/inline/asm.md)キーワードをインライン アセンブラーを呼び出し、C または C++ ステートメントは有効な任意の場所を使用できます。 これは、単独では使用できません。 アセンブリ命令、中かっこで囲まれた命令グループ、または少なくとも空の中かっこの後で指定する必要があります。 "`__asm` ブロック" という用語は、ここでは、中かっこに囲まれているかどうかを問わず、命令または命令のグループを示します。  
  
 次のコードは、単純な`__asm`中かっこで囲まれたブロックします。 (コードは、カスタム関数プロローグ シーケンスです)。  
  
```  
// asm_overview.cpp  
// processor: x86  
void __declspec(naked) main()  
{  
    // Naked functions must provide their own prolog...  
    __asm {  
        push ebp  
        mov ebp, esp  
        sub esp, __LOCAL_SIZE  
    }  
  
    // ... and epilog  
    __asm {  
        pop ebp  
        ret  
    }  
}  
```  
  
 または、各アセンブリ命令の前に `__asm` を置くことができます。  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 `__asm` キーワードはステートメント区切り文字であるため、アセンブリ命令も同じ行に記述できます。  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)
---
description: '詳細情報: インライン アセンブラー (C)'
title: インライン アセンブラー (C)
ms.date: 11/04/2016
helpviewer_keywords:
- __asm keyword [C]
- inline assembler [C]
ms.assetid: 821acc77-60b1-434c-ba54-2ba930a25ab4
ms.openlocfilehash: 8c5dc8ecc713968786b05eca6ab38e4752ea48c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181853"
---
# <a name="inline-assembler-c"></a>インライン アセンブラー (C)

**Microsoft 固有の仕様**

インライン アセンブラーでは、追加のアセンブリとリンク ステップを使用せずに、アセンブリ言語命令を C のソース プログラムに直接埋め込むことができます。 インライン アセンブラーは、コンパイラに組み込まれます。したがって、MASM (Microsoft Macro Assembler) などの別のアセンブラーは必要ではありません。

インライン アセンブラーは別のアセンブリとリンクの手順を必要としないので、別のアセンブラーより便利です。 インライン アセンブラー コードでは、スコープ内にある C 変数や関数名を使用できるので、プログラムの C コードと簡単に統合できます。 そして、アセンブリ コードは C のステートメントと混合できるため、C 単独では使いにくいタスクや不可能なタスクを行うことができます。

**`__asm`** キーワードによってインライン アセンブラーを呼び出せます。C ステートメントが有効である任意の場所に使用できます。 これは、単独では使用できません。 アセンブリ命令、中かっこで囲まれた命令グループ、または少なくとも空の中かっこの後で指定する必要があります。 " **`__asm`** ブロック" という用語は、ここでは、中かっこに囲まれているかどうかを問わず、命令または命令のグループを示します。

次のコードは、中かっこで囲まれたシンプルな **`__asm`** ブロックです (コードは、カスタム関数プロローグ シーケンスです)。

```
__asm
{
   push ebp
   mov  ebp, esp
   sub  esp, __LOCAL_SIZE
}
```

または、各アセンブリ命令の前に **`__asm`** を置くことができます。

```
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

**`__asm`** キーワードはステートメント区切り文字であるため、アセンブリ命令も同じ行に記述できます。

```
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[関数の属性](../c-language/function-attributes.md)

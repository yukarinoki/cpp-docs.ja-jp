---
title: インライン アセンブラーの概要
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
ms.openlocfilehash: 3872dcb194146bf0f4c89b0be03a49b5fe3a9e37
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192081"
---
# <a name="inline-assembler-overview"></a>インライン アセンブラーの概要

**Microsoft 固有の仕様**

インラインアセンブラーでは、アセンブリとリンクの手順を追加せずに、C および C++ のソースプログラムにアセンブリ言語命令を埋め込むことができます。 インライン アセンブラーは、コンパイラに組み込まれます。したがって、MASM (Microsoft Macro Assembler) などの別のアセンブラーは必要ではありません。

インライン アセンブラーは別のアセンブリとリンクの手順を必要としないので、別のアセンブラーより便利です。 インラインアセンブラーコードでは、スコープ内にある C または C++ の変数または関数の名前を使用できます。そのため、プログラムの C および C++ コードと簡単に統合できます。 また、アセンブリコードは C と C++ のステートメントと混在させることができるため、C または C++ だけでは煩雑で不可能なタスクを実行できます。

[__Asm](../../assembler/inline/asm.md)キーワードは、インラインアセンブラーを呼び出し、C または C++ のステートメントが有効であればどこにでも表示できます。 これは、単独では使用できません。 アセンブリ命令、中かっこで囲まれた命令グループ、または少なくとも空の中かっこの後で指定する必要があります。 ここでの "ブロック" という用語は、 **`__asm`** 中かっこで囲まれているかどうかにかかわらず、命令または命令のグループを指します。

次のコードは、 **`__asm`** 中かっこで囲まれた単純なブロックです。 (コードは、カスタム関数プロローグ シーケンスです)。

```cpp
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

または、 **`__asm`** 各アセンブリ命令の前にを配置することもできます。

```cpp
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

**`__asm`** キーワードはステートメント区切り文字であるため、同じ行にアセンブリ命令を配置することもできます。

```cpp
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>

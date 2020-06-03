---
title: インライン アセンブラーの概要
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
ms.openlocfilehash: 6233e07e115c21a0a173f094079dc9c1753533b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169398"
---
# <a name="inline-assembler-overview"></a>インライン アセンブラーの概要

**Microsoft 固有の仕様**

インラインアセンブラーでは、アセンブリとリンクの手順を追加せずC++に、C およびソースプログラムにアセンブリ言語命令を埋め込むことができます。 インライン アセンブラーは、コンパイラに組み込まれます。したがって、MASM (Microsoft Macro Assembler) などの別のアセンブラーは必要ではありません。

インライン アセンブラーは別のアセンブリとリンクの手順を必要としないので、別のアセンブラーより便利です。 インラインアセンブラーコードでは、スコープ内C++にある c または変数または関数の名前を使用できます。そのため、プログラムの c C++およびコードと簡単に統合できます。 また、アセンブリコードは C とC++ステートメントを混在させることができるため、c またはC++単独では煩雑で不可能なタスクを実行できます。

[__Asm](../../assembler/inline/asm.md)キーワードは、インラインアセンブラーを呼び出し、C またはC++ステートメントが有効であればどこにでも表示できます。 これは、単独では使用できません。 アセンブリ命令、中かっこで囲まれた命令グループ、または少なくとも空の中かっこの後で指定する必要があります。 "`__asm` ブロック" という用語は、ここでは、中かっこに囲まれているかどうかを問わず、命令または命令のグループを示します。

次のコードは、中かっこで囲まれた単純な `__asm` ブロックです。 (コードは、カスタム関数プロローグ シーケンスです)。

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

または、各アセンブリ命令の前に `__asm` を置くことができます。

```cpp
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

`__asm` キーワードはステートメント区切り文字であるため、アセンブリ命令も同じ行に記述できます。

```cpp
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>

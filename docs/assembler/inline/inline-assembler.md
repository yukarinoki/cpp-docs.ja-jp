---
description: 詳細については、「インラインアセンブラー」を参照してください。
title: インライン アセンブラー
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
ms.openlocfilehash: 67ae8c40dee71f693dd6641dd81e8f61b8536a1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117771"
---
# <a name="inline-assembler"></a>インライン アセンブラー

**Microsoft 固有の仕様**

アセンブリ言語は、プログラムの実行速度の向上、必要メモリ量の削減、ハードウェアの制御など、さまざまな目的に適しています。 インライン アセンブラーを使用して、追加のアセンブリとリンク ステップを使用せずに、アセンブリ言語命令を C および C++ のソース プログラムに直接埋め込むことができます。 インライン アセンブラーは、コンパイラに組み込まれます。したがって、MASM (Microsoft Macro Assembler) などの別のアセンブラーは必要ではありません。

> [!NOTE]
> インライン アセンブラー コードを含むプログラムは、他のハードウェア プラットフォームに完全に移植できるわけではありません。 移植性を考慮して設計する場合、インライン アセンブラーは使用しないでください。

インラインアセンブリは、ARM および x64 プロセッサではサポートされていません。  ここからのトピックでは、x86 プロセッサで Visual C/C++ インライン アセンブラーを使用する方法を示します。

- [インラインアセンブラーの概要](../../assembler/inline/inline-assembler-overview.md)

- [インラインアセンブリの利点](../../assembler/inline/advantages-of-inline-assembly.md)

- [__asm](../../assembler/inline/asm.md)

- [__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)

- [__Asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)

- [インラインアセンブリでのレジスタの使用と保持](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)

- [インラインアセンブリ内のラベルへのジャンプ](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)

- [インラインアセンブリでの C 関数の呼び出し](../../assembler/inline/calling-c-functions-in-inline-assembly.md)

- [インラインアセンブリでの C++ 関数の呼び出し](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)

- [定義 (__asm ブロックを C マクロとして)](../../assembler/inline/defining-asm-blocks-as-c-macros.md)

- [インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込みとアセンブリ言語](../../intrinsics/compiler-intrinsics-and-assembly-language.md)<br/>
[C++ 言語リファレンス](../../cpp/cpp-language-reference.md)<br/>

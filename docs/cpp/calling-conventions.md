---
title: 呼び出し規則
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: 9aa25598674aa52502d5d3619e5015eb13b6fff8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532783"
---
# <a name="calling-conventions"></a>呼び出し規則

Visual C/C++ コンパイラには、内部関数と外部関数の呼び出し規約がいくつか用意されています。 これらの異なる方法を理解することは、プログラムをデバッグし、コードをアセンブリ言語ルーチンとリンクするときに役立ちます。

この話題に関するトピックでは、呼び出し規約の違い、引数の渡し方、関数による値の返し方について説明します。 naked 関数の呼び出し (独自のプロローグおよびエピローグ コードを記述できる高度な機能) についても説明します。

X64 呼び出し規則については、プロセッサを参照してください[呼び出し規約](../build/calling-convention.md)します。

## <a name="topics-in-this-section"></a>このセクションのトピック

- [引数を渡すと名前付け規則](../cpp/argument-passing-and-naming-conventions.md)(`__cdecl`、 `__stdcall`、 `__fastcall`、およびその他)

- [呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)

- [Naked 関数呼び出しを使用して、カスタム プロローグ/エピローグ コードを記述するには](../cpp/naked-function-calls.md)

- [浮動小数点コプロセッサと呼び出し規約](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [廃止された呼び出し規則](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>関連項目

[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)
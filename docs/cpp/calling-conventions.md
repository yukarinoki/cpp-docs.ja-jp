---
title: 呼び出し規則
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: 432cb1b6910db5ea735288edfbf6aa9e10f0a486
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190288"
---
# <a name="calling-conventions"></a>呼び出し規則

Visual C/C++ コンパイラには、内部関数と外部関数の呼び出し規約がいくつか用意されています。 これらの異なる方法を理解することは、プログラムをデバッグし、コードをアセンブリ言語ルーチンとリンクするときに役立ちます。

この話題に関するトピックでは、呼び出し規則の違い、引数の渡し方、関数による値の返し方について説明します。 naked 関数の呼び出し (独自のプロローグおよびエピローグ コードを記述できる高度な機能) についても説明します。

X64 プロセッサの呼び出し規約の詳細については、「[呼び出し規約](../build/x64-calling-convention.md)」を参照してください。

## <a name="topics-in-this-section"></a>このセクションのトピック

- [引数の引き渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)(`__cdecl`、`__stdcall`、`__fastcall`など)

- [呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)

- [生の関数呼び出しを使用してカスタムプロローグ/エピローグコードを記述する](../cpp/naked-function-calls.md)

- [浮動小数点コプロセッサと呼び出し規約](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [互換性のために残されている呼び出し規約](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>参照

[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)

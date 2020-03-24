---
title: __thiscall
ms.date: 11/04/2016
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: 8772159dca71bb7605af5e5919425065423d503d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188156"
---
# <a name="__thiscall"></a>__thiscall

**Microsoft 固有の仕様**

**__Thiscall**呼び出し規約は、メンバー関数で使用されます。変数引数を使用C++しないメンバー関数によって使用される既定の呼び出し規約です。 **__Thiscall**では、呼び出し先がスタックを消去します。これは `vararg` 関数では不可能です。 引数はスタック上で右から左にプッシュされます。**この**ポインターは、x86 アーキテクチャではスタックではなくレジスタ ECX によって渡されます。

**__Thiscall**を使用する理由の1つは、既定で `__clrcall` を使用するメンバー関数を持つクラスです。 その場合は **__thiscall**を使用して、ネイティブコードから個々のメンバー関数を呼び出せるようにすることができます。

[/Clr: pure](../build/reference/clr-common-language-runtime-compilation.md)を指定してコンパイルする場合、特に指定しない限り、すべての関数および関数ポインターが `__clrcall` されます。 **/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

Visual Studio 2005 より前のリリースでは、 **__thiscall**がキーワードではないため、 **__thiscall**呼び出し規約をプログラムで明示的に指定できませんでした。

`vararg` メンバー関数は、 **__cdecl**呼び出し規約を使用します。 すべての関数の引数はスタックにプッシュされ、**この**ポインターは最後にスタックに配置されます。

この呼び出し規則は C++ だけに適用されるため、C の名前の装飾スキームはありません。

ARM および x64 コンピューターでは、 **__thiscall**は受け入れられ、コンパイラによって無視されます。

静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規約の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)

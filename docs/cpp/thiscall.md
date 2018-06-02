---
title: _ _thiscall |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4912628529ae0b47a5a5b938ab8e6d25a9099510
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704404"
---
# <a name="thiscall"></a>__thiscall

**Microsoft 固有の仕様**

`__thiscall` 呼び出し規約はメンバー関数で使用され、可変個引数を使用しない C++ メンバー関数によって使用される既定の呼び出し規約です。 `__thiscall` では呼び出し先がスタックをクリーンアップしますが、これは `vararg` 関数では不可能です。 引数は、x86 アーキテクチャでは、スタックではなくレジスタ ECX を介して渡される `this` ポインターでスタックに右から左へプッシュされます。

`__thiscall` を使用する理由の 1 つは、メンバー関数が `__clrcall` を既定で使用するクラスにあります。 その場合、`__thiscall` を使用して、個々のメンバー関数をネイティブ コードから呼び出すことができます。

コンパイルするときに[/clr: 純粋な](../build/reference/clr-common-language-runtime-compilation.md)、すべての関数および関数ポインターは`__clrcall`指定しない限り、します。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

Visual C 2005 以前のリリースで、`__thiscall`呼び出し規約がない明示的に指定するプログラムでは、ため`__thiscall`キーワードではありません。

`vararg` メンバー関数は `__cdecl` の呼び出し規約を使用します。 関数のすべての引数は、スタックにプッシュされ、`this` ポインターが最後にスタックに配置されます。

この呼び出し規則は C++ だけに適用されるため、C の名前の装飾スキームはありません。

ARM および x64 マシン`__thiscall`が受け入れられたり、コンパイラによって無視されます。

静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規則が定義の時点で仮定されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

- [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)

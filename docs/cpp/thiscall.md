---
title: _ _thiscall |Microsoft Docs
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
ms.openlocfilehash: af20b6d406b0e2119df04d5348c554b3405e8597
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103374"
---
# <a name="thiscall"></a>__thiscall

**Microsoft 固有の仕様**

**_ _Thiscall**メンバー関数で使用され、可変個の引数を使用しない C++ メンバー関数によって使用される既定の呼び出し規約は、呼び出し規約。 **_ _Thiscall**、呼び出し先のことはできませんが、スタックを消去する`vararg`関数。 右から左への引数をスタックにプッシュは、**この**ポインター レジスタ ECX、および、x86 上で、スタックに渡されるアーキテクチャ。

使用する理由の 1 つ **_ _thiscall**クラス メンバー関数が使用されて`__clrcall`既定。 使用する場合、 **_ _thiscall**個々 のメンバーの関数をネイティブ コードから呼び出すことにします。

コンパイルするときに[/clr: 純粋な](../build/reference/clr-common-language-runtime-compilation.md)、すべての関数および関数ポインターは`__clrcall`それ以外の場合に指定されていない場合。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

Visual C 2005 では、以前のリリースでは、 **_ _thiscall**呼び出し規約がいない明示的に指定するプログラムでは、ため **_ _thiscall**がキーワードではありません。

`vararg` メンバー関数の使用、 **_ _cdecl**呼び出し規約。 すべての関数の引数はで、スタックにプッシュされます、**この**ポインターはスタックに最後に配置

この呼び出し規則は C++ だけに適用されるため、C の名前の装飾スキームはありません。

ARM と x64 マシン **_ _thiscall**が受け入れられるし、コンパイラによって無視されます。

静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規則が定義の時点で仮定されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)
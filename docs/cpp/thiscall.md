---
title: __thiscall
ms.date: 05/22/2020
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: b9edc2cd8caa5fd5458f6a53c5fdb1f8a5e69914
ms.sourcegitcommit: 5bb421fdf61d290cac93a03e16a6a80959accf6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83854815"
---
# `__thiscall`

**Microsoft 固有**の **`__thiscall`** 呼び出し規約は、X86 アーキテクチャの C++ クラスメンバー関数で使用されます。 これは、可変個の引数 (functions) を使用しないメンバー関数によって使用される既定の呼び出し規約です `vararg` 。

で **`__thiscall`** は、呼び出し先がスタックを消去します。これは、関数では不可能です `vararg` 。 引数は、右から左にスタックにプッシュされます。 **`this`** ポインターは、スタックではなくレジスタ ECX を介して渡されます。

ARM、ARM64、および x64 コンピューターで **`__thiscall`** は、はコンパイラによって受け入れられ、無視されます。 これは、既定では、レジスタベースの呼び出し規約を使用するためです。

使用する理由の1つ **`__thiscall`** は、メンバー関数が既定でを使用するクラスにある **`__clrcall`** ことです。 その場合は、を使用して、 **`__thiscall`** 個々のメンバー関数をネイティブコードから呼び出すことができます。

を指定してコンパイルする場合 [**`/clr:pure`**](../build/reference/clr-common-language-runtime-compilation.md) 、特に指定しない限り、すべての関数および関数ポインターはに **`__clrcall`** なります。 **`/clr:pure`** および **`/clr:safe`** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

`vararg`メンバー関数は、 **`__cdecl`** 呼び出し規約を使用します。 すべての関数の引数はスタックにプッシュされ、 **`this`** ポインターは最後にスタックに配置されます。

この呼び出し規則は C++ にのみ適用されるため、C の名前の装飾スキームはありません。

非静的クラスメンバー関数をアウトオブラインで定義する場合は、宣言内でのみ呼び出し規約修飾子を指定します。 アウトオブライン定義で再度指定する必要はありません。 コンパイラは、定義の時点で、宣言時に指定された呼び出し規約を使用します。

## <a name="see-also"></a>関連項目

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)

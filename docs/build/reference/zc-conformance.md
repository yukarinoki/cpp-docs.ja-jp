---
title: /Zc (準拠)
description: /Zc 準拠コンパイラオプションは、準拠または下位互換性の動作のサポートを有効または無効にします。
ms.date: 09/10/2020
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 15027182d632c1076c78e2e8a1335e1059ac7e3b
ms.sourcegitcommit: 14d6ae0d527d05d153e26463d4cd5ada0f43e864
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "98104766"
---
# <a name="zc-conformance"></a>`/Zc` 互換性

コンパイラオプションを使用して、 **`/Zc`** 標準または Microsoft 固有のコンパイラの動作を指定できます。

## <a name="syntax"></a>構文

> **`/Zc:`**_オプション_{、_オプション_}

## <a name="remarks"></a>解説

Visual Studio で、標準と互換性のない C または C++ の拡張機能が実装されている場合は、準拠オプションを使用して、 **`/Zc`** 標準準拠または Microsoft 固有の動作を指定できます。 一部のオプションでは、既存のコードに大きな変更が加えられないように、Microsoft 固有の動作が既定値になります。 それ以外の場合、既定値は標準の動作であり、セキュリティ、パフォーマンス、または互換性の向上が重大な変更のコストよりも優先されます。 各準拠オプションの既定の設定は、新しいバージョンの Visual Studio で変更される可能性があります。 各準拠オプションの詳細については、「」を参照してください。 [`/permissive-`](permissive-standards-conformance.md)コンパイラオプションは、既定では、準拠する設定に設定されていない準拠オプションを暗黙的に設定します。

コンパイラオプションは次の **`/Zc`** とおりです。

| オプション | 動作 |
|--|--|
| [`/Zc:alignedNew`](zc-alignednew.md) | C++ 17 の動的割り当て (C++ 17 では既定でオン) を有効にします。 |
| [`/Zc:auto`](zc-auto-deduce-variable-type.md) | (既定ではオン) に新しい標準 C++ の意味を適用し **`auto`** ます。 |
| [`/Zc:__cplusplus`](zc-cplusplus.md) | `__cplusplus`サポートされている標準を報告するようにマクロを有効にします (既定ではオフ)。 |
| [`/Zc:externConstexpr`](zc-externconstexpr.md) | 変数の外部リンケージを有効に **`constexpr`** します (既定ではオフ)。 |
| [`/Zc:forScope`](zc-forscope-force-conformance-in-for-loop-scope.md) | 標準 C++ **`for`** のスコープ規則を適用します (既定ではオン)。 |
| [`/Zc:implicitNoexcept`](zc-implicitnoexcept-implicit-exception-specifiers.md) | 必須の関数に対して暗黙的に有効に **`noexcept`** します (既定ではオン)。 |
| [`/Zc:inline`](zc-inline-remove-unreferenced-comdat.md) | 参照されていない関数またはデータが COMDAT である場合、または内部リンケージのみを持つ場合 (既定ではオフ) は、削除します。 |
| [`/Zc:noexceptTypes`](zc-noexcepttypes.md) | C++ 17 の **`noexcept`** 規則を適用します (既定では c++ 17 以降で)。 |
| [`/Zc:preprocessor`](zc-preprocessor.md) | 新しい準拠プリプロセッサを使用します (既定ではオフになっていますが、C11/C17 は除きます)。 |
| [`/Zc:referenceBinding`](zc-referencebinding-enforce-reference-binding-rules.md) | UDT の一時停止は、非定数の左辺値参照にバインドされません (既定ではオフ)。 |
| [`/Zc:rvalueCast`](zc-rvaluecast-enforce-type-conversion-rules.md) | 標準 C++ 明示的な型変換規則を適用します (既定ではオフ)。 |
| [`/Zc:sizedDealloc`](zc-sizeddealloc-enable-global-sized-dealloc-functions.md) | C++ 14 グローバルサイズ割り当て解除関数を有効にします (既定ではオン)。 |
| [`/Zc:strictStrings`](zc-strictstrings-disable-string-literal-type-conversion.md) | 文字列リテラル `char*` または `wchar_t*` 変換 (既定ではオフ) を無効にします。 |
| [`/Zc:ternary`](zc-ternary.md) | オペランドの型に条件演算子規則を適用します (既定ではオフ)。 |
| [`/Zc:threadSafeInit`](zc-threadsafeinit-thread-safe-local-static-initialization.md) | スレッドセーフなローカルの静的初期化 (既定ではオン) を有効にします。 |
| [`/Zc:throwingNew`](zc-throwingnew-assume-operator-new-throws.md) | エラーが発生した場合は **`operator new`** をスローします (既定ではオフ)。 |
| [`/Zc:trigraphs`](zc-trigraphs-trigraphs-substitution.md) | トライグラフを有効にします (obsolete、既定ではオフ)。 |
| [`/Zc:twoPhase`](zc-twophase.md) | 準拠していないテンプレートの解析動作を使用します (既定で準拠)。 |
| [`/Zc:wchar_t`](zc-wchar-t-wchar-t-is-native-type.md) | **`wchar_t`** は、typedef (既定では on) ではなく、ネイティブ型です。 |

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)

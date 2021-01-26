---
title: /Zc (準拠)
description: /Zc 準拠コンパイラオプションは、準拠または下位互換性の動作のサポートを有効または無効にします。
ms.date: 01/23/2021
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.openlocfilehash: 066e6712b07dbc28e88a7e01a5055dab90289326
ms.sourcegitcommit: 74e58bee5cffb30b66e17be6dbfde2544369638e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "98763888"
---
# <a name="zc-conformance"></a>`/Zc` 互換性

コンパイラオプションを使用して、 **`/Zc`** 標準または Microsoft 固有のコンパイラの動作を指定できます。

## <a name="syntax"></a>構文

> **`/Zc:`**_オプション_{、_オプション_ ...}

**`/Zc`** 1 つのコンパイラオプションで、複数のオプションをコンマで区切って設定でき **`/Zc`** ます。 同じコマンドでオプションが有効になっていて無効になっている場合は、 **`/Zc`** last と表示されるオプションが使用されます。

## <a name="remarks"></a>解説

Visual Studio によって、標準と互換性のない C または C++ の拡張機能が実装されている場合は、準拠オプションを使用して **`/Zc`** 標準準拠または Microsoft 固有の動作を指定できます。 一部のオプションでは、既存のコードに大きな変更が加えられないように、Microsoft 固有の動作が既定値になります。 それ以外の場合、既定値は標準の動作であり、セキュリティ、パフォーマンス、または互換性の向上が重大な変更のコストよりも優先されます。 各準拠オプションの既定の設定は、新しいバージョンの Visual Studio で変更される可能性があります。 各準拠オプションの詳細については、「」を参照してください。 コンパイラオプションは、既定では、準拠 [`/permissive-`](permissive-standards-conformance.md) する設定に設定されていない準拠オプションを暗黙的に設定します。

**`/Zc`** コンパイラオプションは次のとおりです。

| オプション | 動作 |
|--|--|
| [`/Zc:alignedNew`](zc-alignednew.md) | C++ 17 の動的割り当て (C++ 17 では既定でオン) を有効にします。 |
| [`/Zc:auto`](zc-auto-deduce-variable-type.md) | (既定ではオン) に新しい標準 C++ の意味を適用し **`auto`** ます。 |
| [`/Zc:__cplusplus`](zc-cplusplus.md) | `__cplusplus`サポートされている標準を報告するようにマクロを有効にします (既定ではオフ)。 |
| [`/Zc:externConstexpr`](zc-externconstexpr.md) | 変数の外部リンケージを有効に **`constexpr`** します (既定ではオフ)。 |
| [`/Zc:forScope`](zc-forscope-force-conformance-in-for-loop-scope.md) | 標準 C++ **`for`** のスコープ規則を適用します (既定ではオン)。 |
| [`/Zc:hiddenFriend`](zc-hiddenfriend.md) | 標準 C++ の非表示フレンド規則を適用する (によって暗黙的 **`/permissive-`** ) |
| [`/Zc:implicitNoexcept`](zc-implicitnoexcept-implicit-exception-specifiers.md) | 必須の関数に対して暗黙的に有効に **`noexcept`** します (既定ではオン)。 |
| [`/Zc:inline`](zc-inline-remove-unreferenced-comdat.md) | 参照されていない関数またはデータが COMDAT である場合や、内部リンケージのみを持つ場合 (既定ではオフ)、参照されない関数またはデータを削除 |
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

MSVC の準拠に関する問題の詳細については、「 [非標準動作](../../cpp/nonstandard-behavior.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)

---
title: /Zc (準拠)
ms.date: 03/06/2018
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 4422524deab2a749c96d5e967bc3223d0c9c9873
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438668"
---
# <a name="zc-conformance"></a>/Zc (準拠)

**/Zc**コンパイラオプションを使用して、標準または Microsoft 固有のコンパイラの動作を指定できます。

## <a name="syntax"></a>構文

> **/Zc:** _option_{,_option_}

## <a name="remarks"></a>コメント

Visual Studio によって C の拡張が実装C++されている場合、または標準と互換性がない場合は、`/Zc` 準拠オプションを使用して、標準準拠または Microsoft 固有の動作を指定できます。 一部のオプションでは、既存のコードに大きな変更が加えられないように、Microsoft 固有の動作が既定値になります。 それ以外の場合、既定値は標準の動作であり、セキュリティ、パフォーマンス、または互換性の向上が重大な変更のコストよりも優先されます。 各準拠オプションの既定の設定は、新しいバージョンの Visual Studio で変更される可能性があります。 各準拠オプションの詳細については、「」を参照してください。 [/Permissive-](permissive-standards-conformance.md)コンパイラオプションは、既定では、準拠する設定に設定されていない準拠オプションを暗黙的に設定します。

`/Zc` コンパイラオプションを次に示します。

|オプション|動作|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C++ 17 の動的割り当て (C++ 17 では既定でオン) を有効にします。|
|[自動\[-\]](zc-auto-deduce-variable-type.md)|`auto` (既定でC++はオン) の新しい標準の意味を適用します。|
|[__cplusplus\[-\]](zc-cplusplus.md)|サポートされている標準をレポートするために **__cplusplus**マクロを有効にします (既定ではオフ)。|
|[externConstexpr\[-\]](zc-externconstexpr.md)|`constexpr` 変数の外部リンケージを有効にします (既定ではオフ)。|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|標準C++ `for` のスコープルールを適用します (既定ではオン)。|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|必須の関数で暗黙の `noexcept` を有効にします (既定ではオン)。|
|[インライン\[-\]](zc-inline-remove-unreferenced-comdat.md)|参照されていない関数またはデータが COMDAT である場合、または内部リンケージのみを持つ場合 (既定ではオフ) は、削除します。|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C++ 17 noexcept ルールを適用します (既定では C++ 17 以降でオン)。|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|UDT の一時停止は、非定数の左辺値参照にバインドされません (既定ではオフ)。|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|標準C++の明示的な型変換規則を適用します (既定ではオフ)。|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C++ 14 グローバルサイズ割り当て解除関数を有効にします (既定ではオン)。|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|`char*` または `wchar_t*` 変換 (既定ではオフ) に対して文字列リテラルを無効にします。|
|[三項\[-\]](zc-ternary.md)|オペランドの型に条件演算子規則を適用します (既定ではオフ)。|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|スレッドセーフなローカルの静的初期化 (既定ではオン) を有効にします。|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|エラーが発生したときに `operator new` スローするとします (既定ではオフ)。|
|[トライグラフ\[-\]](zc-trigraphs-trigraphs-substitution.md)|トライグラフを有効にします (obsolete、既定ではオフ)。|
|[twoPhase](zc-twophase.md)|準拠していないテンプレートの解析動作を使用します (既定で準拠)。|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` は、typedef (既定ではオン) ではなく、ネイティブな型です。|

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)

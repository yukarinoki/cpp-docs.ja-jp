---
title: C++ のドキュメントの更新情報
description: Microsoft C/C++ コンパイラ、ATL/MFC、C ランタイム、標準ライブラリに関する新しいドキュメントとドキュメントの更新。
ms.date: 02/17/2021
ms.openlocfilehash: ad626dc598cd17de091801b2c313b7339db4cbc7
ms.sourcegitcommit: 5efc34c2b98d4d0d3e41aec38b213f062c19d078
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "101844534"
---
# <a name="microsoft-c-docs-whats-new-for-visual-studio-168"></a>Microsoft C++ のドキュメント: Visual Studio 16.8 での更新情報

この記事では、Visual Studio 16.8 のドキュメントに対する主な変更点の一部を示します。 

Visual Studio での新機能については、「[Visual Studio での C++ の新機能](what-s-new-for-visual-cpp-in-visual-studio.md)」を参照してください。

C++ の最新の準拠状態については、「[Visual Studio の C++ 準拠の強化](cpp-conformance-improvements.md)」を参照してください。

## <a name="c-language"></a>C 言語

### <a name="new-articles"></a>新しい記事

- [`_Noreturn` キーワードと `noreturn` マクロ (C11)](../c-language/noreturn.md)
- [_Static_assert キーワードと static_assert マクロ (C11)](../c-language/static-assert-c.md)

### <a name="updated-articles"></a>更新された記事

- [C コマンド ライン引数の解析](../c-language/parsing-c-command-line-arguments.md) - C 引数の解析に関する規則に対する例外の記載
- [型修飾子](../c-language/type-qualifiers.md) - `restrict` の追加
- [C 代入演算子](../c-language/c-assignment-operators.md) - C17 の字句文法の更新
- [C キーワード](../c-language/c-keywords.md) - C17 の字句文法の更新
- [C 字句文法](../c-language/lexical-grammar.md) - C17 の字句文法の更新
- [宣言の概要](../c-language/summary-of-declarations.md) - C17 の字句文法の更新
- [式の概要](../c-language/summary-of-expressions.md) - C17 の字句文法の更新
- [C での列挙体の宣言](../c-language/c-enumeration-declarations.md) - 字句文法の修正
- [C ステートメントの概要](../c-language/summary-of-statements.md) - `__leave` および `__try` キーワードに関する更新

## <a name="c-runtime-library"></a>C ランタイム ライブラリ

### <a name="new-articles"></a>新しい記事

- [ジェネリック型数値演算](../c-runtime-library/tgmath.md)

### <a name="updated-articles"></a>更新された記事

- [`qsort`](../c-runtime-library/reference/qsort.md) - 安定性に関するメモの追加
- [`_cwait`](../c-runtime-library/reference/cwait.md) - コード例の修正
- [関数ファミリの概要](../c-runtime-library/function-family-overviews.md) - 演算子 `new` と `delete` の追加
- [`round, roundf, roundl`](../c-runtime-library/reference/round-roundf-roundl.md) - 丸めのコード例の明確化
- [互換性](../c-runtime-library/compatibility.md) - C99 の準拠に関するメモの追加
- [`realloc`](../c-runtime-library/reference/realloc.md) - C99 の準拠に関するメモの追加
- [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md) - C99 の準拠に関するメモの追加
- [`assert Macro, _assert, _wassert`](../c-runtime-library/reference/assert-macro-assert-wassert.md) - アサートの動作の明確化
- [`vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l`](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md) - 戻り値の明確化
- [`setlocale, _wsetlocale`](../c-runtime-library/reference/setlocale-wsetlocale.md) - C ランタイムの UTF-8 サポート情報の追加

## <a name="cc-preprocessor-reference"></a>C/C++ のプリプロセッサ リファレンス

### <a name="updated-articles"></a>更新された記事

- [定義済みマクロ](../preprocessor/predefined-macros.md) - 16.8 リリース ノート、C11/C17 の `/std` のサポート、SDK インストール ドキュメントの更新
- [MSVC の新しいプリプロセッサの概要](../preprocessor/preprocessor-experimental-overview.md) - プリプロセッサに関する内容の更新

## <a name="code-quality"></a>コード品質

### <a name="new-articles"></a>新しい記事

- [C33001](../code-quality/c33001.md) - VC Code Analysis - 16.8 での新しい規則に関する追加
- [C33004](../code-quality/c33004.md) - VC Code Analysis - 16.8 での新しい規則に関する追加
- [C33005](../code-quality/c33005.md) - VC Code Analysis - 16.8 での新しい規則に関する追加
- [C33010](../code-quality/c33010.md) - VC Code Analysis - 16.8 での新しい規則に関する追加
- [C33011](../code-quality/c33011.md) - VC Code Analysis - 16.8 での新しい規則に関する追加
- [C33020](../code-quality/c33020.md) - VC Code Analysis - 16.8 での新しい規則に関する追加
- [C33022](../code-quality/c33022.md) - VC Code Analysis - 16.8 での新しい規則に関する追加

### <a name="updated-articles"></a>更新された記事

- [`C6262`](../code-quality/c6262.md) - cpp-docs.zh-tw 問題 20 への対処
- [`C26497 USE_CONSTEXPR_FOR_FUNCTION`](../code-quality/c26497.md) - C26497 への例の追加
- [`C26496 USE_CONST_FOR_VARIABLE`](../code-quality/c26496.md) - C26496 への例の追加
- [`C26495 MEMBER_UNINIT`](../code-quality/c26495.md) - C26495 での例とリンクの更新
- [`C26483 STATIC_INDEX_OUT_OF_RANGE`](../code-quality/c26483.md) - C26483 への例の追加
- [`C26462 USE_CONST_POINTER_FOR_VARIABLE`](../code-quality/c26462.md) - C26462 への説明と例の追加
- [`C26461 USE_CONST_POINTER_ARGUMENTS:`](../code-quality/c26461.md) - C26461 への説明と例の追加
- [`C26460 USE_CONST_REFERENCE_ARGUMENTS`](../code-quality/c26460.md) - C26460 への説明と例の追加
- [`C26440 DECLARE_NOEXCEPT`](../code-quality/c26440.md) - C26440 に関する例とコア ガイドラインへのリンクの追加
- [`C26439 SPECIAL_NOEXCEPT`](../code-quality/c26439.md) - C26439 に関する例とコア ガイドラインへのリンクの追加
- [`C26436 NEED_VIRTUAL_DTOR`](../code-quality/c26436.md) - C26436 に関する例とコア ガイドラインへのリンクの追加
- [`C26408 NO_MALLOC_FREE`](../code-quality/c26408.md) - C26408 に関する例とコア ガイドラインへのリンクの追加
- [`C26401 DONT_DELETE_NON_OWNER`](../code-quality/c26401.md) - C26401 に関する例とコア ガイドラインへのリンクの追加
- [`C26494 VAR_USE_BEFORE_INIT`](../code-quality/c26494.md) - C26494 への例の追加
- [`C26493 NO_CSTYLE_CAST`](../code-quality/c26493.md) - C26493 への例の追加
- [`C26492 NO_CONST_CAST`](../code-quality/c26492.md) - C26492 への例の追加
- [`C26490 NO_REINTERPRET_CAST`](../code-quality/c26490.md) - C26490 への例の追加
- [`C26482 NO_DYNAMIC_ARRAY_INDEXING`](../code-quality/c26482.md) - C26482 への例の追加
- [`C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR`](../code-quality/c26471.md) - C26471 への例の追加
- [`C26466 NO_STATIC_DOWNCAST_POLYMORPHIC`](../code-quality/c26466.md) - C26466 への例の追加
- [`C26465 NO_CONST_CAST_UNNECESSARY`](../code-quality/c26465.md) - C26465 への例の追加
- [`C26447 DONT_THROW_IN_NOEXCEPT`](../code-quality/c26447.md) - C26447 への例の追加
- [`C26446 USE_GSL_AT`](../code-quality/c26446.md) - C26446 への例の追加
- [`C26434 DONT_HIDE_METHODS`](../code-quality/c26434.md) - C26434 への例の追加
- [`C26432 DEFINE_OR_DELETE_SPECIAL_OPS`](../code-quality/c26432.md) - C26432 への例の追加
- [`C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT`](../code-quality/c26402.md) - C26402 への例の追加
- [`C26409 NO_NEW_DELETE`](../code-quality/c26409.md) - C26409 への例の追加
- [`C26474 NO_IMPLICIT_CAST`](../code-quality/c26474.md) - 基本と派生のケースを明確にするための C26474 の更新
## <a name="linux-with-microsoft-c-in-visual-studio"></a>Linux と Visual Studio での Microsoft C++

### <a name="new-articles"></a>新しい記事

- [Visual Studio で Linux CMake プロジェクトを構成する](../linux/cmake-linux-configure.md)

### <a name="updated-articles"></a>更新された記事

- [Visual Studio で Linux MSBuild C++ プロジェクトを作成する](../linux/create-a-new-linux-project.md) - linux プロジェクトを作成するための手順の更新
- [ConnectionManager リファレンス](../linux/connectionmanager-reference.md) - コマンド modify と clean の追加
- [Visual Studio で Linux CMake プロジェクトを構成する](../linux/cmake-linux-configure.md) - 最新の UI を反映するための更新
- [Linux MSBuild プロジェクトのデプロイ、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md) - `GDB Path` の追加

## <a name="cc-compiler-and-tools-errors-and-warnings"></a>C/C++ のコンパイラとツールのエラーと警告

### <a name="new-articles"></a>新しい記事

- [コンパイラ警告 (レベル 4) C4388](../error-messages/compiler-warnings/c4388.md) - 警告 C4388 の追加、16.7 の警告の更新

### <a name="updated-articles"></a>更新された記事

- [コンパイラ警告 (レベル 3) C4018](../error-messages/compiler-warnings/compiler-warning-level-3-c4018.md) - 16.7 の警告の更新
- [コンパイラ警告 (レベル 4) C4389](../error-messages/compiler-warnings/compiler-warning-level-4-c4389.md) - 16.7 の警告の更新
- [コンパイラのバージョンによるコンパイラ警告](../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md) - 16.7 の警告の更新
- [コンパイラの警告 C4800 - C5999](../error-messages/compiler-warnings/compiler-warnings-c4800-through-c4999.md) - 16.7 の警告の更新
- [コンパイラ エラー C3381](../error-messages/compiler-errors-2/compiler-error-c3381.md) - cpp-docs 2493 への対処、解説と例の更新

## <a name="cc-compiler-intrinsics-and-assembly-language"></a>C/C++ コンパイラの組み込みとアセンブリ言語

### <a name="updated-articles"></a>更新された記事

- [Visual Studio の C++ 準拠の強化](../overview/cpp-conformance-improvements.md) - 16.8 リリース ノートの更新
- [Microsoft C/C++ のヘルプとコミュニティ](../overview/visual-cpp-help-and-community.md) - DevCom および Microsoft Docs の Q&A リンクの更新
- [Visual Studio での C++](../overview/visual-cpp-in-visual-studio.md) - DevCom および Microsoft Docs の Q&A リンクの更新
- [Microsoft C++ 言語の準拠表](../overview/visual-cpp-language-conformance.md) - C++20 ライブラリ準拠の表の更新、16.7 の言語機能の表の更新

## <a name="c-in-visual-studio"></a>Visual Studio での C++

### <a name="updated-articles"></a>更新された記事

- [`__restrict`](../cpp/extension-restrict.md)
- [if-else ステートメント (C++)](../cpp/if-else-statement-cpp.md) - `if/else` の文法に関する説明の追加
- [`union`](../cpp/unions.md) - コード スニペットの修正

## <a name="cc-projects-and-build-systems"></a>C/C++ のプロジェクトとビルド システム

### <a name="new-articles"></a>新しい記事

- [`.vcxproj` ファイルとワイルドカード](../build/reference/vcxproj-files-and-wildcards.md)
- [`/headerUnit` (ヘッダー ユニット IFC の使用)](../build/reference/headerunit.md)
- [`/module:exportHeader` (ヘッダー ユニットの作成)](../build/reference/module-exportheader.md)
- [`/module:reference` (名前付きモジュール IFC の使用)](../build/reference/module-reference.md)
- [`/translateInclude` (インクルード ディレクティブをインポート ディレクティブに変換する)](../build/reference/translateinclude.md)
- [`/Zc:preprocessor` (プリプロセッサ準拠モードの有効化)](../build/reference/zc-preprocessor.md)

### <a name="updated-articles"></a>更新された記事

- [`/permissive-` (標準への準拠)](../build/reference/permissive-standards-conformance.md) - 16.8 リリース ノートの更新
- [`/clr` (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md) - `/clr` に関する説明の追加
- [pgosweep](../build/pgosweep.md) - より多くの pgosweep オプションの追加
- [`__declspec(dllimport)` を使用してデータをインポートする](../build/importing-data-using-declspec-dllimport.md) - 例の更新

## <a name="c-porting-and-upgrade-guide"></a>C++ の移植とアップグレードに関するガイド

### <a name="updated-articles"></a>更新された記事

- [方法: ユニバーサル Windows プラットフォーム アプリで既存の C++ コードを使用する](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md) - 明確化のための修正と、例の更新

## <a name="c-standard-library-stl-reference"></a>C++ 標準ライブラリ (STL) リファレンス

### <a name="new-articles"></a>新しい記事

- [`<bit>`](../standard-library/bit.md)
- [`<bit>` 関数](../standard-library/bit-functions.md)
- [`endian` 列挙型](../standard-library/bit-enum.md)

### <a name="updated-articles"></a>更新された記事

- [`<ios>` typedef](../standard-library/ios-typedefs.md) - GitHub #2514 に従った例の更新
- [`basic_string` クラス](../standard-library/basic-string-class.md) - `_starts_with()` と `ends_with()` の追加
- [`ios_base Class`](../standard-library/ios-base-class.md)
- [`map` クラス](../standard-library/map-class.md)
- [`multimap` クラス](../standard-library/multimap-class.md) - `contains()` の追加
- [`multiset` クラス](../standard-library/multiset-class.md) - `contains()` の追加
- [`set` クラス](../standard-library/set-class.md) - `contains()` の追加
- [`unordered_map` クラス](../standard-library/unordered-map-class.md) - `contains()` の追加
- [`unordered_multimap` クラス](../standard-library/unordered-multimap-class.md) - `contains()` の追加
- [`unordered_multiset` クラス](../standard-library/unordered-multiset-class.md) - `contains()` の追加
- [`unordered_set` クラス](../standard-library/unordered-set-class.md) - `contains()` の追加
- [`basic_string_view` クラス](../standard-library/basic-string-view-class.md) - `starts_with()` と `ends_with()` の追加
- [`<bit>` 関数](../standard-library/bit-functions.md) -`nodiscard` 構文の更新

## <a name="community-contributors"></a>コミュニティの共同作成者

上記の期間中、C++、C、アセンブラに関するドキュメントに協力していただいた方々です。 ご協力に感謝いたします。 投稿方法については、「[Microsoft Docs 共同作成者ガイド概要](/contribute/)」を参照してください。

- [yecril71pl](https://github.com/yecril71pl) - Christopher Yeleighton (4)
- [definedrisk](https://github.com/definedrisk) - Ben (3)
- [BeardedFish](https://github.com/BeardedFish) - Darian B. (1)
- [codevenkat](https://github.com/codevenkat) (1)
- [eltociear](https://github.com/eltociear) - Ikko Ashimine (1)
- [fsb4000](https://github.com/fsb4000) - Igor Zhukov (1)
- [Jaiganeshkumaran](https://github.com/Jaiganeshkumaran) - Jaiganesh Kumaran (1)
- [jogo-](https://github.com/jogo-) (1)
- [justanotheranonymoususer](https://github.com/justanotheranonymoususer) (1)
- [matrohin](https://github.com/matrohin) - Dmitry Matrokhin (1)
- [mhemmit](https://github.com/mhemmit) (1)
- [MSDN-WhiteKnight](https://github.com/MSDN-WhiteKnight) - MSDN.WhiteKnight (1)
- [OdinTemple](https://github.com/OdinTemple) - Odin Temple (1)
- [r00tdr4g0n](https://github.com/r00tdr4g0n) - r00tdr4g0n (1)
- [sebkraemer](https://github.com/sebkraemer) - Sebastian Krämer (1)
- [vtjnash](https://github.com/vtjnash) - Jameson Nash (1)
- [Youssef1313](https://github.com/Youssef1313) - Youssef Victor (1)
- [zecozephyr](https://github.com/zecozephyr) - Jonathan Bailey (1)
---
description: 詳細については、「メイクファイル前処理ディレクティブ」を参照してください。
title: メイクファイルのプリプロセス ディレクティブ
ms.date: 08/11/2019
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
ms.openlocfilehash: 7c394e3547044be661fea5a8ec86f05a3b93e967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138073"
---
# <a name="makefile-preprocessing-directives"></a>メイクファイルのプリプロセス ディレクティブ

プリプロセスディレクティブでは、大文字と小文字は区別されません。 最初の感嘆符 (!) は、行の先頭に置く必要があります。 インデントの場合は、感嘆符の後に0個以上の空白またはタブを表示できます。

- `!CMDSWITCHES` { `+` &#124; `-` }*オプション* ...

   各 *オプション* をオンまたはオフにします。 スペースまたはタブは、または演算子の前に指定する必要があります `+` `-` 。演算子と [オプションの文字](running-nmake.md#nmake-options)の間には使用できません。 文字は大文字と小文字が区別されず、スラッシュ () なしで指定され `/` ます。 一部のオプションを有効にし、他のオプションを無効にするには、の個別の仕様を使用し `!CMDSWITCHES` ます。

   メイクファイルで使用できるのは、/D、/I、/N、および/S だけです。 Tools.ini では、/F、/HELP、/NOLOGO、/X、/? 以外のすべてのオプションを使用できます。 Description ブロックで指定された変更は、次の説明ブロックまで有効になりません。 このディレクティブは、 **Makeflags** を更新します。 **Makeflags** が指定されている場合、再帰中に変更が継承されます。

- `!ERROR`*テキスト*

   エラー U1050 に *テキスト* を表示し、/K、/i、 `.IGNORE` 、、 `!CMDSWITCHES` またはダッシュ ( `-` ) のコマンド修飾子が使用されている場合でも、NMAKE を停止します。 *テキスト* の前のスペースまたはタブは無視されます。

- `!MESSAGE`*テキスト*

   *テキスト* を標準出力に表示します。 *テキスト* の前のスペースまたはタブは無視されます。

- `!INCLUDE` [ `<` ] *ファイル名* [ `>` ]

   *ファイル名* をメイクファイルとして読み取り、現在のメイクファイルで続行します。 NMAKE は、指定されたディレクトリまたは現在のディレクトリの *ファイル名* を最初に検索し、親メイク *ファイル* のディレクトリを再帰的に検索します。次に、filename が山かっこ () で囲まれている場合は、 `< >` **include** マクロで指定されたディレクトリ内で、最初は include 環境変数に設定されます。 `.SUFFIXES`設定、 `.PRECIOUS` 、および推論規則を再帰的なメイクメイクに渡す場合に便利です。

- `!IF`*constant_expression*

   との間のステートメントを処理し `!IF` 、 `!ELSE` `!ENDIF` *constant_expression* が0以外の値に評価される場合はを処理します。

- `!IFDEF` *macroname*

   と次の間のステートメントを処理し `!IFDEF` `!ELSE` `!ENDIF` ます。また、 *macroname* が定義されている場合はを処理します。 Null マクロは定義されていると見なされます。

- `!IFNDEF` *macroname*

   との間のステートメントを処理し `!IFNDEF` `!ELSE` `!ENDIF` ます。また、 *macroname* が定義されていない場合はを処理します。

- `!ELSE` [ `IF` *constant_expression* &#124; `IFDEF` *macroname* &#124; `IFNDEF` *macroname*]

   `!ELSE` `!ENDIF` 前の `!IF` 、 `!IFDEF` 、またはステートメントが0に評価された場合、との間のステートメントを処理し `!IFNDEF` ます。 省略可能なキーワードを使うと、前処理をさらに制御できます。

- `!ELSEIF`

   `!ELSE IF` と同義。

- `!ELSEIFDEF`

   `!ELSE IFDEF` と同義。

- `!ELSEIFNDEF`

   `!ELSE IFNDEF` と同義。

- `!ENDIF`

   `!IF`、 `!IFDEF` 、またはブロックの末尾をマークし `!IFNDEF` ます。 同じ行の後のテキスト `!ENDIF` は無視されます。

- `!UNDEF` *macroname*

   *Macroname* を未定義にします。

## <a name="see-also"></a>関連項目

- [メイクファイルのプリプロセス](makefile-preprocessing.md)

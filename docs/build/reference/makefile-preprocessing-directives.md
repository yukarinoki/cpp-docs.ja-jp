---
title: メイクファイルのプリプロセス ディレクティブ
ms.date: 06/14/2018
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
ms.openlocfilehash: 0945d0e1c149b7e1ab31b0dbbd5003f8b15a1e4d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826781"
---
# <a name="makefile-preprocessing-directives"></a>メイクファイルのプリプロセス ディレクティブ

プリプロセス ディレクティブは大文字小文字が区別されません。 初期の感嘆符 (!) する必要があります、行の先頭に表示されます。 0 以上のスペースまたはタブは、インデント、感嘆符の後に表示できます。

- **!CMDSWITCHES** {**+** &#124; **-**}*option* ...

   それぞれに*オプション*オンまたはオフを一覧表示します。 前にスペースまたはタブを表示する必要があります、+ または - 演算子。演算子間なし に表示できる、[オプション文字](nmake-options.md)します。 文字が小文字は区別されず、スラッシュ (/) なしで指定されます。 一部のオプションおよび他のユーザーを無効には、個別の仕様を使用して、 **!CMDSWITCHES**します。

   のみの/D/メイクファイルでは、/N、および/S を使用できます。 /F、/HELP、/NOLOGO を除くすべてのオプションは許可 tools.ini、/、X と/ですか。 記述ブロックで指定した変更は次の記述ブロックされるまで有効になりません。 このディレクティブを更新**MAKEFLAGS**; 場合、再帰中に変更が継承される**MAKEFLAGS**を指定します。

- **!エラー** *テキスト*

   表示*テキスト*エラー U1050、し、停止 (nmake の)、偶数の場合に/K、/、**します。無視**、 **!CMDSWITCHES**、またはダッシュ (-) のコマンド修飾子を使用します。 スペースまたはタブの前に*テキスト*は無視されます。

- **!メッセージ** *テキスト*

   表示*テキスト*標準出力に出力します。 スペースまたはタブの前に*テキスト*は無視されます。

- **!INCLUDE** [ **\<** ] *filename* [ **>** ]

   読み取り*filename*メイクファイルをし、続けて現在のメイクファイルを使用します。 (Nmake の) 検索*filename*指定されているか、現在のディレクトリで次のいずれかのディレクトリを再帰的に親メイクファイル、次に場合、 *filename*山かっこで囲まれた (\<>)、によって指定されたディレクトリで、 **INCLUDE**マクロで、最初は、INCLUDE 環境変数に設定します。 渡す便利な**します。サフィックス**設定、**します。貴重な**、および再帰メイクファイルに推論規則。

- **!IF** *constant_expression*

   ステートメントの間での処理 **!IF**と次の **!ELSE**または **!ENDIF**場合*constant_expression* 0 以外の値に評価されます。

- **!IFDEF** *マクロ名*

   ステートメントの間での処理 **!IFDEF**と次の **!ELSE**または **!ENDIF**場合*macroname*が定義されています。 Null マクロを定義すると見なされます。

- **!IFNDEF** *マクロ名*

   ステートメントの間での処理 **!IFNDEF**と次の **!ELSE**または **!ENDIF**場合*macroname*が定義されていません。

- **!ELSE** [**IF** *constant_expression* &#124; **IFDEF** *macroname* &#124; **IFNDEF** *macroname*]

   ステートメントの間での処理 **!ELSE**と次の **!ENDIF**場合する前に、 **!IF**、 **!IFDEF**、または **!IFNDEF**ステートメントが 0 に評価されます。 省略可能なキーワードの前処理のコントロールをさらに与えます。

- **!ELSEIF**

   シノニム **!ELSE IF**します。

- **!ELSEIFDEF**

   シノニム **!他の IFDEF**します。

- **!ELSEIFNDEF**

   シノニム **!他の IFNDEF**します。

- **!ENDIF**

   終了をマークする **!IF**、 **!IFDEF**、または **!IFNDEF**ブロックします。 任意のテキストの後 **!ENDIF**同じ行には無視されます。

- **!UNDEF** *マクロ名*

   未定義に*macroname*します。

## <a name="see-also"></a>関連項目

- [メイクファイルのプリプロセス](makefile-preprocessing.md)
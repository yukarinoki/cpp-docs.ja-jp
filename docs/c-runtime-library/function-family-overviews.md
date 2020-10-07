---
title: 関数ファミリの概要
description: ファミリ別の Microsoft C ランタイム関数の概要を説明します。
ms.date: 10/05/2020
ms.assetid: b05a2755-9d11-4ea9-ab97-d00a4e872e16
ms.openlocfilehash: de5192cd03c3821afc646241d75a3e8c6c8c12e3
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806514"
---
# <a name="function-family-overview"></a>関数ファミリの概要

このセクションでは、関数ファミリ別の C ランタイムライブラリルーチンの一覧を示します。

## <a name="crt-library-routine-families"></a>CRT ライブラリのルーチンファミリ

[_exec、_wexec](exec-wexec-functions.md)\
新しいプロセスを読み込んで実行する関数。

[ファイル名検索関数](filename-search-functions.md)\
指定されたファイル名を検索し、検索を終了する関数。

[およびの書式指定構文 `printf``wprintf`](format-specification-syntax-printf-and-wprintf-functions.md)\
およびの書式指定文字列と引数について説明し `printf` `wprintf` ます。

[書式指定フィールド文字: `scanf` および `wscanf`](format-specification-fields-scanf-and-wscanf-functions.md)\
関数ファミリ全体の入力ストリームを解析するための書式指定フィールドについて説明し `scanf` ます。

[`is`、 `isw` 関数](is-isw-routines.md)\
大文字、ASCII、数字、句読点などの文字をテストするための関数。

[`_ismbb` 関数](ismbb-routines.md)\
アルファ文字、空白文字、印刷文字などを表す整数値をテストするための関数。

[`_ismbc` 関数](ismbc-routines.md)\
マルチバイト文字がアルファベット文字、空白文字、印刷文字などを表すかどうかをテストする関数。

[演算子 `delete` (CRT)](delete-operator-crt.md)\
Visual Studio 2013 以降では、ユニバーサル C ランタイム (UCRT) は、C++ 固有の operator delete 関数をサポートしなくなりました。 これは、C++ 標準ライブラリの一部になっています。

[演算子 `new` (CRT)](new-operator-crt.md)\
Visual Studio 2013 以降では、ユニバーサル C ランタイム (UCRT) は、C++ 固有の operator new 関数をサポートしなくなりました。 これは、C++ 標準ライブラリの一部になっています。

[`printf` 位置指定パラメーター関数](printf-p-positional-parameters.md)\
位置指定パラメーターは、書式指定文字列のフィールドに代入される引数の数で指定します。

[`scanf` 型フィールド文字](scanf-type-field-characters.md)\
型文字は、関連付けられている引数が、などの `scanf` セキュリティで保護されたバージョンを含む、関数ファミリのいずれかの文字、文字列、または数値として解釈されるかどうかを決定し `scanf_s` ます。

[`scanf` 幅の指定](scanf-width-specification.md)\
Width フィールドは、そのフィールドに対して読み取る最大文字数を制御する正の10進整数です。 などの `scanf` セキュリティで保護されたバージョンを含む関数ファミリのいずれかに適用され `scanf_s` ます。

[_spawn, _wspawn 関数](spawn-wspawn-functions.md)\
新しいプロセスを作成して実行する関数。

[`strcoll` 関数](strcoll-functions.md)\
`strcoll`関数と `wcscoll` 関数は、 `LC_COLLATE` ロケールコードページのカテゴリの設定に従って2つの文字列を比較します。

[文字列から数値への関数](string-to-numeric-value-functions.md)\
`strtod`関数ファミリは、null で終わる文字列を数値に変換します。

[`vprintf` 関数](vprintf-functions.md)\
関数は、 `vprintf` 引数リストへのポインターを受け取り、書式設定し、結果を指定された出力先に書き込みます。 これらの関数は、実行されるパラメーターの検証、ワイドまたは1バイト文字列、出力先、および書式設定文字列でパラメーターを使用する順序を指定する場合とで異なります。

## <a name="see-also"></a>参照

[C ランタイムライブラリリファレンス](c-run-time-library-reference.md)
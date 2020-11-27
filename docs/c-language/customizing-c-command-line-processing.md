---
title: C のコマンド ライン処理のカスタマイズ
description: ランタイムのスタートアップ コードで `main` 関数の引数と環境パラメーターの処理を抑制する方法。
ms.date: 11/19/2020
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.openlocfilehash: fc306172491cd401caeecb3c87c0711f8b4ef911
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483296"
---
# <a name="customizing-c-command-line-processing"></a>C のコマンド ライン処理のカスタマイズ

プログラムがコマンド ライン引数を受け取らない場合は、コマンド ライン処理ルーチンを抑制して領域を少し節約できます。 その使用を抑制するには、 *`noarg.obj`* ファイルを (`main`、`wmain` どちらの場合でも) **`/link`** コンパイラ オプションまたは **`LINK`** コマンド ラインに含めます。

同様に、 *`envp`* 引数を使用して環境のテーブルにアクセスしない場合は、内部の環境処理ルーチンを抑制できます。 その使用を抑制するには、 *`noenv.obj`* ファイルを (`main`、`wmain` どちらの場合でも) **`/link`** コンパイラ オプションまたは **`LINK`** コマンド ラインに含めます。

ランタイムのスタートアップ リンカー オプションの詳細については、「[リンク オプション](../c-runtime-library/link-options.md)」を参照してください。

プログラムによって、C ランタイム ライブラリの `spawn` または `exec` ファミリのルーチンが呼び出されることがあります。 その場合は、親プロセスから子プロセスに環境を渡すために環境処理ルーチンが使用されるため、抑制しないでください。

## <a name="see-also"></a>関連項目

[`main` 関数とプログラム実行](../c-language/main-function-and-program-execution.md)\
[リンク オプション](../c-runtime-library/link-options.md)。

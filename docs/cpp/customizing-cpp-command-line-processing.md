---
title: C++ コマンド ライン処理のカスタマイズ
ms.date: 11/04/2016
f1_keywords:
- _setenvp
- _setargv
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
ms.openlocfilehash: 1541840521695658b5c4d809ba7e11767b1330a2
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857555"
---
# <a name="customizing-c-command-line-processing"></a>C++ コマンド ライン処理のカスタマイズ

**Microsoft 固有の仕様**

プログラムがコマンド ラインの引数を受け取らない場合は、コマンド ライン処理を実行するライブラリ ルーチンの使用を制約することで、領域を節約できます。 このルーチンは `_setargv` と呼ばれ、[ワイルドカードの展開](../cpp/wildcard-expansion.md)で説明されています。 使用しないようにするには、`main` 関数を含むファイルで何も実行しないルーチンを定義し、`_setargv`という名前を指定します。 `_setargv`の定義によって `_setargv` の呼び出しが満たされ、ライブラリのバージョンが読み込まれません。

同様に、`envp` 引数を使用して環境テーブルにアクセスしない場合は、環境処理ルーチン `_setenvp`の代わりに独自の空のルーチンを使用することができます。 `_setargv` 関数と同様に、`_setenvp` を**extern "C"** として宣言する必要があります。

プログラムによって、C ランタイムライブラリで `spawn` または `exec` のルーチンファミリが呼び出される場合があります。 この場合、このルーチンは親プロセスから子プロセスに環境を渡すために使用されるため、環境処理ルーチンを抑制しないでください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[main: プログラムの起動](../cpp/main-program-startup.md)
---
title: リンカ ツール エラー LNK1211 |Microsoft ドキュメント
ms.date: 12/05/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1211
dev_langs:
- C++
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57948556ae7b94b9a1788b7cb4453646b5b504f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300385"
---
# <a name="linker-tools-error-lnk1211"></a>リンカ ツール エラー LNK1211

> プリコンパイル済みの型情報が見つかりませんでした。'*filename*' リンクしていないか、上書き

*Filename*オブジェクト ファイルを使用してコンパイル[/Yc](../../build/reference/yc-create-precompiled-header-file.md)LINK コマンドで指定されていない、または上書きされました。

プリコンパイル済みヘッダーを使用するデバッグ ライブラリを作成する場合を指定して **/Yc**と[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)、Visual C デバッグ情報を含むプリコンパイル済みのオブジェクト ファイルが生成されます。 ライブラリに、プリコンパイル済みのオブジェクト ファイルを格納する場合のみにエラーが発生する、ライブラリを使用して、実行可能イメージを構築、参照されているオブジェクト ファイルにはプリコンパイル済みのオブジェクト ファイルで定義された関数のいずれかに推移的な参照はありません。

このような状況を回避する 2 つの方法はあります。

- 指定して、 [/yd への取り込み](../../build/reference/yd-place-debug-information-in-object-file.md)コンパイラ オプションは、プリコンパイル済みヘッダーからデバッグ情報の各オブジェクト モジュールに追加します。 一般にアプリケーションをリンクするために必要な時間を向上できるラージ オブジェクト モジュールが生成されるので、このメソッドは小さいことをお勧めします。

- 指定[/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)し、関数定義を含まないプリコンパイル済みヘッダー ファイルを作成するときに、任意の文字列の名前を渡します。 プリコンパイル済みのオブジェクト ファイルでシンボルを作成して、プリコンパイル済みのオブジェクト ファイルに関連付けられているプリコンパイル済みヘッダー ファイルを使用している各オブジェクト ファイルでそのシンボルへの参照を出力する、コンパイラに指示します。

持つモジュールをコンパイルするときに **/Yc**と **/Yl**、シンボルを作成するようなコンパイラ`__@@_PchSym_@00@...@symbol_name`ここで、省略記号 (...) コンパイラによって生成された文字列を表しに格納、モジュールのオブジェクト。 このプリコンパイル済みヘッダーを使用してコンパイルする任意のソース ファイルは、リンカーはオブジェクト モジュールなどのライブラリからのデバッグ情報に、指定した記号を指します。

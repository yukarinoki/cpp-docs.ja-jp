---
title: assert 関数によって出力される診断
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: 330c694b53957cab2e44da7cb8b52031c33fb5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549046"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert 関数によって出力される診断

**ANSI 4.2** **assert** 関数が印刷する診断と関数の終了動作

**assert** 関数は診断メッセージを表示し、式が false (0) の場合に **abort** ルーチンを呼び出します。 診断メッセージにフォームがあります

> **アサーションに失敗しました**: <em>expression</em>**, ファイル** <em>filename</em>**, 行** *linenumber*

ここで、*filename* はソース ファイルの名前であり、*linenumber* はソース ファイルで失敗したアサーションの行番号です。 *expression* が true の場合 (ゼロ以外)、アクションは発生しません。

## <a name="see-also"></a>参照

[ライブラリ関数](../c-language/library-functions.md)
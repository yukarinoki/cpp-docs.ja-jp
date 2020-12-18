---
description: '詳細情報: assert 関数によって出力される診断'
title: assert 関数によって出力される診断
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: cab4f6dfd2cab7d4b46486a103b39abb6ca17005
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186793"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert 関数によって出力される診断

**ANSI 4.2** **assert** 関数が印刷する診断と関数の終了動作

**assert** 関数は診断メッセージを表示し、式が false (0) の場合に **abort** ルーチンを呼び出します。 診断メッセージにフォームがあります

> **アサーションに失敗しました**: <em>expression</em> **, ファイル** <em>filename</em> **, 行** *linenumber*

ここで、*filename* はソース ファイルの名前であり、*linenumber* はソース ファイルで失敗したアサーションの行番号です。 *expression* が true の場合 (ゼロ以外)、アクションは発生しません。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)

---
title: ワイルドカードの展開
ms.date: 11/04/2016
f1_keywords:
- _setargv
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
ms.openlocfilehash: 2d495f94f2e3fb7b88d235edc7b98f8e90775393
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209516"
---
# <a name="wildcard-expansion"></a>ワイルドカードの展開

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

コマンド ラインでファイル名とパスの引数を指定するときに、ワイルドカード (疑問符 (?) およびアスタリスク (*)) を使用できます。

コマンドライン引数はというルーチンによって処理される`_setargv`(または`_wsetargv`ワイド文字環境で)、ワイルドカードの展開で個別の文字列に既定ではありません、`argv`文字列配列。 ワイルドカードの展開の有効化の詳細についてを参照してください[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[main:プログラムの起動](../cpp/main-program-startup.md)
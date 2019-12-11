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
ms.openlocfilehash: 1fdea297bb45a06a08bde4f63f90eabef6ddb539
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857178"
---
# <a name="wildcard-expansion"></a>ワイルドカードの展開

**Microsoft 固有の仕様**

コマンド ラインでファイル名とパスの引数を指定するときに、ワイルドカード (疑問符 (?) およびアスタリスク (*)) を使用できます。

コマンドライン引数は `_setargv` (ワイド文字環境では `_wsetargv`) と呼ばれるルーチンによって処理されます。既定では、ワイルドカードは `argv` 文字列配列内の個別の文字列に展開されません。 ワイルドカードの展開を有効にする方法の詳細については、「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[main: プログラムの起動](../cpp/main-program-startup.md)
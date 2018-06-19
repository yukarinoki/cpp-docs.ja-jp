---
title: ワイルドカードの展開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb58d5da479d686cac0d18c9d36e500bd6b5a632
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420651"
---
# <a name="wildcard-expansion"></a>ワイルドカードの展開
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 コマンド ラインでファイル名とパスの引数を指定するときに、ワイルドカード (疑問符 (?) およびアスタリスク (*)) を使用できます。  
  
 コマンドライン引数はというルーチンによって処理される **_setargv** (または **_wsetargv**ワイド文字環境で)、既定では展開されませんワイルドカード、で個別の文字列に`argv`文字列配列。 参照してワイルドカードの展開を有効にする方法の詳細については、[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)
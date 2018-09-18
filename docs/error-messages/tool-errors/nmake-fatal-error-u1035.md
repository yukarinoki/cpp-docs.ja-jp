---
title: NMAKE の致命的なエラー U1035 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0383bf4742d637d669070efa5370ebda0c7ab159
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019862"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE の致命的なエラー U1035

構文エラー: 予想 ':' または '=' 区切り記号

いずれかにコロン (**:**) または等号 (=) (**=**) が必要です。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ターゲットの後ろにコロンがありません。

1. 1 文字のターゲットの後にコロンと a:) などの領域がありません。 NMAKE でドライブの指定と、解釈されます。

1. 推論規則の後ろにコロンがありません。

1. マクロ定義は、等号 (=) で後にありませんでした。

1. 後ろに円記号の文字 (**\\**) に新しい行にコマンドを引き続き使用されました。

1. NMAKE の構文規則に従っていない文字列が表示されます。

1. ワード プロセッサでメイクファイルが書式設定されます。
---
title: BSCMAKE エラー BK1514 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1514
dev_langs:
- C++
helpviewer_keywords:
- BK1514
ms.assetid: 7c7e2504-a490-44ab-bb1f-47385ee2f4b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20f66c5c48547e92aef00568d5488a6293303be1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094716"
---
# <a name="bscmake-error-bk1514"></a>BSCMAKE エラー BK1514

すべての。SBR ファイルが切り捨てファイル名に見つかりませんでした。

指定されている更新プログラムの .sbr ファイルのいずれも、元の参照情報 (.bsc) ファイルの一部であった。 このエラーの原因となった .sbr ファイルの名前を検索するには、読み取り、 [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md)前に警告します。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. .Sbr または .bsc ファイルに指定されたファイル名が間違っています。

1. 破損した .bsc ファイルには、BSCMAKE の処理を再構築が必要です。
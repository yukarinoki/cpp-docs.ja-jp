---
title: BSCMAKE の警告 BK4502 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4502
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4142993b3f4f5bda2b3e4ce322aa26d7beca8584
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056327"
---
# <a name="bscmake-warning-bk4502"></a>BSCMAKE の警告 BK4502

切り捨てられます。SBR ファイル 'filename' のファイル名ではなく

.Bsc ファイルの一部ではない長さ 0 の .sbr ファイルが更新中に指定されました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 指定されたファイル名が間違っています。

1. ファイルが削除されました。 (エラー [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md)結果です)。

1. フル ビルドを実行するを必要とするファイルが壊れています。
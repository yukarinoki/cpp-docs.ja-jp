---
title: BSCMAKE の警告 BK4502
ms.date: 11/04/2016
f1_keywords:
- BK4502
helpviewer_keywords:
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
ms.openlocfilehash: 1c5204239909e579fa93006e245e3841b7fb64eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197458"
---
# <a name="bscmake-warning-bk4502"></a>BSCMAKE の警告 BK4502

切れ..SBR ファイル ' filename ' がファイル名にありません。

最初は .bsc ファイルの一部ではない、長さが0の .sbr ファイルが更新中に指定されました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 指定されたファイル名が正しくありません。

1. ファイルが削除されました。 (エラー [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md)の結果。)

1. ファイルが破損しています。 BSCMAKE で完全なビルドを実行する必要があります。

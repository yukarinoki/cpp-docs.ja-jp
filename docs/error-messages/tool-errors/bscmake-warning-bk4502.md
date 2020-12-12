---
description: 詳細については、「BSCMAKE Warning BK4502」を参照してください。
title: BSCMAKE の警告 BK4502
ms.date: 11/04/2016
f1_keywords:
- BK4502
helpviewer_keywords:
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
ms.openlocfilehash: 97fb7745353a92704fb624a2782a91ea63dc532a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237882"
---
# <a name="bscmake-warning-bk4502"></a>BSCMAKE の警告 BK4502

切れ..SBR ファイル ' filename ' がファイル名にありません。

最初は .bsc ファイルの一部ではない、長さが0の .sbr ファイルが更新中に指定されました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 指定されたファイル名が正しくありません。

1. ファイルが削除されました。 (エラー [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) の結果。)

1. ファイルが破損しています。 BSCMAKE で完全なビルドを実行する必要があります。

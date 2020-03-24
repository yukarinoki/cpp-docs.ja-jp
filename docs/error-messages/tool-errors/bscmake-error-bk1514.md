---
title: BSCMAKE エラー BK1514
ms.date: 11/04/2016
f1_keywords:
- BK1514
helpviewer_keywords:
- BK1514
ms.assetid: 7c7e2504-a490-44ab-bb1f-47385ee2f4b0
ms.openlocfilehash: 14f74bba69db5bf3e02aecedd4540ef8a90d576b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197627"
---
# <a name="bscmake-error-bk1514"></a>BSCMAKE エラー BK1514

すべての.SBR ファイルが切り捨てられました。ファイル名に見つかりませんでした。

更新プログラムに指定された .sbr ファイルは、元のブラウザー情報 (.bsc) ファイルの一部ではありませんでした。 このエラーの原因となった .sbr ファイルの名前を確認するには、その前にある[BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md)の警告を参照してください。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. .Sbr または .bsc に指定されたファイル名が正しくありません。

1. .Bsc ファイルが破損しています。再構築するには BSCMAKE が必要です。

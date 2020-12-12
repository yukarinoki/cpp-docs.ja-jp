---
description: '詳細情報: 別のテーブルに行への参照が含まれている場合に列を更新する'
title: 別のテーブルに行への参照が含まれている場合に列を更新する
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 5c4562aaaa435c9745bedd146c04c98158d50cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272618"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>行への参照が別のテーブルにある場合に列を更新する方法

プロバイダーによっては、行のどの列が変更されるかを検出できますが、多くのプロバイダーでは使用できません。 その結果、更新しようとしている行への参照があると、列を更新するとエラーが発生する可能性があります。 この問題を解決するには、変更する列だけを保持する別のアクセサーを作成します。 そのアクセサーの番号をに渡し `SetData` ます。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)

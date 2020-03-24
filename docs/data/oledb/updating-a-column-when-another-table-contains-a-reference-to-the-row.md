---
title: 別のテーブルに行への参照が含まれている場合に列を更新する
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 95cddfd5f030c7bd8d1220cf040de4bc5a883226
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209483"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>行への参照が別のテーブルにある場合に列を更新する方法

プロバイダーによっては、行のどの列が変更されるかを検出できますが、多くのプロバイダーでは使用できません。 その結果、更新しようとしている行への参照があると、列を更新するとエラーが発生する可能性があります。 この問題を解決するには、変更する列だけを保持する別のアクセサーを作成します。 そのアクセサーの番号を `SetData`に渡します。

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)

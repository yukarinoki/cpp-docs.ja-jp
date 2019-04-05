---
title: 別のテーブルに行への参照が含まれている場合は、列を更新します
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 46de5f54a3ec6525f779a6b55a700429a2a84fef
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039216"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>行への参照が別のテーブルにある場合に列を更新する方法

一部のプロバイダーは列を行の変更で検出できますが、多くのプロバイダーのことはできません。 その結果、列を更新することができます、エラー発生を更新しようとしている行への参照がある場合。 この問題を解決するには、変更する列のみを保持している別のアクセサーを作成します。 そのアクセサーの数を渡して`SetData`します。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)
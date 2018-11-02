---
title: 'テクニカル ノート 47: データベース トランザクション要件の緩和'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: d609576c5ffda1a3ba8021e6a459943092c40e98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658836"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>テクニカル ノート 47: データベース トランザクション要件の緩和

MFC ODBC データベース クラスのトランザクション要件のように、このテクニカル ノートでは廃止されました。 データベース クラスがカーソルをレコード セットの後に保持されることを必須 MFC 4.2 では、前に、 **CommitTrans**または**ロールバック**操作。 ODBC ドライバーと DBMS がこのレベルのカーソル位置の保持をサポートしていない場合、データベース クラスは、有効にしていないトランザクション。

データベース クラスは、MFC の 4.2 以降では、カーソル位置の保持を要求する場合の制限を緩和しました。 ドライバーはそれらをサポートしている場合は、トランザクションを有効になります。 、の効果が今すぐ確認する必要があります、 **CommitTrans**または**ロールバック**オープンのレコード セットで操作します。 メンバー関数を参照してください。 [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior)と[CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior)詳細についてはします。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)


---
title: 'TN047: データベース トランザクション要件の緩和 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96f3116f503ffa0ffc461ea2c1a0bdaf8947a0be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427018"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>テクニカル ノート 47: データベース トランザクション要件の緩和

MFC ODBC データベース クラスのトランザクション要件のように、このテクニカル ノートでは廃止されました。 データベース クラスがカーソルをレコード セットの後に保持されることを必須 MFC 4.2 では、前に、 **CommitTrans**または**ロールバック**操作。 ODBC ドライバーと DBMS がこのレベルのカーソル位置の保持をサポートしていない場合、データベース クラスは、有効にしていないトランザクション。

データベース クラスは、MFC の 4.2 以降では、カーソル位置の保持を要求する場合の制限を緩和しました。 ドライバーはそれらをサポートしている場合は、トランザクションを有効になります。 、の効果が今すぐ確認する必要があります、 **CommitTrans**または**ロールバック**オープンのレコード セットで操作します。 メンバー関数を参照してください。 [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior)と[CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior)詳細についてはします。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)


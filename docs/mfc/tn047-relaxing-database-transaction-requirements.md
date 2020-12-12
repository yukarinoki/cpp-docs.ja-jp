---
description: '詳細については、「テクニカルノート 47: リラックスしたデータベーストランザクションの要件」を参照してください。'
title: 'テクニカル ノート 47: データベース トランザクション条件の緩和'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: 6f356db75df93466bc392e555246a363e6b52187
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215119"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>テクニカル ノート 47: データベース トランザクション条件の緩和

MFC ODBC データベースクラスのトランザクション要件について説明したこのテクニカルノートは、互換性のために残されています。 MFC 4.2 より前のデータベースクラスでは、 **CommitTrans** または **Rollback** 操作の後に、レコードセットでカーソルを保持する必要がありました。 ODBC ドライバーと DBMS がこのレベルのカーソルの保持をサポートしていない場合、データベースクラスではトランザクションが有効になりませんでした。

MFC 4.2 以降では、データベースクラスはカーソルの保持を必要とする制限を緩和しています。 トランザクションは、ドライバーでサポートされている場合に有効になります。 ただし、現在は、開いているレコードセットに対して、 **CommitTrans** または **Rollback** 操作の効果を確認する必要があります。 詳細については、メンバー関数 [CDatabase:: Getカーソル Commitbehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) と [CDatabase:: GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) を参照してください。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)

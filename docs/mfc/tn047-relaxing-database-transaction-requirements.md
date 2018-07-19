---
title: 'TN047: データベース トランザクション条件の緩和 |Microsoft ドキュメント'
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
ms.openlocfilehash: be5870efacb61d5c0bb74f85427c41f787d2edd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380935"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>テクニカル ノート 47: データベース トランザクション要件の緩和
MFC ODBC データベース クラスのトランザクションの要件を説明するには、このテクニカル ノートでは廃止されました。 データベース クラスがレコード セットの後にカーソルを保持することを必須 MFC 4.2 の前に、 **CommitTrans**または**ロールバック**操作します。 ODBC ドライバーと DBMS がこのレベルのカーソル位置の保存をサポートしていない場合、データベース クラスは、有効にしなかったトランザクションです。  
  
 MFC 4.2 以降では、データベース クラスではカーソル位置を保持する必要がという制限が緩和されてです。 ドライバーによってサポートされる場合、トランザクションを有効にされます。 、の効果が今すぐ確認する必要があります、 **CommitTrans**または**ロールバック**開いているレコード セットで操作します。 メンバー関数を参照してください[CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior)と[CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)


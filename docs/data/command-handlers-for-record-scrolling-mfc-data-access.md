---
title: レコード スクロール (MFC データ アクセス) のハンドラーをコマンド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03dec2e3eff0f61db5f4c8b7573400a589615b02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089380"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)
[CRecordView](../mfc/reference/crecordview-class.md)クラスには、既定のコマンドを次の標準コマンドの処理が用意されています。  
  
-   **ID_RECORD_MOVE_FIRST**  
  
-   **ID_RECORD_MOVE_LAST**  
  
-   **ID_RECORD_MOVE_NEXT**  
  
-   **ID_RECORD_MOVE_PREV**  
  
 `OnMove`メンバー関数は既定のコマンド レコード間を移動するすべての 4 つのコマンドの処理を提供します。 これらのコマンドが発行されると、RFX (または DFX) によってレコードセットのフィールドに新しいレコードが読み込まれ、DDX によってレコード フォームのコントロールに値が移動されます。 RFX については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../data/odbc/record-field-exchange-rfx.md)です。  
  
> [!NOTE]
>  標準的なレコード移動コマンドに関連付けられているユーザー インターフェイス オブジェクトには、必ずこれらの標準コマンド ID を使用してください。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビューのナビゲーションをサポートします。](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)
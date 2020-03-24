---
title: レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 8bbacd6625e846381d2bafc8133e8b36efe51b1a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213448"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)

[CRecordView](../mfc/reference/crecordview-class.md)クラスは、次の標準コマンドに対する既定のコマンド処理を提供します。

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

`OnMove` メンバー関数は、レコード間を移動する4つのすべてのコマンドに対して既定のコマンド処理を提供します。 これらのコマンドが発行されると、RFX (または DFX) によってレコードセットのフィールドに新しいレコードが読み込まれ、DDX によってレコード フォームのコントロールに値が移動されます。 RFX の詳細については、「[レコードフィールドエクスチェンジ (rfx)](../data/odbc/record-field-exchange-rfx.md)」を参照してください。

> [!NOTE]
>  標準的なレコード移動コマンドに関連付けられているユーザー インターフェイス オブジェクトには、必ずこれらの標準コマンド ID を使用してください。

## <a name="see-also"></a>参照

[レコードビューでのナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)

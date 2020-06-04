---
title: レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 14ef845c3029f1d9a30d257f91c1b33017b6ec8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336938"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)

[CRecordView](../mfc/reference/crecordview-class.md)クラスは、次の標準コマンドの既定のコマンド処理を提供します。

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

この`OnMove`メンバー関数は、レコードからレコードへ移動する 4 つのコマンドすべてについて、デフォルトのコマンド処理を提供します。 これらのコマンドが発行されると、RFX (または DFX) によってレコードセットのフィールドに新しいレコードが読み込まれ、DDX によってレコード フォームのコントロールに値が移動されます。 RFX の詳細については、「[レコード フィールド エクスチェンジ (RFX)」](../data/odbc/record-field-exchange-rfx.md)を参照してください。

> [!NOTE]
> 標準的なレコード移動コマンドに関連付けられているユーザー インターフェイス オブジェクトには、必ずこれらの標準コマンド ID を使用してください。

## <a name="see-also"></a>関連項目

[レコード ビュー内の移動](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)

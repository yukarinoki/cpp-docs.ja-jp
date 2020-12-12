---
description: 詳細については、「レコードスクロール用のコマンドハンドラー (MFC データアクセス)」を参照してください。
title: レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 03fce51e7b045df0ae5ad1ceb0fa99eb98d0b7c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181385"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)

[CRecordView](../mfc/reference/crecordview-class.md)クラスは、次の標準コマンドに対する既定のコマンド処理を提供します。

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

この `OnMove` メンバー関数は、レコード間を移動する4つのコマンドすべてに対して、既定のコマンド処理を提供します。 これらのコマンドが発行されると、RFX (または DFX) によってレコードセットのフィールドに新しいレコードが読み込まれ、DDX によってレコード フォームのコントロールに値が移動されます。 RFX の詳細については、「 [レコードフィールドエクスチェンジ (rfx)](../data/odbc/record-field-exchange-rfx.md)」を参照してください。

> [!NOTE]
> 標準的なレコード移動コマンドに関連付けられているユーザー インターフェイス オブジェクトには、必ずこれらの標準コマンド ID を使用してください。

## <a name="see-also"></a>関連項目

[レコード ビュー内の移動](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)

---
description: 詳細については、User-Interface オブジェクトとコマンド Id に関するページを参照してください。
title: ユーザー インターフェイス オブジェクトとコマンド ID
ms.date: 11/19/2018
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
ms.openlocfilehash: 142b72956e0a1b9e60ef48c7db325cd0ac822444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263622"
---
# <a name="user-interface-objects-and-command-ids"></a>ユーザー インターフェイス オブジェクトとコマンド ID

メニュー項目、ツールバーボタン、およびアクセラレータキーは、コマンドを生成できる "ユーザーインターフェイスオブジェクト" です。 このようなユーザーインターフェイスオブジェクトにはそれぞれ ID があります。 オブジェクトとコマンドに同じ ID を割り当てることによって、ユーザーインターフェイスオブジェクトをコマンドに関連付けます。 「 [メッセージ](../mfc/messages.md)」で説明されているように、コマンドは特別なメッセージとして実装されています。 次の図「フレームワークのコマンド」では、フレームワークがコマンドを管理する方法を示しています。 ユーザーインターフェイスオブジェクトがなどのコマンドを生成すると、 `ID_EDIT_CLEAR_ALL` アプリケーション内のいずれかのオブジェクトがコマンドを処理します。次の図では、ドキュメントオブジェクトの `OnEditClearAll` 関数がドキュメントのメッセージマップを介して呼び出されます。

![フレームワークにおけるコマンド](../mfc/media/vc385p1.gif "フレームワークにおけるコマンド") <br/>
フレームワークにおけるコマンド

次の図「フレームワークでのコマンドの更新」では、MFC がメニュー項目やツールバーボタンなどのユーザーインターフェイスオブジェクトを更新する方法を示しています。 メニューがドロップされる前、またはツールバーのボタンの場合はアイドルループ中に、MFC は update コマンドをルーティングします。 次の図では、ドキュメントオブジェクトは update コマンドハンドラーを呼び出して、 `OnUpdateEditClearAll` ユーザーインターフェイスオブジェクトを有効または無効にします。

![フレームワークでのコマンド更新](../mfc/media/vc385p2.png "フレームワークでのコマンド更新") <br/>
フレームワーク内のコマンド更新

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

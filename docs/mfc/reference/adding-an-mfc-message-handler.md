---
title: MFC メッセージ ハンドラーの追加
ms.date: 09/06/2019
f1_keywords:
- vc.codewiz.adding.mfc.msghandler
helpviewer_keywords:
- message handling [MFC], adding handlers
ms.assetid: 4251cfce-76ca-443d-bd2f-6303afa6d942
ms.openlocfilehash: bbd88225249ac18a2bb3ca4006e1edbe62fbddfc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371655"
---
# <a name="adding-an-mfc-message-handler"></a>MFC メッセージ ハンドラーの追加

[クラス ウィザード](mfc-class-wizard.md)または**CLass ビュー**の**プロパティ**ウィンドウを使用して、メッセージ ハンドラー (Windows メッセージを処理するメンバー関数) をクラスに追加し、Windows メッセージをメッセージ ハンドラーにマップできます。 また、ダイアログ[ボックス コントロールに対してイベント ハンドラを](../../windows/adding-event-handlers-for-dialog-box-controls.md)追加することもできます。

**クラス ウィザード**または **[プロパティ**] ウィンドウ **([クラス ビュー**] ) を使用してメッセージ処理関数とイベント処理関数を定義すると、メッセージ ディスパッチ テーブル (またはメッセージ マップ) とクラス ヘッダー ファイルを自動的に更新できます。

> [!NOTE]
> クラス ウィザードを使用して ATL クラスにメッセージ ハンドラーを追加できます。ただし、結果の一部は異なる場合があります。 詳細については、ATL のトピック ATL[メッセージ ハンドラーの追加を参照してください](../../atl/adding-an-atl-message-handler.md)。

## <a name="see-also"></a>関連項目

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[クラス各部へのジャンプ](../../ide/navigate-code-cpp.md)<br/>
[ダイアログ エディター](../../windows/dialog-editor.md)

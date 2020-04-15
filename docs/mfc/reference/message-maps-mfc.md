---
title: メッセージ マップ (MFC)
ms.date: 09/07/2019
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 8080becf1a1a153322bfd03cbd7006eaf2ce4e13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356575"
---
# <a name="message-maps-mfc"></a>メッセージ マップ (MFC)

このセクションでは、すべてのメッセージ[マッピング マクロ](../../mfc/reference/message-map-macros-mfc.md)とすべての[CWnd](../../mfc/reference/cwnd-class.md)メッセージ マップ エントリと、対応するメンバー関数プロトタイプを示します。

|カテゴリ|説明|
|--------------|-----------------|
|ON\_コマンド メッセージ ハンドラ|ユーザー`WM_COMMAND`メニューの選択またはメニュー アクセス キーによって生成されたメッセージを処理します。|
|[子ウィンドウ通知メッセージ ハンドラ](../../mfc/reference/child-window-notification-message-handlers.md)|子ウィンドウからの通知メッセージを処理します。|
|[WM_ メッセージ ハンドラー](../../mfc/reference/handlers-for-wm-messages.md)|などの`WM_``WM_PAINT`メッセージを処理します。|
|[ユーザー定義メッセージ ハンドラー](../../mfc/reference/user-defined-handlers.md)|ユーザー定義メッセージを処理します。|

(このリファレンスで使用する用語と規則については、「[メッセージ マップ相互参照の使用方法](../../mfc/reference/how-to-use-the-message-map-cross-reference.md)」を参照してください)。

Windows はメッセージ指向オペレーティング システムであることが理由で、Windows 環境向けのプログラミングの大部分にはメッセージ処理が関係しています。 キーストロークやマウス クリックなどのイベントが発生するたびに、そのイベントを処理する必要があるアプリケーションに対してメッセージが送信されます。

Microsoft Foundation Class ライブラリには、メッセージベースのプログラミングに最適化されたプログラミング モデルが用意されています。 このモデルでは、特定のクラスに対してどの関数がさまざまなメッセージを処理するかを指定した "メッセージ マップ" を使用します。 メッセージ マップには、どの関数がどのメッセージを処理するかを指定する 1 つ以上のマクロが含まれています。 たとえば、`ON_COMMAND` マクロを含むメッセージ マップは、次のように記述されることがあります。

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

`ON_COMMAND` マクロは、メニュー、ボタン、およびアクセラレータ キーによって生成されるコマンド メッセージを処理するために使用します。 [マクロ](../../mfc/reference/message-map-macros-mfc.md)は、次のマップに使用できます。

## <a name="windows-messages"></a>Windows メッセージ

- コントロールの通知

- ユーザー定義メッセージ

## <a name="command-messages"></a>コマンド メッセージ

- 登録済みのユーザー定義メッセージ

- ユーザー インターフェイス更新メッセージ

## <a name="ranges-of-messages"></a>メッセージの範囲

- コマンド

- ハンドラー メッセージの更新

- コントロールの通知

メッセージ マップ マクロは重要なマクロですが、通常は直接記述する必要はありません。 これは、メッセージ処理関数をメッセージに関連付けるために使用すると、[クラス ウィザード](mfc-class-wizard.md)によって自動的にメッセージ マップ エントリがソース ファイルに作成されるためです。 メッセージ マップ エントリを編集または追加する場合は、クラス ウィザードを使用できます。

> [!NOTE]
> クラス ウィザードは、メッセージ マップ範囲をサポートしていません。 これらのメッセージ マップ エントリは、独自に作成する必要があります。

ただし、メッセージ マップは、Microsoft Foundation Class ライブラリの重要な部分です。 これらが何を実行するかを理解する必要があり、そのためのドキュメントが用意されています。

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

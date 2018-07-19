---
title: メッセージ マップ (MFC) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d1479ac7cb119ef206f8c20b6fa53bf7017b8ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371713"
---
# <a name="message-maps-mfc"></a>メッセージ マップ (MFC)
このリファレンス」のセクションでは、すべて一覧表示[メッセージ マップ マクロ](../../mfc/reference/message-map-macros-mfc.md)すべてと[CWnd](../../mfc/reference/cwnd-class.md)メッセージ マップ エントリを対応するメンバーと共に関数のプロトタイプ。  
  
|カテゴリ|説明|  
|--------------|-----------------|  
|ON\_コマンド メッセージ ハンドラー|処理`WM_COMMAND`ユーザー メニュー選択またはメニュー アクセス キーによって生成されるメッセージ。|  
|[子ウィンドウの通知メッセージ ハンドラー](../../mfc/reference/child-window-notification-message-handlers.md)|子ウィンドウからの通知メッセージを処理します。|  
|[Wm _ メッセージ ハンドラー](../../mfc/reference/handlers-for-wm-messages.md)|処理`WM_`メッセージなど、`WM_PAINT`です。|  
|[ユーザー定義のメッセージ ハンドラー](../../mfc/reference/user-defined-handlers.md)|ユーザー定義メッセージを処理します。|  
  
 (用語とこのリファレンスで使用される規則の詳細については、次を参照してください[メッセージ マップ クロス リファレンスの使い方](../../mfc/reference/how-to-use-the-message-map-cross-reference.md)。)。  
  
 Windows はメッセージ指向オペレーティング システムであることが理由で、Windows 環境向けのプログラミングの大部分にはメッセージ処理が関係しています。 キーストロークやマウス クリックなどのイベントが発生するたびに、そのイベントを処理する必要があるアプリケーションに対してメッセージが送信されます。  
  
 Microsoft Foundation Class ライブラリには、メッセージベースのプログラミングに最適化されたプログラミング モデルが用意されています。 このモデルでは、特定のクラスに対してどの関数がさまざまなメッセージを処理するかを指定した "メッセージ マップ" を使用します。 メッセージ マップには、どの関数がどのメッセージを処理するかを指定する 1 つ以上のマクロが含まれています。 たとえば、`ON_COMMAND` マクロを含むメッセージ マップは、次のように記述されることがあります。  
  
 [!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]  
  
 `ON_COMMAND` マクロは、メニュー、ボタン、およびアクセラレータ キーによって生成されるコマンド メッセージを処理するために使用します。 [マクロ](../../mfc/reference/message-map-macros-mfc.md)は、次のマップを使用できます。  
  
## <a name="windows-messages"></a>Windows メッセージ  
  
-   コントロールの通知  
  
-   ユーザー定義メッセージ  
  
## <a name="command-messages"></a>コマンド メッセージ  
  
-   登録済みのユーザー定義メッセージ  
  
-   ユーザー インターフェイス更新メッセージ  
  
## <a name="ranges-of-messages"></a>メッセージの範囲  
  
-   コマンド  
  
-   ハンドラー メッセージの更新  
  
-   コントロールの通知  
  
 メッセージ マップ マクロは重要なマクロですが、通常は直接記述する必要はありません。 これは、開発者がメッセージとメッセージ処理関数を関連付けると、[プロパティ] ウィンドウでメッセージ マップ エントリがソース ファイル内に自動的に作成されるためです。 メッセージ マップ エントリは、[プロパティ] ウィンドウでいつでも編集および追加できます。  
  
> [!NOTE]
>  [プロパティ] ウィンドウでは、メッセージ マップの範囲をサポートしていません。 これらのメッセージ マップ エントリは、独自に作成する必要があります。  
  
 ただし、メッセージ マップは、Microsoft Foundation Class ライブラリの重要な部分です。 これらが何を実行するかを理解する必要があり、そのためのドキュメントが用意されています。  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


---
title: 既定のコントロール イベント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7a57cb6c72d7d444c345140f4a738a3d4a3232c0
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315614"
---
# <a name="default-control-events"></a>既定のコントロール イベント

次のコントロール名では、既定のイベントがあります。

|コントロール名|既定のイベント|
|------------------|-------------------|
|アニメーション化|ACN_START|
|チェック ボックス|BN_CLICKED|
|コンボ ボックス|CBN_SELCHANGE|
|カスタム|TTN_GETDISPINFO|
|日時指定|DTN_DATETIMECHANGE|
|エディット ボックス|EN_CHANGE|
|グループ ボックス|(適用なし)|
|ホット キー|NM_OUTOFMEMORY|
|IP アドレス|IPN_FIELDCHANGED|
|リスト|LVN_ITEMCHANGE|
|リスト ボックス|LBN_SELCHANGE|
|月間予定表|MCN_SELCHANGE|
|画像コントロール|(適用なし)|
|進行状況|NM_CUSTOMDRAW|
|プッシュ ボタン|BN_CLICKED|
|オプション ボタン|BN_CLICKED|
|リッチ エディットします。|EN_CHANGE|
|スクロール バー|NM_THEMECHANGED|
|スライダー|NM_CUSTOMDRAW|
|スピン|UDN_DELTAPOS|
|静的なテキスト|(適用なし)|
|タブ|TCN_SELCHANGE|
|ツリー|TVN_SELCHANGE|

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ コントロールのメンバー変数の定義](../windows/defining-member-variables-for-dialog-controls.md)  
[ユーザー インターフェイス オブジェクトに関連付けられたメッセージ](../mfc/reference/message-types-associated-with-user-interface-objects.md)  
[メッセージ ハンドラーの編集](../mfc/reference/editing-a-message-handler.md)  
[リフレクション メッセージ用のメッセージ ハンドラーの定義](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)  
[新しいコントロール クラスに基づいた変数の宣言](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)  
[仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)
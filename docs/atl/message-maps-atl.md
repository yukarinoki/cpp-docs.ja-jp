---
description: '詳細情報: メッセージマップ (ATL)'
title: メッセージマップ (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
ms.openlocfilehash: c5b3340abbfbc66ac710ab716e3daa38dd7cd6df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159519"
---
# <a name="message-maps-atl"></a>メッセージマップ (ATL)

メッセージマップでは、ハンドラー関数が特定のメッセージ、コマンド、または通知に関連付けられます。 ATL の [メッセージマップマクロ](../atl/reference/message-map-macros-atl.md)を使用して、ウィンドウのメッセージマップを指定できます。 、、およびのウィンドウプロシージャは、 `CWindowImpl` `CDialogImpl` `CContainedWindowT` ウィンドウのメッセージをメッセージマップに送信します。

[メッセージハンドラー関数](../atl/message-handler-functions.md)は、型の追加の引数を受け取り `BOOL&` ます。 この引数は、メッセージが処理されたかどうかを示し、既定では TRUE に設定されています。 ハンドラー関数は、メッセージを処理していないことを示すために、引数を FALSE に設定できます。 この場合、ATL はメッセージマップ内でハンドラー関数をさらに検索し続けます。 この引数を FALSE に設定すると、最初にメッセージに応答して何らかのアクションを実行してから、既定の処理または別のハンドラー関数がメッセージの処理を完了できるようになります。

## <a name="chained-message-maps"></a>チェーンメッセージマップ

ATL では、メッセージマップを連結して、メッセージの処理を別のクラスで定義されたメッセージマップに送信することもできます。 たとえば、共通のメッセージ処理を別のクラスに実装して、そのクラスに対するすべての windows チェーンに対して一様な動作を実現できます。 基底クラスまたはクラスのデータメンバーにチェーンできます。

ATL では、動的なチェーンもサポートされています。これにより、実行時に別のオブジェクトのメッセージマップにチェーンすることができます。 動的なチェーンを実装するには、 [CDynamicChain](../atl/reference/cdynamicchain-class.md)からクラスを派生させる必要があります。 次に、メッセージマップで [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) マクロを宣言します。 CHAIN_MSG_MAP_DYNAMIC には、オブジェクトと、チェーンするメッセージマップを識別する一意の番号が必要です。 この一意の値は、の呼び出しを使用して定義する必要があり `CDynamicChain::SetChainEntry` ます。

クラスが [CMessageMap](../atl/reference/cmessagemap-class.md)から派生していれば、メッセージマップを宣言する任意のクラスにチェーンできます。 `CMessageMap` オブジェクトが他のオブジェクトにメッセージマップを公開できるようにします。 は、 `CWindowImpl` 既にから派生していることに注意 `CMessageMap` してください。

## <a name="alternate-message-maps"></a>代替メッセージマップ

最後に、ATL は、 [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) マクロを使用して宣言された代替メッセージマップをサポートします。 各代替メッセージマップは、ALT_MSG_MAP に渡す一意の番号で識別されます。 代替メッセージマップを使用すると、複数のウィンドウのメッセージを1つのマップで処理できます。 既定で `CWindowImpl` は、は代替メッセージマップを使用しないことに注意してください。 このサポートを追加するには、 `WindowProc` 派生クラスのメソッドをオーバーライド `CWindowImpl` し、 `ProcessWindowMessage` メッセージマップ識別子を使用してを呼び出します。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)

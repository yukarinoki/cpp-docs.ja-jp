---
title: 'サーバー: 埋め込み Windows の実装 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6ef01a7943bbb0c14ec630651757a8665373b85
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055223"
---
# <a name="servers-implementing-in-place-frame-windows"></a>サーバー : 埋め込み先フレーム ウィンドウの実装

この記事では、サーバー アプリケーションを作成するアプリケーション ウィザードを使用しない場合、ビジュアル編集サーバー アプリケーションでの埋め込み先フレーム ウィンドウを実装するために必要な作業について説明します。 この記事で説明する手順に従うと、代わりに、アプリケーション ウィザードで生成されたアプリケーションまたは Visual C で提供されるサンプルのいずれかから既存の埋め込み先フレーム ウィンドウ クラスを使用できます。

#### <a name="to-declare-an-in-place-frame-window-class"></a>埋め込み先フレーム ウィンドウ クラスを宣言するには

1. 埋め込み先フレーム ウィンドウ クラスを派生`COleIPFrameWnd`します。

   - クラスのヘッダー ファイルで DECLARE_DYNCREATE マクロを使用します。

   - クラス実装 (.cpp) ファイルに含めるには、IMPLEMENT_DYNCREATE マクロを使用します。 これにより、フレームワークによって作成するには、このクラスのオブジェクトです。

1. 宣言を`COleResizeBar`フレーム ウィンドウ クラスのメンバー。 これは、サーバー アプリケーションで、インプレースのサイズ変更をサポートする場合に必要です。

   宣言、`OnCreate`メッセージ ハンドラー (を使用して、**プロパティ**ウィンドウ)、呼び出す`Create`の`COleResizeBar`定義されている場合はメンバー。

1. ツールバーの場合は、宣言、`CToolBar`フレーム ウィンドウ クラスのメンバー。

   上書き、`OnCreateControlBars`インプレース サーバーがアクティブなときにツールバーを作成するメンバー関数。 例えば:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   このコードを次の手順 5. の説明を参照してください。

1. メインの .cpp ファイルには、この埋め込み先フレーム ウィンドウ クラスのヘッダー ファイルを含めます。

1. `InitInstance`アプリケーション クラスを呼び出し、`SetServerInfo`オープンで一括編集で使用する埋め込み先フレーム ウィンドウとリソースを指定するドキュメント テンプレート オブジェクトの関数。

一連の関数の呼び出し、**場合**ステートメントを作成、ツールバーのリソースから指定されたサーバー。 この時点で、ツールバーには、コンテナーのウィンドウの階層構造の一部です。 このツールバーはから派生しているため`CToolBar`所有者を変更する場合を除き、その所有者では、コンテナー アプリケーションのフレーム ウィンドウにそのメッセージに合格します。 理由を呼び出す`SetOwner`必要があります。 この呼び出しは、ウィンドウのコマンドがサーバーに渡されるメッセージの原因と、サーバーのフレーム ウィンドウに送信される場所を変更します。 これにより、サーバーが提供するツールバーの操作に対応するためです。

ツールバーのビットマップの ID は、サーバー アプリケーションで定義されているその他の埋め込みリソースとして同じになります。 参照してください[メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)詳細についてはします。

詳細については、次を参照してください[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)、 [COleResizeBar](../mfc/reference/coleresizebar-class.md)、および[CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo)で、*クラス ライブラリ リファレンス*.

## <a name="see-also"></a>関連項目

[サーバー](../mfc/servers.md)<br/>
[サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)<br/>
[サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md)<br/>
[サーバー: サーバー アイテム](../mfc/servers-server-items.md)


---
title: 'サーバー: 埋め込み先フレーム ウィンドウの実装 |Microsoft ドキュメント'
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
ms.openlocfilehash: f0f03d66fac6d58bdb48aa9b7a6d8aafe18a74ea
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956435"
---
# <a name="servers-implementing-in-place-frame-windows"></a>サーバー : 埋め込み先フレーム ウィンドウの実装
この記事では、サーバー アプリケーションを作成するアプリケーションのウィザードを使用しない場合、ビジュアル編集サーバー アプリケーションに埋め込み先フレーム ウィンドウを実装する必要な操作について説明します。 この記事で説明した手順に従うと、代わりに、アプリケーション ウィザードで生成されたアプリケーションまたは Visual C で提供されたサンプルのいずれかから既存の埋め込み先フレーム ウィンドウ クラスを使用する可能性があります。  
  
#### <a name="to-declare-an-in-place-frame-window-class"></a>埋め込み先フレーム ウィンドウ クラスを宣言するには  
  
1.  埋め込み先フレーム ウィンドウ クラスを派生`COleIPFrameWnd`です。  
  
    -   クラスのヘッダー ファイルで DECLARE_DYNCREATE マクロを使用します。  
  
    -   クラスは、実装 (.cpp) ファイルで、IMPLEMENT_DYNCREATE マクロを使用します。 これにより、フレームワークによって作成するには、このクラスのオブジェクト。  
  
2.  宣言、`COleResizeBar`フレーム ウィンドウ クラスのメンバーです。 インプレースでのサーバー アプリケーションでサイズ変更をサポートする場合、これが必要です。  
  
     宣言、`OnCreate`メッセージ ハンドラー (を使用して、**プロパティ**ウィンドウ)、呼び出す`Create`の`COleResizeBar`メンバーを定義している場合。  
  
3.  ツールバーがあれば、宣言、`CToolBar`フレーム ウィンドウ クラスのメンバーです。  
  
     上書き、`OnCreateControlBars`サーバー使用されているアクティブなときに、ツールバーを作成するメンバー関数。 例えば:  
  
     [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]  
  
     このコードを次の手順 5. の説明を参照してください。  
  
4.  メインの .cpp ファイルでこの埋め込み先フレーム ウィンドウ クラスのヘッダー ファイルをインクルードします。  
  
5.  `InitInstance`アプリケーション クラスを呼び出して、`SetServerInfo`関数のドキュメント テンプレート オブジェクトの開かれていて、インプレース編集に使用される埋め込み先フレーム ウィンドウとリソースを指定します。  
  
 内の一連の関数呼び出し、**場合**ステートメント サーバーを作成、ツールバーのリソースを提供します。 この時点では、ツールバーは、コンテナーのウィンドウの階層構造の一部です。 このツールバーはから派生しているため`CToolBar`所有者を変更する場合を除き、コンテナー アプリケーションのフレーム ウィンドウで、その所有者にそのメッセージに合格します。 理由への呼び出し`SetOwner`が必要です。 この呼び出しは、コマンドをサーバーに渡されるメッセージの原因と、サーバーの埋め込み先フレーム ウィンドウに送信されているウィンドウを変更します。 これにより、ツールバーで提供される操作に対応するためにサーバー。  
  
 ツールバーのビットマップの ID は、サーバー アプリケーションで定義されている他の埋め込みリソースと同じにする必要があります。 参照してください[メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)詳細についてはします。  
  
 詳細については、次を参照してください[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)、 [COleResizeBar](../mfc/reference/coleresizebar-class.md)、および[CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo)で、*クラス ライブラリ リファレンス*.  
  
## <a name="see-also"></a>関連項目  
 [サーバー](../mfc/servers.md)   
 [サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)   
 [サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md)   
 [サーバー: サーバー アイテム](../mfc/servers-server-items.md)


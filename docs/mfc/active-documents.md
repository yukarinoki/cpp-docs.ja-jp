---
title: アクティブ ドキュメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC]
- active documents [MFC], requirements
- view objects [MFC], requirements
- OLE [MFC], active documents
- views [MFC], active documents
- active documents [MFC], views
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7a391dda8f8ffee6cec3cebc9d03250336195db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="active-documents"></a>Active ドキュメント
アクティブなドキュメントは、OLE の複合ドキュメント テクノロジを拡張します。 これらの拡張機能は、オブジェクトがコンテナー内で機能をまだ保持の表示および印刷機能を制御できるように、ビューを管理する追加のインターフェイスの形式で提供されます。 この処理できるようになります (Microsoft Office バインダーや Microsoft Internet Explorer の場合) などの外部のフレームとネイティブ フレーム (、製品のビュー ポートなど) の両方にドキュメントを表示します。  
  
 このセクションでは、機能について説明[アクティブ ドキュメントの要件](#requirements_for_active_documents)です。 作業中の文書は、一連のデータを所有し、データを保存および取得できます、記憶域にアクセスします。 作成し、データの 1 つまたは複数のビューを管理できます。 アクティブ ドキュメントだけでなく、通常を埋め込むと、インプレース アクティブ化のインターフェイス OLE ドキュメントをサポートする、ビューを作成するには、その機能が通信する`IOleDocument`です。 このインターフェイスからは、コンテナーは、アクティブなドキュメントを表示できるビューを作成する (および場合によっては列挙) を要求できます。 このインターフェイスを使用では、アクティブなドキュメントは、自身に関する複数のビューまたは複雑な四角形をサポートするかどうかなどの他の情報も提供します。  
  
 次に、**示す**インターフェイスです。 なお、 **IEnumOleDocumentViews**インターフェイスの標準の OLE 列挙子は、 **IOleDocumentView \*** 型です。  
  
```  
interface IOleDocument : IUnknown  
    {  
    HRESULT CreateView(  
        [in] IOleInPlaceSite *pIPSite,  
        [in] IStream *pstm,  
        [in] DWORD dwReserved,  
        [out] IOleDocumentView **ppView);  

    HRESULT GetDocMiscStatus([out] DWORD *pdwStatus);  

    HRESULT EnumViews(  
        [out] IEnumOleDocumentViews **ppEnum,  
        [out] IOleDocumentView **ppView);  
    }  
```  
  
 すべてのアクティブなドキュメントには、このインターフェイスを持つビュー フレーム プロバイダーが必要です。 コンテナー内にあるドキュメントが埋め込まれていない場合、active ドキュメント サーバー自体はビュー フレームを提供する必要があります。 ただし、active ドキュメント コンテナーには、アクティブなドキュメントが埋め込まれている場合、コンテナーは、ビュー フレームを提供します。  
  
 アクティブ ドキュメントの 1 つまたは複数の種類を作成できます[ビュー](#requirements_for_view_objects)のデータ (例では、通常、アウトライン、ページのレイアウト、およびなど)。 ビューは、フィルターを使用する、データを表示できるように機能します。 場合でも、ドキュメントでは、ビューの 1 つだけの型を持つ、可能性がありますか新しいウィンドウの機能をサポートするための手段として複数のビューをサポートするために (たとえば、**新しいウィンドウ**上の品目、**ウィンドウ**Office のメニューアプリケーションの場合)。  
  
##  <a name="requirements_for_active_documents"></a> アクティブ ドキュメントの要件  
 Active ドキュメント コンテナーに表示できるアクティブなドキュメントが必要です。  
  
-   そのストレージ メカニズムとして OLE の複合ファイルを使用して実装することによって`IPersistStorage`です。  
  
-   などの OLE ドキュメントの基本的な埋め込み機能をサポートして**ファイルから作成**です。 インターフェイスが必要になりますこの`IPersistFile`、 `IOleObject`、および`IDataObject`です。  
  
-   1 つまたは複数のビュー、それぞれが、インプレース アクティブ化の機能をサポートします。 ビューが、インターフェイスをサポートする必要があります`IOleDocumentView`インターフェイスだけでなく`IOleInPlaceObject`と`IOleInPlaceActiveObject`(コンテナーを使用して**ビュー**と**IOleInPlaceFrame**インターフェイス)。  
  
-   標準のアクティブなドキュメントのインターフェイスをサポートして`IOleDocument`、 `IOleCommandTarget`、および`IPrint`です。  
  
 場合の知識とコンテナー側のインターフェイスを使用する方法については、これらの要件で暗黙的です。  
  
##  <a name="requirements_for_view_objects"></a> オブジェクトを表示するための要件  
 アクティブなドキュメントには、そのデータの 1 つまたは複数のビューを作成できます。 機能的には、これらのビューは、データを表示するための特定のメソッドへのポートです。 アクティブなドキュメントは、1 つのビューのみをサポートする場合、アクティブなドキュメントとビューを実装する 1 つのクラスです。 **この**、同じオブジェクトを返します`IOleDocumentView`インターフェイス ポインター。  
  
 Active ドキュメント コンテナー内で表現されているビュー コンポーネントをサポートする必要があります**IOleInPlaceObject**と**IOleInPlaceActiveObject**に加えて`IOleDocumentView`:  
  
```  
interface IOleDocumentView : IUnknown  
    {  
    HRESULT SetInPlaceSite([in] IOleInPlaceSite *pIPSite);  
    HRESULT GetInPlaceSite([out] IOleInPlaceSite **ppIPSite);  
    HRESULT GetDocument([out] IUnknown **ppunk);  
    [input_sync] HRESULT SetRect([in] LPRECT prcView);  
    HRESULT GetRect([in] LPRECT prcView);  
    [input_sync] HRESULT SetRectComplex(  
        [in] LPRECT prcView,  
        [in] LPRECT prcHScroll,  
        [in] LPRECT prcVScroll,  
        [in] LPRECT prcSizeBox);  
    HRESULT Show([in] BOOL fShow);  
    HRESULT UIActivate([in] BOOL fUIActivate);  
    HRESULT Open(void);  
    HRESULT CloseView([in] DWORD dwReserved);  
    HRESULT SaveViewState([in] IStream *pstm);  
    HRESULT ApplyViewState([in] IStream *pstm);  
    HRESULT Clone(  
        [in] IOleInPlaceSite *pIPSiteNew,  
        [out] IOleDocumentView **ppViewNew);  
    }  
```  
  
 すべてのビューには、ビュー フレームとビュー ポート (HWND とそのウィンドウ内の四角形の領域) をカプセル化する、関連付けられたビュー サイトがあります。 サイトこの機能が公開されても、標準**ビュー**インターフェイスです。 1 つの HWND の 1 つ以上のビュー ポートを設定することに注意してください。  
  
 通常のビューの種類ごとには印刷結果は異なります。 したがってビューと、対応するサイトを表示する必要があります、インターフェイスを実装印刷場合`IPrint`と`IContinueCallback`、それぞれします。 ビューのフレームを使用して、ビュー プロバイダーとネゴシエートする必要があります**IPrint**印刷が開始した場合、ヘッダー、フッター、余白、および関連する要素が正しく印刷できるようにします。 ビュー プロバイダー経由の印刷関連のイベントのフレームに通知`IContinueCallback`です。 これらのインターフェイスの使用に関する詳細については、次を参照してください。[プログラムによる印刷](../mfc/programmatic-printing.md)です。  
  
 アクティブなドキュメントは、1 つのビューのみをサポートする場合して、アクティブなドキュメントとビューできますを実装する 1 つの具象クラスを使用してに注意してください。 **この**、同じオブジェクトの値を返します`IOleDocumentView`インターフェイス ポインター。 つまり、ことがある 2 つの個別のオブジェクト インスタンス 1 つのビューが必要な場合必要はありません。  
  
 ビュー オブジェクトには、コマンド ターゲットことができます。 実装することによって`IOleCommandTarget`ビューは、コンテナーのユーザー インターフェイスで発生するコマンドを受け取ることができます (など**新規**、**開く**、**名前を付けて保存**、 **印刷**上、**ファイル**メニューおよび**コピー**、**貼り付け**、**を元に戻す**上、 **を編集**メニュー)。 詳細については、次を参照してください。[メッセージの処理とコマンド ターゲット](../mfc/message-handling-and-command-targets.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)


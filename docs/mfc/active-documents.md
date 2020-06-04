---
title: Active ドキュメント
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC]
- active documents [MFC], requirements
- view objects [MFC], requirements
- OLE [MFC], active documents
- views [MFC], active documents
- active documents [MFC], views
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
ms.openlocfilehash: cbea3e032932477006820c5a71fbbf3e40123bdf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322084"
---
# <a name="active-documents"></a>Active ドキュメント

アクティブ ドキュメントは、OLE の複合ドキュメント テクノロジを拡張します。 これらの拡張機能は、オブジェクトがコンテナー内で機能し、表示および印刷機能の制御を保持できるように、ビューを管理する追加のインターフェイスの形式で提供されます。 このプロセスにより、ドキュメントを外部フレーム (Microsoft Office バインダーや Internet Explorer など) とネイティブ フレーム (製品独自のビュー ポートなど) の両方で表示できます。

ここでは、[アクティブ ドキュメント](#requirements_for_active_documents)の機能要件について説明します。 アクティブ ドキュメントはデータのセットを所有し、データを保存および取得できるストレージにアクセスできます。 データに関する 1 つ以上のビューを作成および管理できます。 OLE ドキュメントの通常の埋め込みインターフェイスと埋め込みアクティブ化インターフェイスをサポートするだけでなく、アクティブ ドキュメントは を使用`IOleDocument`してビューを作成する機能を伝達します。 コンテナーは、このインターフェイスを通じて、アクティブ ドキュメントが表示できるビューを作成 (場合によっては列挙) するように要求できます。 アクティブ ドキュメントは、このインターフェイスを通じて、複数のビューや複雑な四角形をサポートしているかどうかなど、そのドキュメントに関するさまざまな情報を提供することもできます。

インターフェイスは次のとおりです`IOleDocument`。 `IEnumOleDocumentViews`インターフェイスは`IOleDocumentView*`型の標準 OLE 列挙子であることに注意してください。

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

アクティブなドキュメントには、このインターフェイスを持つビュー フレーム プロバイダーが必要です。 ドキュメントがコンテナー内に埋め込まれていない場合、アクティブ ドキュメント サーバー自体がビュー フレームを提供する必要があります。 ただし、アクティブ ドキュメントがアクティブ ドキュメント コンテナーに埋め込まれている場合、コンテナーはビュー フレームを提供します。

アクティブドキュメントでは、データの 1 つ以上の[種類のビュー](#requirements_for_view_objects) (標準、アウトライン、ページ レイアウトなど) を作成できます。 ビューは、データを見ることができるフィルターのように動作します。 ドキュメントに 1 種類のビューしか含めなくても、新しいウィンドウ機能をサポートする手段として複数のビューをサポートする必要があります (たとえば、Office アプリケーションの **[ウィンドウ**] メニューの **[新しいウィンドウ**] 項目)。

## <a name="requirements-for-active-documents"></a><a name="requirements_for_active_documents"></a>アクティブ ドキュメントの要件

アクティブ ドキュメント コンテナーに表示できるアクティブ ドキュメントは、次のことが必要です。

- を実装`IPersistStorage`して、OLE の複合ファイルをストレージ機構として使用します。

- OLE ドキュメントの基本的な埋め込み機能 **([ファイルから作成]** など) をサポートします。 この場合、インターフェイス`IPersistFile`、、`IOleObject`および`IDataObject`が必要になります。

- 1 つ以上のビューをサポートし、各ビューはインプレース アクティベーションが可能です。 つまり、ビューはインターフェイスと`IOleDocumentView`インターフェイスをサポートし、(`IOleInPlaceObject``IOleInPlaceActiveObject`コンテナ`IOleInPlaceSite`と`IOleInPlaceFrame`インターフェイスを使用して)サポートする必要があります。

- 標準のアクティブ ドキュメント`IOleDocument`インターフェイス`IOleCommandTarget`、`IPrint`および をサポートします。

これらの要件では、コンテナー側インターフェイスを使用するタイミングと方法に関する知識が示されます。

## <a name="requirements-for-view-objects"></a><a name="requirements_for_view_objects"></a>ビュー オブジェクトの要件

アクティブドキュメントは、そのデータのビューを 1 つ以上作成できます。 機能的には、これらのビューは、データを表示するための特定の方法へのポートのようなものです。 アクティブ ドキュメントが 1 つのビューしかサポートしていない場合、アクティブ ドキュメントとその 1 つのビューは、単一のクラスを使用して実装できます。 `IOleDocument::CreateView`は同じオブジェクトのインターフェイス`IOleDocumentView`ポインタを返します。

アクティブドキュメントコンテナ内で表現するには、ビューコンポーネントが`IOleInPlaceObject``IOleInPlaceActiveObject``IOleDocumentView`をサポートし、に加えて、

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

すべてのビューにはビュー サイトが関連付けられており、ビュー フレームとビュー ポート(HWND とそのウィンドウ内の四角形領域)がカプセル化されます。 サイトは、標準`IOleInPlaceSite`インターフェイスを使用してこの機能を公開します。 1 つの HWND に複数のビュー ポートを設定できます。

通常、ビューの種類ごとに、異なる印刷表現が表示されます。 したがって、ビューとそれに対応するビュー サイトは、それぞれ`IPrint`、`IContinueCallback`と がそれぞれ印刷インターフェイスを実装する必要があります。 ビュー フレームは、印刷の開始時に`IPrint`ビュー プロバイダーとネゴシエートして、ヘッダー、フッター、余白、および関連する要素が正しく印刷されるようにする必要があります。 ビュー プロバイダーは、印刷関連のイベントのフレームに`IContinueCallback`を通知します。 これらのインターフェイスの使用方法の詳細については、「[プログラムによる印刷](../mfc/programmatic-printing.md)」を参照してください。

アクティブ ドキュメントが 1 つのビューしかサポートしていない場合、アクティブ ドキュメントとその単一のビューは、単一の具象クラスを使用して実装できます。 `IOleDocument::CreateView`同じオブジェクトのインターフェイス ポインター`IOleDocumentView`を返すだけです。 つまり、1 つのビューのみが必要な場合に、2 つの個別のオブジェクト インスタンスが存在する必要はありません。

ビュー オブジェクトは、コマンド ターゲットにすることもできます。 ビューを`IOleCommandTarget`実装することにより、コンテナ**Edit**のユーザー インターフェイスで生成されたコマンド **([ファイル]** メニューの **[新規**]、[**開く**]、[**名前を付けて保存**] **、[ファイル**] メニューの [印刷] 、コピー 、**貼り付け**、**元に戻す**コマンドなど) を受信できます。 **Copy** 詳細については、「[メッセージ処理とコマンド ターゲット](../mfc/message-handling-and-command-targets.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Active ドキュメント コンテインメント](../mfc/active-document-containment.md)

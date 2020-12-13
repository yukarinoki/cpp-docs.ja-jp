---
description: '詳細情報: アクティブドキュメント'
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
ms.openlocfilehash: cae0eda775670867d5e36b4f2b9ec895a5dc3eb7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150307"
---
# <a name="active-documents"></a>Active ドキュメント

アクティブドキュメントは、OLE の複合ドキュメントテクノロジを拡張します。 これらの拡張機能は、ビューを管理する追加のインターフェイスの形式で提供されます。これにより、オブジェクトをコンテナー内で機能させることができるようになり、表示と印刷の機能の制御を維持できます。 このプロセスにより、ドキュメントを外部フレーム (Microsoft Office バインダーや Microsoft Internet Explorer など) とネイティブフレーム (製品独自のビューポートなど) の両方に表示できるようになります。

ここでは、 [アクティブなドキュメントの](#requirements_for_active_documents)機能の要件について説明します。 アクティブドキュメントは、データのセットを所有し、データを保存および取得できるストレージにアクセスできます。 データに対して1つ以上のビューを作成および管理できます。 アクティブドキュメントは、OLE ドキュメントの通常の埋め込みおよびインプレースアクティベーションインターフェイスをサポートするだけでなく、を通じてビューを作成する機能を通知し `IOleDocument` ます。 コンテナーは、このインターフェイスを使用して、アクティブなドキュメントに表示されるビューを作成 (および場合によっては列挙) するように要求できます。 このインターフェイスを使用して、アクティブなドキュメントでは、複数のビューや複雑な四角形をサポートするかどうかなど、その他の情報を提供することもできます。

インターフェイスを次に示し `IOleDocument` ます。 `IEnumOleDocumentViews`インターフェイスは、型の標準の OLE 列挙子であることに注意して `IOleDocumentView*` ください。

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

すべてのアクティブなドキュメントには、このインターフェイスを持つビューフレームプロバイダーが必要です。 ドキュメントがコンテナー内に埋め込まれていない場合は、アクティブなドキュメントサーバー自体がビューフレームを提供する必要があります。 ただし、アクティブなドキュメントがアクティブなドキュメントコンテナーに埋め込まれている場合、コンテナーにはビューフレームが用意されています。

アクティブなドキュメントでは、そのデータの1つまたは複数の種類の [ビュー](#requirements_for_view_objects) (通常、アウトライン、ページレイアウトなど) を作成できます。 ビューは、データを表示できるフィルターのように機能します。 ドキュメントにビューの種類が1つしかない場合でも、新しいウィンドウ機能をサポートする手段として複数のビューをサポートすることができます (たとえば、Office アプリケーションの [**ウィンドウ**] メニューの [**新しいウィンドウ**] 項目)。

## <a name="requirements-for-active-documents"></a><a name="requirements_for_active_documents"></a> アクティブなドキュメントの要件

アクティブなドキュメントコンテナーに表示できるアクティブなドキュメントは次のようにする必要があります。

- を実装することによって、OLE の複合ファイルをストレージメカニズムとして使用し `IPersistStorage` ます。

- OLE ドキュメントの基本的な埋め込み機能 ( **Create From File** など) をサポートします。 これには、インターフェイス、 `IPersistFile` `IOleObject` 、およびが `IDataObject` あります。

- 1つまたは複数のビューをサポートします。それぞれがインプレースライセンス認証に対応しています。 つまり、ビューはインターフェイスとインターフェイス、および `IOleDocumentView` `IOleInPlaceObject` `IOleInPlaceActiveObject` (コンテナーのおよびインターフェイスを使用して) をサポートする必要があり `IOleInPlaceSite` `IOleInPlaceFrame` ます。

- 標準の active ドキュメントインターフェイスである、、およびをサポートし `IOleDocument` `IOleCommandTarget` `IPrint` ます。

コンテナー側のインターフェイスをいつどのように使用するかについての知識は、これらの要件で暗黙に示されます。

## <a name="requirements-for-view-objects"></a><a name="requirements_for_view_objects"></a> ビューオブジェクトの要件

アクティブなドキュメントは、そのデータの1つまたは複数のビューを作成できます。 機能的には、これらのビューは、データを表示するための特定の方法のポートに似ています。 アクティブなドキュメントが1つのビューのみをサポートしている場合は、アクティブなドキュメントとその単一のビューを1つのクラスを使用して実装できます。 `IOleDocument::CreateView` 同じオブジェクトの `IOleDocumentView` インターフェイスポインターを返します。

アクティブなドキュメントコンテナー内で表現するには、ビューコンポーネントで次の機能をサポートする必要があり `IOleInPlaceObject` `IOleInPlaceActiveObject` `IOleDocumentView` ます。

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

すべてのビューには関連付けられたビューサイトがあり、ビューフレームとビューポート (そのウィンドウの HWND と四角形の領域) がカプセル化されます。 この機能は、標準のインターフェイスを介して公開され `IOleInPlaceSite` ます。 1つの HWND に複数のビューポートを含めることができることに注意してください。

通常、ビューの種類ごとに印刷表現が異なります。 したがって、ビューとそれに対応するビューサイトでは、それぞれがおよびの場合は、印刷インターフェイスを実装する必要があり `IPrint` `IContinueCallback` ます。 ビューフレームは、印刷開始時にビュープロバイダーとネゴシエートし `IPrint` 、ヘッダー、フッター、余白、および関連要素が正しく印刷されるようにする必要があります。 ビュープロバイダーは、を使用して、印刷関連のイベントのフレームを通知し `IContinueCallback` ます。 これらのインターフェイスの使用方法の詳細については、「 [プログラムによる印刷](programmatic-printing.md)」を参照してください。

アクティブなドキュメントでサポートされているビューは1つだけである場合、アクティブなドキュメントとその単一のビューは、1つの具象クラスを使用して実装できます。 `IOleDocument::CreateView` は、同じオブジェクトのインターフェイスポインターを単に返し `IOleDocumentView` ます。 つまり、1つのビューのみが必要な場合は、2つの異なるオブジェクトインスタンスを使用する必要はありません。

ビューオブジェクトもコマンドターゲットにすることができます。 ビューを実装することにより、 `IOleCommandTarget` コンテナーのユーザーインターフェイスで生成されたコマンドを受け取ることができます ([**新規**]、[**開く**]、[名前を付け **て保存**]、[**ファイル**] メニューの [**印刷**]、[**編集**] メニューの [**コピー**]、[**貼り付け**]、[**元に戻す**] など)。 詳細については、「 [メッセージ処理とコマンドターゲット](message-handling-and-command-targets.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Active ドキュメントコンテインメント](active-document-containment.md)

---
description: '詳細情報: CDocObjectServer クラス'
title: CDocObjectServer クラス
ms.date: 09/12/2018
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
ms.openlocfilehash: 5a87363fef66a4819fc8efd504da96398cf3c89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184947"
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer クラス

標準の `COleDocument` サーバーを完全な DocObject サーバーにするために必要な、 `IOleDocument`、 `IOleDocumentView`、 `IOleCommandTarget`、 `IPrint`などの追加 OLE インターフェイスを実装します。

## <a name="syntax"></a>構文

```
class CDocObjectServer : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|`CDocObjectServer` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|ドキュメントオブジェクトサーバーをアクティブにしますが、表示しません。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CDocObjectServer:: Onアクティブビュー](#onactivateview)|DocObject ビューを表示します。|
|[CDocObjectServer:: OnApplyViewState](#onapplyviewstate)|DocObject ビューの状態を復元します。|
|[CDocObjectServer:: OnSaveViewState](#onsaveviewstate)|DocObject ビューの状態を保存します。|

## <a name="remarks"></a>解説

`CDocObjectServer` はから派生 `CCmdTarget` し、と密接に連携して `COleServerDoc` 、インターフェイスを公開します。

DocObject server ドキュメントには、DocObject items へのサーバーインターフェイスを表す [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) オブジェクトを含めることができます。

DocObject サーバーをカスタマイズするには、から独自のクラスを派生させ、 `CDocObjectServer` その view setup functions、 [On view](#onactivateview)、 [onactivateview](#onapplyviewstate)、および [onactivateview](#onsaveviewstate)をオーバーライドします。 フレームワーク呼び出しへの応答として、クラスの新しいインスタンスを提供する必要があります。

DocObjects の詳細については、 *MFC リファレンス* の [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) and [COleCmdUI](../../mfc/reference/colecmdui-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>要件

**ヘッダー:** afxdocob

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a> CDocObjectServer::ActivateDocObject

ドキュメントオブジェクトサーバーをアクティブ化しますが、表示しない場合は、この関数を呼び出します。

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>解説

`ActivateDocObject` は `IOleDocumentSite` `ActivateMe` 、メソッドを呼び出しますが、ビューの設定と表示については、 [CDocObjectServer:: 代わっ](#onactivateview)の呼び出しで指定されているように、ビューを表示しません。

`ActivateDocObject` `OnActivateView` DocObject ビューをアクティブ化して表示します。 DocObject のアクティブ化は、他の種類の OLE の埋め込みアクティベーションとは異なります。 DocObject activation は、埋め込み先ハッチの境界とオブジェクトの装飾 (サイズ変更ハンドルなど) の表示をバイパスし、オブジェクトのエクステント関数を無視し、四角形の外に描画するのではなく、ビューの四角形内にスクロールバーを描画します (通常のインプレースアクティブ化と同様)。

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a> CDocObjectServer::CDocObjectServer

`CDocObjectServer` オブジェクトを構築して初期化します。

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>パラメーター

*pOwner*<br/>
DocObject サーバーのクライアントであるクライアントサイトドキュメントへのポインター。

*pDocSite*<br/>
コンテナーによって実装されるインターフェイスへのポインター `IOleDocumentSite` 。

### <a name="remarks"></a>解説

DocObject がアクティブになると、クライアントサイト OLE インターフェイス () によって、 `IOleDocumentSite` DocObject サーバーがクライアント (コンテナー) と通信できるようになります。 DocObject サーバーがアクティブになると、まず、コンテナーがインターフェイスを実装していることが確認され `IOleDocumentSite` ます。 その場合は、 [COleServerDoc:: GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) が呼び出され、コンテナーが DocObjects をサポートしているかどうかが確認されます。 既定では、は `GetDocObjectServer` NULL を返します。 をオーバーライドして、 `COleServerDoc::GetDocObjectServer` 新しいオブジェクトまたは独自の派生オブジェクトを構築する必要があります。これには、 `CDocObjectServer` コンテナーへのポインターと、 `COleServerDoc` そのインターフェイスを `IOleDocumentSite` コンストラクターへの引数として指定します。

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a> CDocObjectServer:: Onアクティブビュー

DocObject ビューを表示するには、この関数を呼び出します。

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>戻り値

エラーまたは警告の値を返します。 既定では、は成功した場合は NOERROR を返します。それ以外の場合は、E_FAIL ます。

### <a name="remarks"></a>解説

この関数は、埋め込み先フレームウィンドウを作成し、ビュー内にスクロールバーを描画します。次に、サーバーがコンテナーと共有するメニューを設定し、フレームコントロールを追加して、アクティブなオブジェクトを設定します。最後に、埋め込み先フレームウィンドウを表示し、フォーカスを設定します。

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a> CDocObjectServer:: OnApplyViewState

DocObject ビューの状態を復元するには、この関数をオーバーライドします。

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
`CArchive`ビューステートのシリアル化元のオブジェクト。

### <a name="remarks"></a>解説

この関数は、ビューがインスタンス化された後に初めて表示されるときに呼び出されます。 `OnApplyViewState``CArchive` [Onsaveviewstate](#onsaveviewstate)で以前に保存したオブジェクトのデータに従って、ビューを再初期化するように指示します。 ビューは、オブジェクト内のデータを検証する必要があり `CArchive` ます。これは、コンテナーがビューステートデータを何らかの方法で解釈しようとしないためです。

を使用すると `OnSaveViewState` 、ビューの状態に固有の永続的な情報を格納できます。 をオーバーライドして情報を格納する場合 `OnSaveViewState` は、をオーバーライドして `OnApplyViewState` その情報を読み取り、新しくアクティブになったときにビューに適用する必要があります。

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a> CDocObjectServer:: OnSaveViewState

DocObject ビューに関する追加の状態情報を保存するには、この関数をオーバーライドします。

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
`CArchive`ビューステートのシリアル化先となるオブジェクト。

### <a name="remarks"></a>解説

状態には、ビューの種類、拡大率、挿入、選択ポイントなどのプロパティが含まれる場合があります。 通常、コンテナーはビューを非アクティブ化する前にこの関数を呼び出します。 保存された状態は、後で [Onapplyviewstate](#onapplyviewstate)を使用して復元できます。

を使用すると `OnSaveViewState` 、ビューの状態に固有の永続的な情報を格納できます。 をオーバーライドして情報を格納する場合 `OnSaveViewState` は、をオーバーライドして `OnApplyViewState` その情報を読み取り、新しくアクティブになったときにビューに適用する必要があります。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)

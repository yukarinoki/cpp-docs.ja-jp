---
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
ms.openlocfilehash: ccd8ddc9f4981b3d9f7f4e1decdf6790cd05b98b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375490"
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
|[をクリックします。](#cdocobjectserver)|`CDocObjectServer` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトサーバー::アクティブにDocオブジェクト](#activatedocobject)|ドキュメント オブジェクト サーバーをアクティブにしますが、表示しません。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ビューをアクティブにします。](#onactivateview)|[オブジェクト] ビューを表示します。|
|[サーバー::オンアプアビューステート](#onapplyviewstate)|DocObject ビューの状態を復元します。|
|[サーバー::オンセーブビューステート](#onsaveviewstate)|DocObject ビューの状態を保存します。|

## <a name="remarks"></a>解説

`CDocObjectServer`はから`CCmdTarget`派生し、インターフェイスを`COleServerDoc`公開するために密接に動作します。

DocObject サーバー ドキュメントには、DocObject アイテムへのサーバー インターフェイスを表す[CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)オブジェクトを含めることができます。

DocObject サーバーをカスタマイズするには、独自のクラスを`CDocObjectServer`から派生させ、そのビュー設定関数[である OnActivateView](#onactivateview) [、OnApplyViewState](#onapplyviewstate)、および[OnSaveViewState](#onsaveviewstate)をオーバーライドします。 フレームワークの呼び出しに応じて、クラスの新しいインスタンスを提供する必要があります。

DocObject の詳細については *、MFC リファレンス*の[「CDocObject サーバー アイテム](../../mfc/reference/cdocobjectserveritem-class.md)と[COleCmdUI」](../../mfc/reference/colecmdui-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdocob.h

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a>オブジェクトサーバー::アクティブにDocオブジェクト

ドキュメント オブジェクト サーバをアクティブにする (ただし表示しない) 場合は、この関数を呼び出します。

```
void ActivateDocObject();
```

### <a name="remarks"></a>解説

`ActivateDocObject`メソッド`IOleDocumentSite`を`ActivateMe`呼び出しますが[、CDocObjectServer::OnActivateView](#onactivateview)の呼び出しで指定されたビューの設定と表示方法に関する特定の指示を待機するため、ビューは表示されません。

を一`ActivateDocObject`緒`OnActivateView`に行い、DocObject ビューをアクティブにして表示します。 DocObject のアクティブ化は、他の種類の OLE インプレース ライセンス認証とは異なります。 DocObject アクティブ化では、埋め込み先のハッチング枠とオブジェクトの表示要素 (サイズ変更ハンドルなど) の表示を省略し、オブジェクト範囲関数を無視して、ビュー四角形の内側にスクロール バーを描画します。

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a>をクリックします。

`CDocObjectServer` オブジェクトを構築して初期化します。

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>パラメーター

*所有者*<br/>
DocObject サーバーのクライアントであるクライアント サイト ドキュメントへのポインター。

*をクリックします。*<br/>
コンテナーによって`IOleDocumentSite`実装されるインターフェイスへのポインター。

### <a name="remarks"></a>解説

DocObject がアクティブな場合、クライアント サイト OLE`IOleDocumentSite`インターフェイス ( ) は、DocObject サーバーがクライアント (コンテナ) と通信できるようにします。 DocObject サーバーがアクティブ化されると、まず、コンテナーが`IOleDocumentSite`インターフェイスを実装していることを確認します。 その場合は、コンテナーが[DocObjects を](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver)サポートしているかどうかを確認するために呼び出されます。 既定では、NULL`GetDocObjectServer`を返します。 新しい`CDocObjectServer`オブジェクト`COleServerDoc::GetDocObjectServer`または独自の派生オブジェクトを構築するには、コンストラクターへの引数としてコンテナーとその`IOleDocumentSite`インターフェイスへのポインターを使用してオーバーライドする必要があります。 `COleServerDoc`

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a>ビューをアクティブにします。

この関数を呼び出して、DocObject ビューを表示します。

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>戻り値

エラーまたは警告の値を返します。 デフォルトでは、成功した場合は NOERROR を返します。それ以外の場合は、E_FAIL。

### <a name="remarks"></a>解説

この関数は、インプレイス フレーム ウィンドウを作成し、ビュー内にスクロール バーを描画し、サーバーがコンテナーと共有するメニューを設定し、フレーム コントロールを追加して、アクティブ なオブジェクトを設定し、最後にインプレース フレーム ウィンドウを表示してフォーカスを設定します。

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a>サーバー::オンアプアビューステート

DocObject ビューの状態を復元するには、この関数をオーバーライドします。

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
ビュー`CArchive`ステートをシリアル化するオブジェクト。

### <a name="remarks"></a>解説

この関数は、インスタンス化後にビューが初めて表示されるときに呼び出されます。 `OnApplyViewState`では、前に[OnSaveViewState](#onsaveviewstate)で保存したオブジェクト`CArchive`のデータに従って、ビュー自体を再初期化するように指示します。 コンテナーはビューステート データを`CArchive`何らかの方法で解釈しないため、ビューはオブジェクト内のデータを検証する必要があります。

を使用`OnSaveViewState`して、ビューの状態に固有の永続的な情報を格納できます。 情報を格納`OnSaveViewState`するようにオーバーライドする場合は、その情報を`OnApplyViewState`読み取り、新しくアクティブになったときにビューに適用するようにオーバーライドします。

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a>サーバー::オンセーブビューステート

DocObject ビューに関する追加の状態情報を保存するには、この関数をオーバーライドします。

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
ビュー`CArchive`ステートのシリアル化先のオブジェクト。

### <a name="remarks"></a>解説

状態には、ビュータイプ、ズーム倍率、挿入点、選択ポイントなどのプロパティが含まれる場合があります。 通常、コンテナーはビューを非アクティブ化する前にこの関数を呼び出します。 保存された状態は、後で[OnApplyViewState](#onapplyviewstate)を使用して復元できます。

を使用`OnSaveViewState`して、ビューの状態に固有の永続的な情報を格納できます。 情報を格納`OnSaveViewState`するようにオーバーライドする場合は、その情報を`OnApplyViewState`読み取り、新しくアクティブになったときにビューに適用するようにオーバーライドします。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)

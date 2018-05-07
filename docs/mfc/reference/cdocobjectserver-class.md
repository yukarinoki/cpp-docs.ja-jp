---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d9951fd087619371e24f06822774cec005787c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdocobjectserver-class"></a>関数クラス
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
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|ドキュメント オブジェクト サーバーをアクティブには、表示はされません。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|DocObject ビューを表示します。|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|DocObject ビューの状態を復元します。|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|DocObject ビューの状態を保存します。|  
  
## <a name="remarks"></a>コメント  
 `CDocObjectServer` 派生した`CCmdTarget`と密接に連携`COleServerDoc`インターフェイスを公開します。  
  
 DocObject サーバー ドキュメントを含めることができます[CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 、DocObject 項目へのサーバー インターフェイスを表すオブジェクト。  
  
 DocObject サーバーをカスタマイズする、独自のクラスから派生させる`CDocObjectServer`そのビュー セットアップ関数をオーバーライドして[OnActivateView](#onactivateview)、 [OnApplyViewState](#onapplyviewstate)、および[OnSaveViewState](#onsaveviewstate). Framework 呼び出しに対する応答でクラスの新しいインスタンスを提供する必要があります。  
  
 DocObjects については、次を参照してください。 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)と[COleCmdUI](../../mfc/reference/colecmdui-class.md)で、 *『 MFC リファレンス*です。 参照してください[インターネットの最初の手順: Active ドキュメント](../../mfc/active-documents-on-the-internet.md)と[アクティブ ドキュメント](../../mfc/active-documents-on-the-internet.md)です。  
  
 また、次のサポート技術情報の記事を参照してください。  
  
-   Q247382: PRB: ActiveX ドキュメント コンテナーによって非表示には、ActiveX ドキュメント サーバーでのコントロールのツールヒント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdocob.h  
  
##  <a name="activatedocobject"></a>  CDocObjectServer::ActivateDocObject  
 この関数は、ドキュメント オブジェクト サーバーをアクティブ化 (は表示されません) を呼び出します。  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>コメント  
 `ActivateDocObject` 呼び出し`IOleDocumentSite`の**ActivateMe**メソッドを設定およびへの呼び出しで指定されたビューを表示する方法の具体的な手順についてまで待機するために、ビューを表示しない[CDocObjectServer::OnActivateView](#onactivateview).  
  
 同時に、`ActivateDocObject`と`OnActivateView`アクティブ化し、DocObject ビューを表示します。 DocObject アクティブ化は、OLE、インプレース アクティブ化の他の種類によって異なります。 インプレースで点線の枠と (サイズ変更ハンドル) などのオブジェクトの表示要素の表示をバイパスする、オブジェクトの拡張機能、および (標準のように、その四角形の外側に描画するのではなくビューの長方形内のスクロール バーを描画 DocObject アクティブ化インプレース アクティブ化) します。  
  
##  <a name="cdocobjectserver"></a>  CDocObjectServer::CDocObjectServer  
 `CDocObjectServer` オブジェクトを構築して初期化します。  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pOwner*  
 DocObject サーバー用のクライアントは、クライアント サイトのドキュメントへのポインター。  
  
 `pDocSite`  
 ポインター、`IOleDocumentSite`コンテナーによって実装されるインターフェイス。  
  
### <a name="remarks"></a>コメント  
 DocObject がアクティブである場合、クライアント サイトの OLE インターフェイス ( `IOleDocumentSite`) は、DocObject サーバーがクライアント (コンテナー) と通信することができます。 DocObject サーバーがアクティブになると、まず、コンテナーによって実装されている、`IOleDocumentSite`インターフェイスです。 場合は、 [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver)コンテナー DocObjects でサポートされているかどうかに呼び出されます。 既定では、`GetDocObjectServer`返します**NULL**です。 オーバーライドする必要があります`COleServerDoc::GetDocObjectServer`新しい構築するために`CDocObjectServer`オブジェクトまたはへのポインターとの独自の派生オブジェクトを`COleServerDoc`コンテナーとその`IOleDocumentSite`コンス トラクターに引数としてのインターフェイスです。  
  
##  <a name="onactivateview"></a>  CDocObjectServer::OnActivateView  
 DocObject ビューを表示するには、この関数を呼び出します。  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>戻り値  
 エラーまたは警告の値を返します。 既定では、次のように返されます。 **NOERROR**成功した場合は、 **E_FAIL**です。  
  
### <a name="remarks"></a>コメント  
 この関数で埋め込み先フレーム ウィンドウを作成するには、ビュー内にあるスクロール バーの描画、サーバー コンテナーと共有、フレーム コントロールの追加、アクティブなオブジェクトを設定し、最後に、埋め込み先フレーム ウィンドウを示していますおよびフォーカスを設定メニューを設定します。  
  
##  <a name="onapplyviewstate"></a>  CDocObjectServer::OnApplyViewState  
 DocObject ビューの状態を復元するには、この関数をオーバーライドします。  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`ビュー ステートをシリアル化するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 インスタンス化の後に最初に、ビューが表示されるときに、この関数が呼び出されます。 `OnApplyViewState` データに基づいて再初期化するためのビューに指示、`CArchive`以前に保存されているオブジェクト[OnSaveViewState](#onsaveviewstate)です。 ビューのデータを検証する必要があります、`CArchive`オブジェクトをコンテナーは任意の方法で、ビュー状態データを解釈しようとはしません。  
  
 使用することができます`OnSaveViewState`ビューの状態を特定の永続的な情報を格納します。 オーバーライドする場合は`OnSaveViewState`情報を格納するにはオーバーライドする`OnApplyViewState`にその情報を参照し、新しくアクティブになったときに、ビューに適用します。  
  
##  <a name="onsaveviewstate"></a>  CDocObjectServer::OnSaveViewState  
 DocObject ビューに関する特別な状態情報を保存するには、この関数をオーバーライドします。  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`ビュー ステートがシリアル化するオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 状態には、ビューの種類、倍率、カーソルと選択ポイントなどのプロパティが含まれます。 コンテナーは、通常、ビューの非アクティブ化する前にこの関数を呼び出します。 保存された状態は、利用後で復元できます[OnApplyViewState](#onapplyviewstate)です。  
  
 使用することができます`OnSaveViewState`ビューの状態を特定の永続的な情報を格納します。 オーバーライドする場合は`OnSaveViewState`情報を格納するにはオーバーライドする`OnApplyViewState`にその情報を参照し、新しくアクティブになったときに、ビューに適用します。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)

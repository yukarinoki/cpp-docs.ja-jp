---
title: COleServerItem クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
dev_langs:
- C++
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4c5dad276db338b5efa0d15786b090779fcf41a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207506"
---
# <a name="coleserveritem-class"></a>COleServerItem クラス
OLE アイテムへのサーバー インターフェイスが用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|`COleServerItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|プレゼンテーションおよび変換形式の配置を`COleDataSource`オブジェクト。|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|項目をクリップボードにコピーします。|  
|[判定できます。](#dodragdrop)|ドラッグ アンド ドロップ操作を実行します。|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|データ転送 (クリップボードやドラッグ アンド ドロップ) で使用するためには、データ ソースを取得します。|  
|[COleServerItem::GetDocument](#getdocument)|項目を含むサーバーのドキュメントを返します。|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|OLE 項目の CF_EMBEDSOURCE データを取得します。|  
|[COleServerItem::GetItemName](#getitemname)|項目の名前を返します。 リンクされた項目のみに使用されます。|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|OLE 項目の CF_LINKSOURCE データを取得します。|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|OLE 項目の CF_OBJECTDESCRIPTOR データを取得します。|  
|[COleServerItem::IsConnected](#isconnected)|項目が現在作業中のコンテナーに接続されているかどうかを示します。|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|項目がリンクされている OLE 項目を表すかどうかを示します。|  
|[COleServerItem::NotifyChanged](#notifychanged)|自動リンクの更新では、すべてのコンテナーを更新します。|  
|[COleServerItem::OnDoVerb](#ondoverb)|動詞を実行すると呼ばれます。|  
|[:Ondraw](#ondraw)|コンテナー アイテムの描画を要求するときに呼び出されます必要な実装です。|  
|[COleServerItem::OnDrawEx](#ondrawex)|特殊な項目の描画に呼び出されます。|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|クリップボードにコピーされるデータを取得するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnGetExtent](#ongetextent)|OLE 項目のサイズを取得するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|指定したデータ転送オブジェクトの内容を使用して OLE 項目を初期化するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|リンク項目を更新する必要かどうかを判断するには、呼び出されます。|  
|[COleServerItem::OnRenderData](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|データを取得、`CFile`遅延レンダリングの一部としてのオブジェクト。|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|遅延レンダリングの一部として hglobal データを取得します。|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|アイテムの配色を設定すると呼ばれます。|  
|[COleServerItem::OnSetData](#onsetdata)|項目のデータを設定すると呼ばれます。|  
|[COleServerItem::OnSetExtent](#onsetextent)|OLE 項目のサイズを設定するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnUpdate](#onupdate)|呼ばれるには、ドキュメント、項目の一部が属している場合は変更されます。|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|サーバー ドキュメントのすべてのアイテムのプレゼンテーションのキャッシュを更新するには、呼び出されます。|  
|[COleServerItem::SetItemName](#setitemname)|項目の名前を設定します。 リンクされた項目のみに使用されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[は](#getdatasource)|変換形式の格納に使用するオブジェクトを取得します。|  
|[COleServerItem::OnHide](#onhide)|OLE 項目を非表示にするためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnOpen](#onopen)|OLE 項目を最上位レベルのウィンドウに表示するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnShow](#onshow)|コンテナーの要求、アイテムを表示するときに呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|OLE 項目の量が表示される詳細については、サーバーに通知します。|  
  
## <a name="remarks"></a>Remarks  
 リンクされた項目には、サーバー ドキュメントの一部またはすべてを表すことができます。 埋め込みアイテムは、常に、サーバー全体のドキュメントを表します。  
  
 `COleServerItem`クラスを定義 OLE システム ダイナミック リンク ライブラリ (Dll) によって呼び出されるいくつかのオーバーライド可能なメンバー関数は、通常、コンテナーのアプリケーションからの要求に応答します。 これらのメンバー関数は、表示や、その動詞を実行するさまざまな形式でデータの取得元でなど、さまざまな方法で間接的に項目を操作するコンテナー アプリケーションを許可します。  
  
 使用する`COleServerItem`、そこから派生クラスを作成および実装、 [OnDraw](#ondraw)と[Serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数。 `OnDraw`関数は、コンテナー アプリケーションは、複合ドキュメントを開いたときに表示することができます、項目のメタファイル表現を提供します。 `Serialize`関数の`CObject`埋め込みアイテム サーバーとコンテナーのアプリケーション間で転送されるようにする、項目のネイティブな表現を提供します。 [OnGetExtent](#ongetextent)自然なアイテムのサイズのコンテナーを有効にすると、コンテナーに項目のサイズを提供します。  
  
 サーバーとの関連トピックに関する詳細については、記事を参照してください。[サーバー: サーバーを実装する](../../mfc/servers-implementing-a-server.md)と"を作成するコンテナー/サーバー アプリケーションを"記事[コンテナー: 高度な機能](../../mfc/containers-advanced-features.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="addotherclipboarddata"></a>  COleServerItem::AddOtherClipboardData  
 指定した OLE 項目のプレゼンテーションおよび変換の形式を配置するには、この関数を呼び出す`COleDataSource`オブジェクト。  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDataSource*  
 ポインター、`COleDataSource`オブジェクトのデータを配置する必要があります。  
  
### <a name="remarks"></a>Remarks  
 実装している必要があります、 [OnDraw](#ondraw)メンバー関数は、項目の表示形式 (メタファイル画像) を提供します。 その他の変換の形式をサポートするためにそれらの登録を使用して、 [COleDataSource](../../mfc/reference/coledatasource-class.md)によって返されるオブジェクト[GetDataSource](#getdatasource)をオーバーライドし、[は](#onrenderdata)メンバー関数をサポートする形式でデータを提供します。  
  
##  <a name="coleserveritem"></a>  COleServerItem::COleServerItem  
 構築、`COleServerItem`オブジェクトし、ドキュメントの項目のサーバー ドキュメントのコレクションに追加します。  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *pServerDoc*  
 新しい項目を含むドキュメントへのポインター。  
  
 *bAutoDelete*  
 リンクがリリースされたときに、オブジェクトを削除できるかどうかを示すフラグします。 この場合は FALSE に設定、`COleServerItem`オブジェクトが削除する必要がありますドキュメントのデータの不可欠な部分です。 オブジェクトの場合は TRUE に設定を削除するには、フレームワークをドキュメントのデータの範囲を識別するために使用されるセカンダリ構造です。  
  
##  <a name="copytoclipboard"></a>  COleServerItem::CopyToClipboard  
 OLE 項目をクリップボードにコピーするには、この関数を呼び出します。  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bIncludeLink*  
 この場合に TRUE に設定リンク データをクリップボードにコピーする必要があります。 サーバーの場合は FALSE に設定アプリケーションへのリンクをサポートしません。  
  
### <a name="remarks"></a>Remarks  
 関数を使用して、 [OnGetClipboardData](#ongetclipboarddata)メンバー関数を作成する、 [COleDataSource](../../mfc/reference/coledatasource-class.md)サポートされている形式の OLE 項目のデータを含むオブジェクト。 関数を配置し、`COleDataSource`を使用してクリップボード上のオブジェクト、 [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard)関数。 `COleDataSource`オブジェクトにはサポートするすべての変換形式のデータと同様に、CF_METAFILEPICT 形式で、項目のネイティブ データとその表現が含まれます。 実装している必要があります[Serialize](../../mfc/reference/cobject-class.md#serialize)と[OnDraw](#ondraw)させるには、このメンバー関数。  
  
##  <a name="dodragdrop"></a>  判定できます。  
 呼び出す、`DoDragDrop`ドラッグ アンド ドロップ操作を実行するメンバー関数。  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRectItem*  
 クライアント領域を基準とのピクセル単位での画面でアイテムの四角形。  
  
 *ptOffset*  
 オフセット*示す*ドラッグ時に、マウスの位置があった場所。  
  
 *bIncludeLink*  
 この場合に TRUE に設定リンク データをクリップボードにコピーする必要があります。 アプリケーションがリンクをサポートしていない場合は FALSE に設定します。  
  
 *dwEffects*  
 ドラッグ元がドラッグ操作 (コピー、移動、およびリンクの組み合わせ) で許可する効果を決定します。  
  
 *lpRectStartDrag*  
 実際には、ドラッグの開始位置を定義する四角形を指すポインター。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 列挙値。 行った場合は、元のデータを削除する必要があります。  
  
### <a name="remarks"></a>Remarks  
 ドラッグ アンド ドロップ操作はすぐに開始されません。 指定された四角形をマウス カーソルが離れる待機*lpRectStartDrag*または指定したミリ秒数が経過するまでです。 場合*lpRectStartDrag*が null の場合、マウス カーソルが 1 つのピクセルを移動すると、ドラッグが起動されるように、既定の長方形を使用します。  
  
 時刻の遅延は、レジストリ キーの設定によって指定されます。 遅延時間を変更するには呼び出すことによって[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)します。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグの遅延時間は、次のように格納されます。  
  
-   Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。  
  
-   Windows 3.x ドラッグの遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクション。  
  
-   Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI します。  
  
 レジストリのいずれかの遅延情報が格納されている方法の詳細についてはドラッグのまたはします。INI ファイルを参照してください[WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) Windows SDK に含まれています。  
  
##  <a name="getclipboarddata"></a>  COleServerItem::GetClipboardData  
 指定した入力するには、この関数を呼び出す[COleDataSource](../../mfc/reference/coledatasource-class.md)を呼び出した場合、クリップボードにコピーされるすべてのデータ オブジェクト[CopyToClipboard](#copytoclipboard) (場合、同じデータを転送もがします。呼ばれる[DoDragDrop](#dodragdrop))。  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDataSource*  
 ポインター、`COleDataSource`をすべてサポートされている形式で OLE 項目のデータを受け取るオブジェクト。  
  
 *bIncludeLink*  
 TRUE の場合、リンク データをクリップボードにコピーする必要があります。 サーバー アプリケーションがリンクをサポートしていない場合は FALSE。  
  
 *lpOffset*  
 オブジェクトの配信元からマウス カーソルのピクセル単位のオフセット。  
  
 *lpSize*  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出して、 [GetEmbedSourceData](#getembedsourcedata) OLE アイテムと呼び出しのネイティブのデータを取得するメンバー関数、 [AddOtherClipboardData](#addotherclipboarddata)プレゼンテーション形式といずれかを取得するメンバー関数変換形式をサポートします。 場合*bIncludeLink*が true の場合、関数も、呼び出し[GetLinkSourceData](#getlinksourcedata)リンク データ項目を取得します。  
  
 形式を配置する場合は、この関数をオーバーライドする`COleDataSource`オブジェクトによって提供されるこれらの形式の前後に`CopyToClipboard`。  
  
##  <a name="getdatasource"></a>  は  
 取得するには、この関数を呼び出し、 [COleDataSource](../../mfc/reference/coledatasource-class.md)サーバー アプリケーションがサポートする変換形式の格納に使用されるオブジェクト。  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`COleDataSource`オブジェクトへの変換の形式を格納するために使用します。  
  
### <a name="remarks"></a>Remarks  
 操作データの転送中にさまざまな形式でデータを提供する、サーバー アプリケーションを実行する場合に、登録済みの形式で、`COleDataSource`この関数によって返されるオブジェクト。 たとえば、クリップボードまたはドラッグ アンド ドロップ操作の OLE 項目のされているテキスト表現を指定する場合は、書式を登録は、`COleDataSource`オブジェクトがこの関数から制御が戻ると、上書き、`OnRenderXxxData`するメンバー関数データを提供します。  
  
##  <a name="getdocument"></a>  COleServerItem::GetDocument  
 項目を含むドキュメントへのポインターを取得するには、この関数を呼び出します。  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目を含むドキュメントへのポインターアイテム、ドキュメントの一部でない場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 これにより、サーバーのドキュメントへの引数として渡したへのアクセス、`COleServerItem`コンス トラクター。  
  
##  <a name="getembedsourcedata"></a>  COleServerItem::GetEmbedSourceData  
 OLE 項目の CF_EMBEDSOURCE データを取得するには、この関数を呼び出します。  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpStgMedium*  
 ポインター、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) OLE アイテムの CF_EMBEDSOURCE データを受け取る構造体。  
  
### <a name="remarks"></a>Remarks  
 この形式には、項目のネイティブのデータが含まれています。 実装している必要があります、`Serialize`適切に機能するには、この関数のメンバー関数。  
  
 結果を使用してデータ ソースに追加された[取得](../../mfc/reference/coledatasource-class.md#cachedata)します。 この関数はによって自動的に呼び出されます[COleServerItem::OnGetClipboardData](#ongetclipboarddata)します。  
  
 詳細については、次を参照してください。 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK に含まれています。  
  
##  <a name="getitemname"></a>  COleServerItem::GetItemName  
 項目の名前を取得するには、この関数を呼び出します。  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目の名前。  
  
### <a name="remarks"></a>Remarks  
 通常、この関数は、リンクされた項目に対してのみ呼び出します。  
  
##  <a name="getlinksourcedata"></a>  COleServerItem::GetLinkSourceData  
 OLE 項目の CF_LINKSOURCE データを取得するには、この関数を呼び出します。  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpStgMedium*  
 ポインター、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) OLE アイテムの CF_LINKSOURCE データを受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この形式には、OLE アイテムと OLE 項目を含むドキュメントの検索に必要な情報の種類を示す CLSID が含まれています。  
  
 結果は後でデータ ソースに追加できます[取得](../../mfc/reference/coledatasource-class.md#cachedata)します。 この関数はによって自動的に呼び出されます[OnGetClipboardData](#ongetclipboarddata)します。  
  
 詳細については、次を参照してください。 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK に含まれています。  
  
##  <a name="getobjectdescriptordata"></a>  COleServerItem::GetObjectDescriptorData  
 OLE 項目の CF_OBJECTDESCRIPTOR データを取得するには、この関数を呼び出します。  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpOffset*  
 マウスのオフセットは、OLE アイテムの左上隅をクリックします。 NULL にすることができます。  
  
 *lpSize*  
 OLE 項目のサイズ。 NULL にすることができます。  
  
 *lpStgMedium*  
 ポインター、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) OLE アイテムの CF_OBJECTDESCRIPTOR データを受け取る構造体。  
  
### <a name="remarks"></a>Remarks  
 情報は、コピー、`STGMEDIUM`によって示される構造*lpStgMedium*します。 この形式には、貼り付け ダイアログに必要な情報が含まれています。  
  
 詳細については、次を参照してください。 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK に含まれています。  
  
##  <a name="isconnected"></a>  COleServerItem::IsConnected  
 OLE 項目が接続されているかどうかには、この関数を呼び出します。  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目が接続されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 OLE アイテムは、1 つまたは複数のコンテナーの項目への参照がある場合に接続されていると見なされます。 項目は、参照カウントが 0 より大きい場合、または埋め込みアイテムである場合に接続されています。  
  
##  <a name="islinkeditem"></a>  COleServerItem::IsLinkedItem  
 この関数では、OLE 項目がリンクされた項目を参照してください。  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、項目は、リンクされた項目。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 項目が有効では、埋め込みアイテムのドキュメントの一覧が返されない場合、項目がリンクされます。 リンクされた項目は、コンテナーに接続できない場合もあります。  
  
 リンクと埋め込みの両方の項目に同じクラスを使用する一般的です。 `IsLinkedItem` 何度もコードが普通ですが、埋め込みアイテムは、異なる動作にリンクされた項目を作成することができます。  
  
##  <a name="m_sizeextent"></a>  COleServerItem::m_sizeExtent  
 このメンバーは、コンテナーのドキュメントに表示されるオブジェクトの量は、サーバーを指示します。  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>Remarks  
 既定の実装[OnSetExtent](#onsetextent)このメンバーを設定します。  
  
##  <a name="notifychanged"></a>  COleServerItem::NotifyChanged  
 リンクされた項目が変更された後は、この関数を呼び出します。  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrawAspect*  
 OLE 項目の特徴を示す列挙型の値が変更されました。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- DVASPECT_CONTENT 項目は、そのコンテナー内の埋め込みオブジェクトとして表示されることがこのような方法で表されます。  
  
- DVASPECT_THUMBNAIL アイテムは、参照ツールで表示できるように、「サムネイル」表記で表示されます。  
  
- DVASPECT_ICON 項目がアイコンで表されます。  
  
- [ファイル] メニューから [印刷] コマンドを使用して印刷した場合と、DVASPECT_DOCPRINT 項目が表されます。  
  
### <a name="remarks"></a>Remarks  
 コンテナー アイテムが自動のリンクを使用して、ドキュメントにリンクされている場合は、変更を反映するように、項目が更新されます。 Microsoft Foundation Class ライブラリを使用して記述されたコンテナーのアプリケーションで[として](../../mfc/reference/coleclientitem-class.md#onchange)は応答で呼び出されます。  
  
##  <a name="ondoverb"></a>  COleServerItem::OnDoVerb  
 指定した動詞を実行するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 *iVerb*  
 実行する動詞を指定します。 次のいずれかを指定できます。  
  
|[値]|説明|シンボル|  
|-----------|-------------|------------|  
|0|主動詞|OLEIVERB_PRIMARY|  
|1|セカンダリの動詞|(なし)|  
|- 1|編集するための表示項目|で|  
|- 2|別のウィンドウで項目を編集します。|OLEIVERB_OPEN|  
|- 3|アイテムを非表示します。|OLEIVERB_HIDE|  
  
 -1 という値は、通常、他の動詞のエイリアスです。 編集のオープンがサポートされていない場合は、-1 と同じ効果が-2。 追加の値を参照してください。 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK に含まれています。  
  
### <a name="remarks"></a>Remarks  
 場合は、コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが、この関数を呼び出すときに、 [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate)メンバー関数は、対応する`COleClientItem`オブジェクトが呼び出されます。 既定の実装、 [OnShow](#onshow)主動詞またはでが指定されている場合、メンバー関数[OnOpen](#onopen)セカンダリ動詞または OLEIVERB_OPEN が指定されている場合と[OnHide](#onhide)は場合。 既定の実装`OnShow`場合*iVerb*上に示した動詞のいずれかではありません。  
  
 主動詞は、アイテムを表示しない場合は、この関数をオーバーライドします。 たとえば、項目が録音その主動詞が再生の場合は、項目を再生するサーバー アプリケーションを表示する必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK に含まれています。  
  
##  <a name="ondraw"></a>  :Ondraw  
 OLE 項目をメタファイルに表示するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)項目を描画する対象となるオブジェクト。 ディスプレイ コンテキストは、属性の関数が使えるように、自動的に属性のディスプレイ コンテキストに接続します。  
  
 *rSize*  
 メタファイルに描画するための HIMETRIC 単位のサイズ。  
  
### <a name="return-value"></a>戻り値  
 項目が描画できた場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 OLE 項目のメタファイルの表現を使用して、コンテナー アプリケーションでアイテムを表示します。 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが場合、メタファイルで使用、[描画](../../mfc/reference/coleclientitem-class.md#draw)メンバー関数は、対応する[COleClientItem](../../mfc/reference/coleclientitem-class.md)オブジェクト。 既定の実装はありません。 指定されたデバイス コンテキストに項目を描画するには、この関数をオーバーライドする必要があります。  
  
##  <a name="ondrawex"></a>  COleServerItem::OnDrawEx  
 すべての描画するためのフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)項目を描画する対象となるオブジェクト。 DC は、属性の関数が使えるように、自動的に属性の DC に接続します。  
  
 *nDrawAspect*  
 列挙型の値。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- DVASPECT_CONTENT 項目は、そのコンテナー内の埋め込みオブジェクトとして表示されることがこのような方法で表されます。  
  
- DVASPECT_THUMBNAIL アイテムは、参照ツールで表示できるように、「サムネイル」表記で表示されます。  
  
- DVASPECT_ICON 項目がアイコンで表されます。  
  
- [ファイル] メニューから [印刷] コマンドを使用して印刷した場合と、DVASPECT_DOCPRINT 項目が表されます。  
  
 *rSize*  
 HIMETRIC 単位内の項目のサイズ。  
  
### <a name="return-value"></a>戻り値  
 項目が描画できた場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 既定の実装`OnDraw`型が DVASPECT_CONTENT; に失敗します。  
  
 DVASPECT_ICON または DVASPECT_THUMBNAIL などの DVASPECT_CONTENT 以外の側面のプレゼンテーションにデータを提供するには、この関数をオーバーライドします。  
  
##  <a name="ongetclipboarddata"></a>  COleServerItem::OnGetClipboardData  
 取得するためにフレームワークによって呼び出される、`COleDataSource`への呼び出しで、クリップボードに配置がすべてのデータを格納しているオブジェクト、 [CopyToClipboard](#copytoclipboard)メンバー関数。  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *bIncludeLink*  
 この場合に TRUE に設定リンク データをクリップボードにコピーする必要があります。 サーバーの場合は FALSE に設定アプリケーションへのリンクをサポートしません。  
  
 *lpOffset*  
 マウスのカーソル (ピクセル単位) のオブジェクトの配信元からのオフセット。  
  
 *lpSize*  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="return-value"></a>戻り値  
 ポインターを[COleDataSource](../../mfc/reference/coledatasource-class.md)クリップボードのデータを格納しているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装を呼び出す[GetClipboardData](#getclipboarddata)します。  
  
##  <a name="ongetextent"></a>  COleServerItem::OnGetExtent  
 OLE 項目の HIMETRIC 単位のサイズを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrawAspect*  
 境界を取得する OLE アイテムの外観を指定します。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- DVASPECT_CONTENT 項目は、そのコンテナー内の埋め込みオブジェクトとして表示されることがこのような方法で表されます。  
  
- DVASPECT_THUMBNAIL アイテムは、参照ツールで表示できるように、「サムネイル」表記で表示されます。  
  
- DVASPECT_ICON 項目がアイコンで表されます。  
  
- [ファイル] メニューから [印刷] コマンドを使用して印刷した場合と、DVASPECT_DOCPRINT 項目が表されます。  
  
 *rSize*  
 参照を`CSize`OLE 項目のサイズを受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 場合は、コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが、この関数を呼び出すときに、 [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent)メンバー関数は、対応する`COleClientItem`オブジェクトが呼び出されます。 既定の実装では、何も行われません。 必要があります、自分で実装します。 OLE 項目のサイズの要求を処理するときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="onhide"></a>  COleServerItem::OnHide  
 OLE 項目を非表示にするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Remarks  
 既定の呼び出し`COleServerDoc::OnShowDocument( FALSE )`します。 関数には、OLE 項目を非表示にされたコンテナーも通知します。 OLE 項目を非表示するときに特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="oninitfromdata"></a>  COleServerItem::OnInitFromData  
 内容を使用して OLE 項目を初期化するためにフレームワークによって呼び出されます*pDataObject*します。  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDataObject*  
 OLE 項目を初期化するためのさまざまな形式でデータを含む OLE データ オブジェクトへのポインター。  
  
 *bCreation*  
 TRUE の場合、関数は、コンテナー アプリケーションで新しく作成される OLE 項目を初期化するために呼び出されます。 既存の OLE 項目の内容を置き換える、関数が呼び出された場合は FALSE です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 場合*bCreation*が true の場合、コンテナーが現在の選択に基づく挿入の新しいオブジェクトを実装している場合、この関数が呼び出されます。 選択したデータは、新しい OLE 項目を作成するときに使用されます。 などのときのスプレッドシート プログラムでのセルの範囲を選択して、グラフを作成し、新しいオブジェクトの挿入を使用してに基づいて選択範囲の値。 既定の実装では、何も行われません。 によって提供されるものと、許容される形式を選択するには、この関数をオーバーライド*pDataObject*と提供されたデータに基づく OLE 項目を初期化します。 これは、高度なオーバーライド可能な。  
  
 詳細については、次を参照してください。 [IOleObject::InitFromData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-initfromdata) Windows SDK に含まれています。  
  
##  <a name="onopen"></a>  COleServerItem::OnOpen  
 配置ではなく、サーバー アプリケーションの別のインスタンスで OLE 項目を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>Remarks  
 既定の実装を OLE アイテムを含むドキュメントを表示する最初のフレーム ウィンドウをアクティブ化します。アプリケーションがミニ サーバーの場合、既定の実装には、メイン ウィンドウが表示されます。 関数には、OLE アイテムが開かれているコンテナーも通知します。  
  
 OLE 項目を開くときに、特別な処理を実行する場合は、この関数をオーバーライドします。 これは、開かれたときのリンクを選択範囲を設定するリンクされた項目に共通します。  
  
 詳細については、次を参照してください。 [IOleClientSite::OnShowWindow](/windows/desktop/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) Windows SDK に含まれています。  
  
##  <a name="onqueryupdateitems"></a>  COleServerItem::OnQueryUpdateItems  
 現在のサーバーのドキュメントにリンク項目が最新でないかどうかを判断するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの更新が必要なアイテムがある場合、0 以外の場合すべての項目が最新の状態の場合は 0。  
  
### <a name="remarks"></a>Remarks  
 元のドキュメントが変更されましたが、文書の変更を反映するようにリンクされた項目が更新されていない場合、項目は期限切れです。  
  
##  <a name="onrenderdata"></a>  COleServerItem::OnRenderData  
 指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpFormatEtc*  
 指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)情報が要求された形式を指定します。  
  
 *lpStgMedium*  
 指す、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)データが返される構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)または[DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を呼び出す[関数](#onrenderfiledata)または[によって](#onrenderglobaldata)、それぞれに、指定のストレージ メディアは、ファイルまたはメモリがある場合。 これらの形式のどちらでもない場合は、既定の実装は 0 を返し、何も行いません。  
  
 場合*lpStgMedium*-> *tymed* TYMED_NULL には、STGMEDIUM が割り当てられている必要がありで指定された入力*lpFormatEtc tymed]-> [* します。 存在しない場合に、データが配置 TYMED_NULL、STGMEDIUM を入力する必要があります。  
  
 これは、高度なオーバーライド可能な。 要求された形式および中規模のデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドすることがあります。 データが小さく、固定サイズの場合は、オーバーライド`OnRenderGlobalData`します。 データは、ファイルでは、または可変サイズは、オーバーライド`OnRenderFileData`します。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata)、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)、と[TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed) Windows SDK に含まれています。  
  
##  <a name="onrenderfiledata"></a>  COleServerItem::OnRenderFileData  
 ファイルのストレージ メディアは、指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpFormatEtc*  
 指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)情報が要求された形式を指定します。  
  
 *pFile*  
 指す、`CFile`データがレンダリングされるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装は、単に FALSE を返します。  
  
 これは、高度なオーバーライド可能な。 要求された形式および中規模のデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする可能性があります。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データは、ファイルでは、または可変サイズは、オーバーライド[可変](#onrenderfiledata)します。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata)と[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK に含まれています。  
  
##  <a name="onrenderglobaldata"></a>  COleServerItem::OnRenderGlobalData  
 指定したストレージ メディアがグローバル メモリに指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpFormatEtc*  
 指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)情報が要求された形式を指定します。  
  
 *phGlobal*  
 データが返されるグローバル メモリ ハンドルへのポインター。 メモリが割り当てられていない場合、このパラメーターは NULL を指定できます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装は、単に FALSE を返します。  
  
 場合*phGlobal*新しい HGLOBAL を割り当てられで返される必要がありますし、NULL の場合は、 *phGlobal*します。 指定された、HGLOBAL のそれ以外の場合、 *phGlobal*データが格納される必要があります。 HGLOBAL で配置されるデータ量は、メモリ ブロックの現在のサイズを超えない必要があります。 また、ブロックより大きなサイズに再割り当てできることはできません。  
  
 これは、高度なオーバーライド可能な。 要求された形式および中規模のデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドすることがあります。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データは、ファイルでは、または可変サイズは、オーバーライド[可変](#onrenderfiledata)します。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata)と[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK に含まれています。  
  
##  <a name="onsetcolorscheme"></a>  COleServerItem::OnSetColorScheme  
 OLE 項目を編集するときに使用するカラー パレットを指定するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogPalette*  
 Windows へのポインター[保持](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette)構造体。  
  
### <a name="return-value"></a>戻り値  
 カラー パレットを使用する場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数が時に呼び出される場合は、コンテナー アプリケーションは、Microsoft Foundation Class ライブラリを使用して記述されました、 [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme)関数に対応する`COleClientItem`オブジェクトが呼び出されます。 既定の実装では、FALSE を返します。 推奨パレットを使用する場合は、この関数をオーバーライドします。 サーバー アプリケーションでは、推奨パレットを使用する必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) Windows SDK に含まれています。  
  
##  <a name="onsetdata"></a>  COleServerItem::OnSetData  
 OLE 項目のデータを指定されたデータに置き換えるために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpFormatEtc*  
 ポインターを[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)データの形式を指定します。  
  
 *lpStgMedium*  
 ポインターを[STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)データが存在する構造体します。  
  
 *bRelease*  
 関数呼び出しの完了後、ストレージ メディアの所有権を持っているユーザーを示します。 呼び出し元は、ストレージ メディアの代わりに割り当てられたリソースを解放するため担当するユーザーを決定します。 呼び出し元は設定することによって*bRelease*します。 場合*bRelease*が 0 以外の場合、サーバーのアイテムは所有権を取得、使用が完了したら、メディアを解放します。 ときに*bRelease* 0 は、呼び出し元が所有権を保持およびサーバー項目がストレージ メディアを使用して、呼び出しの期間に対してのみです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 正常に取得するまで、サーバー項目によるデータの所有権はなりません。 これは所有権を取得できない場合は 0 を返します。 呼び出すことによってストレージ メディアを解放、データ ソースに所有権がある場合は、パラメーター、 [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium)関数。  
  
 既定の実装では、何も行われません。 OLE 項目のデータを指定されたデータに置き換えるには、この関数をオーバーライドします。 これは、高度なオーバーライド可能な。  
  
 詳細については、次を参照してください。 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)、と[ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) Windows SDK に含まれています。  
  
##  <a name="onsetextent"></a>  COleServerItem::OnSetExtent  
 OLE 項目領域の量は、コンテナーのドキュメントで使用することを確認するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrawAspect*  
 境界が指定されている OLE 項目の外観を指定します。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- DVASPECT_CONTENT 項目は、そのコンテナー内の埋め込みオブジェクトとして表示されることがこのような方法で表されます。  
  
- DVASPECT_THUMBNAIL アイテムは、参照ツールで表示できるように、「サムネイル」表記で表示されます。  
  
- DVASPECT_ICON 項目がアイコンで表されます。  
  
- [ファイル] メニューから [印刷] コマンドを使用して印刷した場合と、DVASPECT_DOCPRINT 項目が表されます。  
  
 *size*  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) OLE 項目の新しいサイズを指定する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 場合は、コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが、この関数を呼び出すときに、 [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent)メンバー関数は、対応する`COleClientItem`オブジェクトが呼び出されます。 既定の実装の設定、[です](#m_sizeextent)、指定されたサイズのメンバー場合*nDrawAspect* DVASPECT_CONTENT; は、それ以外の場合 0 を返します。 アイテムのサイズを変更すると、特別な処理を実行するには、この関数をオーバーライドします。  
  
##  <a name="onshow"></a>  COleServerItem::OnShow  
 OLE 項目の場所で表示するサーバー アプリケーションに指示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Remarks  
 表示される項目を必要があるコンテナー アプリケーションのユーザーがアイテムの作成や編集などの動詞を実行時に、この関数は通常呼び出されます。 既定の実装では、インプレース アクティブ化を試行します。 失敗したかどうか、関数呼び出し、 `OnOpen` OLE 項目を別のウィンドウで表示するメンバー関数。  
  
 OLE 項目が表示されるときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="onupdate"></a>  COleServerItem::OnUpdate  
 項目が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnUpdate(
    COleServerItem* pSender,  
    LPARAM lHint,  
    CObject* pHint,  
    DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSender*  
 ドキュメントを変更する項目へのポインター。 NULL にすることができます。  
  
 *lHint*  
 変更に関する情報が含まれています。  
  
 *pHint*  
 変更に関する情報を格納するオブジェクトへのポインター。  
  
 *nDrawAspect*  
 列挙型の値。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- DVASPECT_CONTENT 項目は、そのコンテナー内の埋め込みオブジェクトとして表示されることがこのような方法で表されます。  
  
- DVASPECT_THUMBNAIL アイテムは、参照ツールで表示できるように、「サムネイル」表記で表示されます。  
  
- DVASPECT_ICON 項目がアイコンで表されます。  
  
- [ファイル] メニューから [印刷] コマンドを使用して印刷した場合と、DVASPECT_DOCPRINT 項目が表されます。  
  
### <a name="remarks"></a>Remarks  
 既定の実装[NotifyChanged](#notifychanged)ヒントや送信者に関係なく、します。  
  
##  <a name="onupdateitems"></a>  COleServerItem::OnUpdateItems  
 サーバー ドキュメントのすべての項目を更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>Remarks  
 既定の実装[UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)すべて`COleClientItem`ドキュメント内のオブジェクト。  
  
##  <a name="setitemname"></a>  COleServerItem::SetItemName  
 その名前を設定するリンクされた項目を作成するときに、この関数を呼び出します。  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszItemName*  
 項目の新しい名前へのポインター。  
  
### <a name="remarks"></a>Remarks  
 名前は、ドキュメント内で一意である必要があります。 リンクされた項目を編集するサーバー アプリケーションが呼び出されると、アプリケーションはこの名前を使用して、項目を検索します。 埋め込みアイテムに対してこの関数を呼び出す必要はありません。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CDocItem クラス](../../mfc/reference/cdocitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)

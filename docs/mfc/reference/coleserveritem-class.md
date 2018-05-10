---
title: COleServerItem クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 4d3165a11aace54ce2062a6321acc7f911fbdc39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|プレゼンテーションと変換の形式の配置、`COleDataSource`オブジェクト。|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|項目をクリップボードにコピーします。|  
|[判定できます。](#dodragdrop)|ドラッグ アンド ドロップ操作を実行します。|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|データ転送 (クリップボードやドラッグ アンド ドロップ) で使用するためには、データ ソースを取得します。|  
|[COleServerItem::GetDocument](#getdocument)|項目を含むサーバー ドキュメントを返します。|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|取得、 **CF_EMBEDSOURCE** OLE アイテムのデータ。|  
|[COleServerItem::GetItemName](#getitemname)|アイテムの名前を返します。 リンクされた項目のみに使用されます。|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|取得、 `CF_LINKSOURCE` OLE アイテムのデータ。|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|取得、 **CF_OBJECTDESCRIPTOR** OLE アイテムのデータ。|  
|[COleServerItem::IsConnected](#isconnected)|アイテムがアクティブなコンテナーに現在アタッチされているかどうかを示します。|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|項目がリンクされている OLE 項目を表すかどうかを示します。|  
|[COleServerItem::NotifyChanged](#notifychanged)|自動リンクの更新では、すべてのコンテナーを更新します。|  
|[COleServerItem::OnDoVerb](#ondoverb)|動詞を実行するには、呼び出されます。|  
|[:Ondraw](#ondraw)|コンテナー アイテムの描画を要求するときに呼び出されます必要な実装です。|  
|[COleServerItem::OnDrawEx](#ondrawex)|特殊化されたアイテムの描画に呼び出されます。|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|クリップボードにコピーされるデータを取得するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnGetExtent](#ongetextent)|OLE 項目のサイズを取得するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|指定したデータ転送オブジェクトのコンテンツを使用して OLE 項目を初期化するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|リンク項目を更新する必要かどうかを決定するには、呼び出されます。|  
|[COleServerItem::OnRenderData](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|データを取得、`CFile`遅延レンダリングの一部としてオブジェクト。|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|データを取得、`HGLOBAL`遅延レンダリングの一部として。|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|アイテムの配色を設定すると呼ばれます。|  
|[COleServerItem::OnSetData](#onsetdata)|アイテムのデータを設定すると呼ばれます。|  
|[COleServerItem::OnSetExtent](#onsetextent)|OLE 項目のサイズを設定するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnUpdate](#onupdate)|呼ばれるは、アイテム、ドキュメントの一部が属している場合は変更されます。|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|サーバー ドキュメントのすべてのアイテムのプレゼンテーション キャッシュを更新するには、呼び出されます。|  
|[COleServerItem::SetItemName](#setitemname)|アイテムの名前を設定します。 リンクされた項目のみに使用されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[は](#getdatasource)|変換形式の格納に使用するオブジェクトを取得します。|  
|[COleServerItem::OnHide](#onhide)|OLE 項目を非表示にするためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnOpen](#onopen)|OLE 項目をそれ自体最上位ウィンドウに表示するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnShow](#onshow)|コンテナーは、アイテムを表示する要求したときに呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|OLE 項目の量が表示される、サーバーを通知します。|  
  
## <a name="remarks"></a>コメント  
 リンクされた項目には、サーバー ドキュメントの一部またはすべてを表すことができます。 埋め込みアイテムは、常に、サーバー全体のドキュメントを表します。  
  
 `COleServerItem`クラスを定義 OLE システム ダイナミック リンク ライブラリ (Dll) によって呼び出されるいくつかのオーバーライド可能なメンバー関数通常コンテナー アプリケーションからの要求に応答します。 これらのメンバー関数では、コンテナー アプリケーションに表示する、その動詞の実行やさまざまな形式でそのデータを取得するように、さまざまな方法で間接的に項目を操作できるようにします。  
  
 使用する`COleServerItem`、クラスの派生、および実装、 [OnDraw](#ondraw)と[Serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数。 `OnDraw`関数は、コンテナー アプリケーションが複合ドキュメントを開いたときに表示されることができる、項目のメタファイルを提供します。 `Serialize`関数の`CObject`埋め込まれたアイテム、サーバーおよびコンテナー アプリケーション間で転送されるようにする、項目のネイティブな表現を提供します。 [OnGetExtent](#ongetextent)アイテムのサイズのコンテナーを有効にすると、コンテナーに項目の自然なサイズを提供します。  
  
 サーバーと関連トピックの詳細については、記事を参照してください。[サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)と作成、コンテナー/サーバーに"Application"、アーティクル[コンテナー: 高度な機能](../../mfc/containers-advanced-features.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="addotherclipboarddata"></a>  COleServerItem::AddOtherClipboardData  
 指定した OLE アイテムのプレゼンテーションと変換の形式を配置するには、この関数を呼び出す`COleDataSource`オブジェクト。  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataSource`  
 ポインター、`COleDataSource`オブジェクトのデータを配置する必要があります。  
  
### <a name="remarks"></a>コメント  
 実装している必要があります、 [OnDraw](#ondraw)アイテムの表示形式 (メタファイルの画像) を提供するメンバー関数。 形式をサポートするその他の変換、それらの登録を使用して、 [COleDataSource](../../mfc/reference/coledatasource-class.md)によって返されるオブジェクト[GetDataSource](#getdatasource)をオーバーライドし、[は](#onrenderdata)するメンバー関数サポートする形式でデータを提供します。  
  
##  <a name="coleserveritem"></a>  COleServerItem::COleServerItem  
 構築、`COleServerItem`オブジェクトし、ドキュメントの項目のサーバー ドキュメントのコレクションに追加します。  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 `pServerDoc`  
 新しい項目を含む文書へのポインター。  
  
 `bAutoDelete`  
 リンクがリリースされたときに、オブジェクトを削除するかどうかを示すフラグします。 これを設定して**FALSE**場合、`COleServerItem`オブジェクトは削除する必要がありますドキュメントのデータの重要な一部です。 これを設定して**TRUE**場合は、オブジェクトは、二次的な構造を削除するには、フレームワークをドキュメントのデータの範囲を識別するために使用します。  
  
##  <a name="copytoclipboard"></a>  COleServerItem::CopyToClipboard  
 OLE 項目をクリップボードにコピーするには、この関数を呼び出します。  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIncludeLink`  
 これを設定して**TRUE**場合は、データ リンクをクリップボードにコピーする必要があります。 これを設定して**FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
### <a name="remarks"></a>コメント  
 関数を使用して、 [OnGetClipboardData](#ongetclipboarddata)メンバー関数を作成する、 [COleDataSource](../../mfc/reference/coledatasource-class.md)サポートされている形式の OLE 項目のデータを含むオブジェクト。 関数は配置し、`COleDataSource`を使用してクリップボード上のオブジェクト、 [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard)関数。 `COleDataSource`オブジェクトは、項目のネイティブ データとその表現で`CF_METAFILEPICT`変換形式がサポートするために選択する任意のデータと同様に、形式です。 実装している必要があります[Serialize](../../mfc/reference/cobject-class.md#serialize)と[OnDraw](#ondraw)を操作するには、このメンバー関数。  
  
##  <a name="dodragdrop"></a>  判定できます。  
 呼び出す、`DoDragDrop`メンバー関数をドラッグ アンド ドロップ操作を実行します。  
  
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
 クライアント領域と相対的ピクセル単位での画面でアイテムの四角形。  
  
 `ptOffset`  
 オフセット`lpItemRect`時のドラッグが、マウスの位置であります。  
  
 `bIncludeLink`  
 これを設定して**TRUE**場合は、データ リンクをクリップボードにコピーする必要があります。 設定**FALSE**アプリがリンクをサポートしていない場合。  
  
 `dwEffects`  
 ドラッグ操作 (コピー、移動、およびリンクの組み合わせ) で、ドラッグ ソースを使用できる効果を指定します。  
  
 `lpRectStartDrag`  
 実際には、ドラッグの開始位置を定義する四角形を指すポインター。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 `DROPEFFECT` 列挙体の値。 場合は`DROPEFFECT_MOVE`、元のデータを削除する必要があります。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作がすぐに開始しません。 によって指定される四角形をマウス カーソルが離れるまで待機して`lpRectStartDrag`または指定したミリ秒数が経過するまでです。 場合`lpRectStartDrag`は**NULL**、マウス カーソルが 1 つのピクセルを移動したときに、ドラッグが起動されるように、既定の四角形を使用します。  
  
 遅延時間は、レジストリ キー設定によって指定されます。 遅延時間を変更するには呼び出すことによって[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)です。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグの遅延時間は、次のように格納されます。  
  
-   Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。  
  
-   Windows 3.x ドラッグ遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクションです。  
  
-   Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI です。  
  
 遅延の情報は、レジストリに格納されている方法の詳細についてドラッグのまたはします。INI ファイルを参照してください[WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows SDK に含まれています。  
  
##  <a name="getclipboarddata"></a>  COleServerItem::GetClipboardData  
 この関数を呼び出して、指定された塗りつぶし[COleDataSource](../../mfc/reference/coledatasource-class.md)を呼び出した場合、クリップボードにコピーされるすべてのデータを持つオブジェクト[CopyToClipboard](#copytoclipboard) (場合、同じデータを転送することはもします。呼ばれる[DoDragDrop](#dodragdrop))。  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataSource`  
 ポインター、`COleDataSource`すべてサポートされている形式で OLE 項目のデータを受け取るオブジェクト。  
  
 `bIncludeLink`  
 **TRUE**場合は、データ リンクをクリップボードにコピーする必要があります。 **FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
 `lpOffset`  
 オブジェクトの原点からのマウス カーソルのピクセル単位のオフセット。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出して、 [GetEmbedSourceData](#getembedsourcedata) OLE アイテムと呼び出しのネイティブ データを取得するメンバー関数、 [AddOtherClipboardData](#addotherclipboarddata)プレゼンテーション形式およびいずれかを取得するメンバー関数変換形式をサポートします。 場合`bIncludeLink`は**TRUE**、関数も呼び出します[GetLinkSourceData](#getlinksourcedata)リンク データ項目を取得します。  
  
 書式を設定する場合は、この関数をオーバーライドする`COleDataSource`オブジェクトによって提供されるそれらの形式の前後に`CopyToClipboard`です。  
  
##  <a name="getdatasource"></a>  は  
 取得するには、この関数を呼び出して、 [COleDataSource](../../mfc/reference/coledatasource-class.md)サーバー アプリケーションをサポートする変換形式の格納に使用されるオブジェクト。  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`COleDataSource`変換形式の格納に使用されるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 操作データの転送中にさまざまな形式でデータを提供するサーバー アプリケーションを実行する場合に、それらの形式での登録、`COleDataSource`この関数によって返されるオブジェクト。 たとえばを指定する場合、**エディット**クリップボード操作やドラッグ アンド ドロップ操作の OLE 項目の表現の形式を登録すると、`COleDataSource`この関数が返すオブジェクトとし、上書き、 **OnRenderXxxData**データを提供するメンバー関数。  
  
##  <a name="getdocument"></a>  COleServerItem::GetDocument  
 この関数では、項目を含むドキュメントへのポインターを取得します。  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目を含むドキュメントへのポインター**NULL**場合は、項目は、ドキュメントの一部ではありません。  
  
### <a name="remarks"></a>コメント  
 これによりへの引数として渡されたサーバー ドキュメントへのアクセス、`COleServerItem`コンス トラクターです。  
  
##  <a name="getembedsourcedata"></a>  COleServerItem::GetEmbedSourceData  
 取得するには、この関数を呼び出して、 **CF_EMBEDSOURCE** OLE アイテムのデータ。  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を受け取る、 **CF_EMBEDSOURCE** OLE 項目のデータ。  
  
### <a name="remarks"></a>コメント  
 この形式には、アイテムのネイティブ データが含まれています。 実装している必要があります、`Serialize`適切に機能するには、この関数のメンバー関数。  
  
 結果はしを使用してデータ ソースに追加された[取得](../../mfc/reference/coledatasource-class.md#cachedata)です。 この関数はによって自動的に呼び出されます[COleServerItem::OnGetClipboardData](#ongetclipboarddata)です。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK に含まれています。  
  
##  <a name="getitemname"></a>  COleServerItem::GetItemName  
 この関数では、アイテムの名前を取得します。  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目の名前。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は、リンクされた項目に対してのみ呼び出します。  
  
##  <a name="getlinksourcedata"></a>  COleServerItem::GetLinkSourceData  
 取得するには、この関数を呼び出して、 `CF_LINKSOURCE` OLE アイテムのデータ。  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を受け取る、 `CF_LINKSOURCE` OLE 項目のデータ。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この形式には、OLE アイテムと OLE 項目を含むドキュメントを検索するために必要な情報の種類を示す CLSID が含まれています。  
  
 結果のデータ ソースを追加できます[取得](../../mfc/reference/coledatasource-class.md#cachedata)です。 この関数はによって自動的に呼び出されます[OnGetClipboardData](#ongetclipboarddata)です。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK に含まれています。  
  
##  <a name="getobjectdescriptordata"></a>  COleServerItem::GetObjectDescriptorData  
 取得するには、この関数を呼び出して、 **CF_OBJECTDESCRIPTOR** OLE アイテムのデータ。  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpOffset`  
 マウスのオフセットは、OLE アイテムの左上隅をクリックします。 指定できます**NULL**です。  
  
 `lpSize`  
 OLE 項目のサイズです。 指定できます**NULL**です。  
  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を受け取る、 **CF_OBJECTDESCRIPTOR** OLE 項目のデータ。  
  
### <a name="remarks"></a>コメント  
 情報をコピー、 **STGMEDIUM**構造体を指す`lpStgMedium`です。 この形式には、貼り付け ダイアログ ボックスに必要な情報が含まれています。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK に含まれています。  
  
##  <a name="isconnected"></a>  COleServerItem::IsConnected  
 OLE 項目が接続されているかどうかにこの関数を呼び出します。  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目が接続されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE 項目では、1 つまたは複数のコンテナーの項目への参照がある場合に接続されていると見なされます。 項目は、参照カウントが 0 より大きい場合、または埋め込みアイテムである場合に接続されています。  
  
##  <a name="islinkeditem"></a>  COleServerItem::IsLinkedItem  
 OLE 項目がリンクされた項目を表示するには、この関数を呼び出します。  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目がリンクされた項目の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 項目が有効では、埋め込みアイテムのドキュメントのリストには返されません場合、項目がリンクされます。 リンクされた項目はなることも、コンテナーに接続されていない可能性があります。  
  
 クラスを使用して、同じリンクと埋め込みの両方の項目に共通であります。 `IsLinkedItem` 使用すると、何度も、コードが普通ですが、埋め込みアイテムは、異なる動作にリンクされた項目を作成できます。  
  
##  <a name="m_sizeextent"></a>  COleServerItem::m_sizeExtent  
 このメンバーは、オブジェクトの量は、コンテナー ドキュメントの表示をサーバーに指示します。  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>コメント  
 既定の実装[OnSetExtent](#onsetextent)このメンバーを設定します。  
  
##  <a name="notifychanged"></a>  COleServerItem::NotifyChanged  
 リンクされた項目が変更された後に、この関数を呼び出します。  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 値、 `DVASPECT` OLE 項目の特徴が変更されたかを示す列挙です。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- `DVASPECT_CONTENT` 項目は、コンテナー内の埋め込みオブジェクトとして表示されること、このような方法で表されます。  
  
- `DVASPECT_THUMBNAIL` 参照ツールで表示できるように、「サムネイル」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON` 項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT` 項目は、[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように表されます。  
  
### <a name="remarks"></a>コメント  
 コンテナー アイテムが自動のリンクを使用してドキュメントにリンクされている場合、項目は、変更を反映するように更新されます。 コンテナー アプリケーション、Microsoft Foundation Class ライブラリを使用して記述で[として](../../mfc/reference/coleclientitem-class.md#onchange)は応答で呼び出されます。  
  
##  <a name="ondoverb"></a>  COleServerItem::OnDoVerb  
 指定された動詞を実行するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 実行する動詞を指定します。 次のいずれかを指定できます。  
  
|[値]|説明|シンボル|  
|-----------|-------------|------------|  
|0|主動詞|`OLEIVERB_PRIMARY`|  
|1|セカンダリの動詞|(なし)|  
|- 1|編集するための表示項目|`OLEIVERB_SHOW`|  
|- 2|別のウィンドウで項目を編集します。|`OLEIVERB_OPEN`|  
|- 3|アイテムを非表示します。|`OLEIVERB_HIDE`|  
  
 -1 の値は、通常、他の動詞のエイリアスです。 開いている編集はサポートされていない、-2 は-1 と同じ効果がします。 追加の値を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが、この関数が呼び出されます場合に、 [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate)の対応するメンバー関数`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装、 [OnShow](#onshow)メンバー関数の場合は主動詞または`OLEIVERB_SHOW`が指定されている[OnOpen](#onopen)場合、セカンダリの動詞または`OLEIVERB_OPEN`が指定されていると[OnHide](#onhide)場合`OLEIVERB_HIDE`を指定します。 既定の実装`OnShow`場合`iVerb`上に示した動詞のいずれかではありません。  
  
 主動詞がアイテムを表示しない場合は、この関数をオーバーライドします。 たとえば場合は、項目は、サウンドの録音、その主動詞がプレイは、項目を再生するサーバー アプリケーションを表示する必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK に含まれています。  
  
##  <a name="ondraw"></a>  :Ondraw  
 OLE 項目をメタファイルに描画するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)項目を描画するオブジェクト。 ディスプレイ コンテキストは、属性の関数が使えるように、自動的に属性のディスプレイ コンテキストに接続します。  
  
 `rSize`  
 サイズの**HIMETRIC**メタファイルを描画するための単位です。  
  
### <a name="return-value"></a>戻り値  
 項目が正常に描画された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE 項目のメタファイル表現を使用して、コンテナー アプリケーションでアイテムを表示します。 メタファイルはによって使用されている場合は、コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが、[描画](../../mfc/reference/coleclientitem-class.md#draw)の対応するメンバー関数[COleClientItem](../../mfc/reference/coleclientitem-class.md)オブジェクト。 既定の実装はありません。 指定されたデバイス コンテキストに項目を描画するには、この関数をオーバーライドする必要があります。  
  
##  <a name="ondrawex"></a>  COleServerItem::OnDrawEx  
 すべての描画するためのフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)項目を描画するオブジェクト。 DC は、属性の関数が使えるように、自動的に属性の DC に接続します。  
  
 `nDrawAspect`  
 `DVASPECT` 列挙体の値。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- `DVASPECT_CONTENT` 項目は、コンテナー内の埋め込みオブジェクトとして表示されること、このような方法で表されます。  
  
- `DVASPECT_THUMBNAIL` 参照ツールで表示できるように、「サムネイル」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON` 項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT` 項目は、[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように表されます。  
  
 `rSize`  
 内の項目のサイズ**HIMETRIC**単位です。  
  
### <a name="return-value"></a>戻り値  
 項目が正常に描画された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装`OnDraw`とき`DVASPECT`と等しい`DVASPECT_CONTENT`;、それ以外の場合は失敗します。  
  
 以外の側面のプレゼンテーションにデータを提供するには、この関数をオーバーライド`DVASPECT_CONTENT`など`DVASPECT_ICON`または`DVASPECT_THUMBNAIL`です。  
  
##  <a name="ongetclipboarddata"></a>  COleServerItem::OnGetClipboardData  
 取得するためにフレームワークによって呼び出されます、`COleDataSource`オブジェクトを含むすべてのデータへの呼び出しによって、クリップボードに配置されますが、 [CopyToClipboard](#copytoclipboard)メンバー関数。  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIncludeLink`  
 これを設定して**TRUE**場合は、データ リンクをクリップボードにコピーする必要があります。 これを設定して**FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
 `lpOffset`  
 マウス ポインターのピクセル単位でオブジェクトの原点からのオフセット。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クリップボード データを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を呼び出す[GetClipboardData](#getclipboarddata)です。  
  
##  <a name="ongetextent"></a>  COleServerItem::OnGetExtent  
 サイズを取得するためにフレームワークによって呼び出されます**HIMETRIC** OLE 項目の単位。  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 境界を取得する OLE アイテムの縦横比を指定します。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- `DVASPECT_CONTENT` 項目は、コンテナー内の埋め込みオブジェクトとして表示されること、このような方法で表されます。  
  
- `DVASPECT_THUMBNAIL` 参照ツールで表示できるように、「サムネイル」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON` 項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT` 項目は、[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように表されます。  
  
 `rSize`  
 参照、 `CSize` OLE 項目のサイズを受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが、この関数が呼び出されます場合に、 [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent)の対応するメンバー関数`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装では、何も行われません。 必要がありますこれを実装する自分でします。 OLE 項目のサイズの要求を処理するときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="onhide"></a>  COleServerItem::OnHide  
 OLE 項目を非表示にするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>コメント  
 既定の呼び出し**COleServerDoc::OnShowDocument (FALSE)** です。 関数には、OLE アイテムを非表示にされたコンテナーも通知します。 OLE 項目を非表示にするときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="oninitfromdata"></a>  COleServerItem::OnInitFromData  
 内容を使用して OLE 項目を初期化するためにフレームワークによって呼び出されます`pDataObject`です。  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 OLE 項目を初期化するためのさまざまな形式でデータを含む OLE データ オブジェクトへのポインター。  
  
 `bCreation`  
 **TRUE**コンテナー アプリケーションで新しく作成される OLE 項目を初期化するために、関数が呼び出されます。 **FALSE**既に既存の OLE 項目の内容を置き換える、関数が呼び出されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bCreation`は**TRUE**コンテナーには、現在の選択範囲に基づく挿入の新しいオブジェクトが実装されている場合、この関数が呼び出されます。 新しい OLE 項目を作成するときに、選択したデータが使用されます。 たとえば、スプレッドシート プログラムではセルの範囲を選択して、グラフを作成し、新しいオブジェクトの挿入を使用してに基づいている場合、選択した範囲内の値。 既定の実装では、何も行われません。 によって提供されるものと受け付け可能な形式を選択するには、この関数をオーバーライド`pDataObject`し、指定されたデータに基づく OLE 項目を初期化します。 これは、高度なオーバーライド可能です。  
  
 詳細については、次を参照してください。 [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) Windows SDK に含まれています。  
  
##  <a name="onopen"></a>  COleServerItem::OnOpen  
 配置ではなく、サーバー アプリケーションの個別のインスタンスでは、OLE アイテムを表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装を OLE アイテムを含むドキュメントを表示する最初のフレーム ウィンドウをアクティブ化します。アプリケーションがミニ サーバーの場合は、既定の実装は、メイン ウィンドウを表示します。 関数には、OLE アイテムが開かれているコンテナーも通知します。  
  
 OLE 項目を開くときに、特別な処理を実行する場合は、この関数をオーバーライドします。 これは、開かれたときに、リンクを選択範囲を設定するリンクされた項目を含むにおいて特に多く見です。  
  
 詳細については、次を参照してください。 [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658) Windows SDK に含まれています。  
  
##  <a name="onqueryupdateitems"></a>  COleServerItem::OnQueryUpdateItems  
 現在のサーバーのドキュメント内のすべてのリンクされた項目が最新でないかどうかを判断するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメント内の更新の必要なアイテムがある場合は 0 以外。すべての項目が最新の状態の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アイテムは最新では、送信元ドキュメントが変更されましたが、ドキュメント内の変更を反映するようにリンクされた項目が更新されていない場合。  
  
##  <a name="onrenderdata"></a>  COleServerItem::OnRenderData  
 指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが返される構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 以前に指定の形式は、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)または[DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を呼び出す[可変](#onrenderfiledata)または[によって](#onrenderglobaldata)、それぞれ、指定されたストレージ メディアがメモリまたはファイルの場合。 これらの形式のどちらが指定されている場合、既定の実装は 0 を返しますを何も行われません。  
  
 場合`lpStgMedium` ->  *tymed*は**TYMED_NULL**、 **STGMEDIUM**を割り当てる必要があるされで指定された入力*lpFormatEtc ->tymed*です。 ない場合**TYMED_NULL**、 **STGMEDIUM**のデータが配置を入力する必要があります。  
  
 これは、高度なオーバーライド可能です。 要求された形式および中規模でデータを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンの 1 つを上書きする可能性があります。 データが小規模で固定サイズの場合は、オーバーライド`OnRenderGlobalData`です。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`です。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)、および[TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) Windows SDK に含まれています。  
  
##  <a name="onrenderfiledata"></a>  COleServerItem::OnRenderFileData  
 ストレージ メディア ファイルは、ときに、指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `pFile`  
 指す、`CFile`データが表示されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 以前に指定の形式は、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を単純に返します**FALSE**です。  
  
 これは、高度なオーバーライド可能です。 要求された形式および中規模でデータを提供するには、この関数をオーバーライドします。 によっては、データは、代わりにこの関数の他のバージョンの 1 つをオーバーライドすることができます。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データをファイル内や可変サイズのオーバーライド[可変](#onrenderfiledata)です。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="onrenderglobaldata"></a>  COleServerItem::OnRenderGlobalData  
 指定されたストレージ メディアが使用するグローバル メモリに指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `phGlobal`  
 データが返されるグローバル メモリへのハンドルへのポインター。 このパラメーターを指定できるメモリが割り当てられていない場合**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 以前に指定の形式は、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を単純に返します**FALSE**です。  
  
 場合`phGlobal`は**NULL**、し、新しい`HGLOBAL`割り当てられで返される必要があります`phGlobal`です。 それ以外の場合、`HGLOBAL`によって指定された`phGlobal`データを格納する必要があります。 内に配置するデータ量、`HGLOBAL`メモリ ブロックの現在のサイズを超えない必要があります。 また、ブロックは、大きいサイズに再割り当てできません。  
  
 これは、高度なオーバーライド可能です。 要求された形式および中規模でデータを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンの 1 つを上書きする可能性があります。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データをファイル内や可変サイズのオーバーライド[可変](#onrenderfiledata)です。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="onsetcolorscheme"></a>  COleServerItem::OnSetColorScheme  
 OLE 項目を編集するときに使用するカラー パレットを指定するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpLogPalette`  
 Windows へのポインター[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)構造体。  
  
### <a name="return-value"></a>戻り値  
 カラー パレットが使用される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションでは、Microsoft Foundation Class ライブラリを使用して書き込まれますが、この関数が呼び出されます場合に、 [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971)関数の対応する`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装を返します**FALSE**です。 推奨パレットを使用する場合は、この関数をオーバーライドします。 サーバー アプリケーションは、推奨パレットを使用する必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Windows SDK に含まれています。  
  
##  <a name="onsetdata"></a>  COleServerItem::OnSetData  
 データを指定して OLE アイテムのデータを置き換えるために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データの形式を指定します。  
  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが存在する構造体します。  
  
 `bRelease`  
 関数呼び出しを完了した後、記憶域メディアの所有権を持っているユーザーを示します。 呼び出し元は、ストレージ メディア代理で割り当てられたリソースを解放する担当者を決定します。 呼び出し元は設定することで`bRelease`です。 場合`bRelease`は 0 以外の場合、サーバー項目所有権を取得、使用が終了すると、メディアを解放します。 ときに`bRelease`0 は、呼び出し元が所有権を保持およびサーバー項目は、呼び出しの間でのみストレージ メディアを使用できます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 サーバー項目では正常に取得するまで、データの所有権になりません。 その所有権を持ちません場合は 0 を返します。 データ ソースの所有権を呼び出すことによってストレージ メディアを解放、 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)関数。  
  
 既定の実装では、何も行われません。 データを指定して、OLE 項目のデータを置き換えるには、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)、および[ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Windows SDK に含まれています。  
  
##  <a name="onsetextent"></a>  COleServerItem::OnSetExtent  
 OLE アイテムをどの程度空き領域があることをコンテナー ドキュメント内に通知するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 境界が指定されている OLE 項目の縦横比を指定します。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- `DVASPECT_CONTENT` 項目は、コンテナー内の埋め込みオブジェクトとして表示されること、このような方法で表されます。  
  
- `DVASPECT_THUMBNAIL` 参照ツールで表示できるように、「サムネイル」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON` 項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT` 項目は、[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように表されます。  
  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) OLE 項目の新しいサイズを指定する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで書き込まれましたが、この関数が呼び出されます場合に、 [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent)の対応するメンバー関数`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装設定、[です](#m_sizeextent)を指定したサイズのメンバー場合`nDrawAspect`は`DVASPECT_CONTENT`です。 それ以外の場合は 0 を返します。 アイテムのサイズを変更すると、特別な処理を実行するには、この関数をオーバーライドします。  
  
##  <a name="onshow"></a>  COleServerItem::OnShow  
 OLE 項目の場所で表示するサーバー アプリケーションに指示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>コメント  
 表示される項目を必要とするコンテナー アプリケーションのユーザーがアイテムの作成や編集などの動詞を実行時に、この関数は通常呼び出されます。 既定の実装では、インプレース アクティブ化を試行します。 失敗したかどうか、関数呼び出し、 `OnOpen` OLE 項目を別のウィンドウで表示するメンバー関数。  
  
 OLE 項目が表示されると、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
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
 `pSender`  
 ドキュメントを変更する項目へのポインター。 指定できます**NULL**です。  
  
 `lHint`  
 変更に関する情報が含まれています。  
  
 `pHint`  
 変更に関する情報を格納するオブジェクトへのポインター。  
  
 `nDrawAspect`  
 `DVASPECT` 列挙体の値。 このパラメーターは、次の値のいずれかを持つことができます。  
  
- `DVASPECT_CONTENT` 項目は、コンテナー内の埋め込みオブジェクトとして表示されること、このような方法で表されます。  
  
- `DVASPECT_THUMBNAIL` 参照ツールで表示できるように、「サムネイル」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON` 項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT` 項目は、[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように表されます。  
  
### <a name="remarks"></a>コメント  
 既定の実装[NotifyChanged](#notifychanged)ヒントや送信者に関係なく、します。  
  
##  <a name="onupdateitems"></a>  COleServerItem::OnUpdateItems  
 サーバー ドキュメントのすべてのアイテムを更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装[UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)すべて`COleClientItem`ドキュメント内のオブジェクト。  
  
##  <a name="setitemname"></a>  COleServerItem::SetItemName  
 その名前を設定するリンクされた項目を作成するときに、この関数を呼び出します。  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszItemName`  
 項目の新しい名前へのポインター。  
  
### <a name="remarks"></a>コメント  
 名前は、ドキュメント内で一意にする必要があります。 リンクされた項目を編集するのにサーバー アプリケーションが呼び出されると、アプリケーションは、項目を検索するのにこの名前を使用します。 埋め込みアイテムに対してこの関数を呼び出す必要はありません。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CDocItem クラス](../../mfc/reference/cdocitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)

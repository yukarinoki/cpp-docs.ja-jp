---
title: COleClientItem クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
dev_langs:
- C++
helpviewer_keywords:
- COleClientItem [MFC], COleClientItem
- COleClientItem [MFC], Activate
- COleClientItem [MFC], ActivateAs
- COleClientItem [MFC], AttachDataObject
- COleClientItem [MFC], CanCreateFromData
- COleClientItem [MFC], CanCreateLinkFromData
- COleClientItem [MFC], CanPaste
- COleClientItem [MFC], CanPasteLink
- COleClientItem [MFC], Close
- COleClientItem [MFC], ConvertTo
- COleClientItem [MFC], CopyToClipboard
- COleClientItem [MFC], CreateCloneFrom
- COleClientItem [MFC], CreateFromClipboard
- COleClientItem [MFC], CreateFromData
- COleClientItem [MFC], CreateFromFile
- COleClientItem [MFC], CreateLinkFromClipboard
- COleClientItem [MFC], CreateLinkFromData
- COleClientItem [MFC], CreateLinkFromFile
- COleClientItem [MFC], CreateNewItem
- COleClientItem [MFC], CreateStaticFromClipboard
- COleClientItem [MFC], CreateStaticFromData
- COleClientItem [MFC], Deactivate
- COleClientItem [MFC], DeactivateUI
- COleClientItem [MFC], Delete
- COleClientItem [MFC], DoDragDrop
- COleClientItem [MFC], DoVerb
- COleClientItem [MFC], Draw
- COleClientItem [MFC], GetActiveView
- COleClientItem [MFC], GetCachedExtent
- COleClientItem [MFC], GetClassID
- COleClientItem [MFC], GetClipboardData
- COleClientItem [MFC], GetDocument
- COleClientItem [MFC], GetDrawAspect
- COleClientItem [MFC], GetExtent
- COleClientItem [MFC], GetIconFromRegistry
- COleClientItem [MFC], GetIconicMetafile
- COleClientItem [MFC], GetInPlaceWindow
- COleClientItem [MFC], GetItemState
- COleClientItem [MFC], GetLastStatus
- COleClientItem [MFC], GetLinkUpdateOptions
- COleClientItem [MFC], GetType
- COleClientItem [MFC], GetUserType
- COleClientItem [MFC], IsInPlaceActive
- COleClientItem [MFC], IsLinkUpToDate
- COleClientItem [MFC], IsModified
- COleClientItem [MFC], IsOpen
- COleClientItem [MFC], IsRunning
- COleClientItem [MFC], OnActivate
- COleClientItem [MFC], OnActivateUI
- COleClientItem [MFC], OnChange
- COleClientItem [MFC], OnDeactivate
- COleClientItem [MFC], OnDeactivateUI
- COleClientItem [MFC], OnGetClipboardData
- COleClientItem [MFC], OnInsertMenus
- COleClientItem [MFC], OnRemoveMenus
- COleClientItem [MFC], OnSetMenu
- COleClientItem [MFC], OnShowControlBars
- COleClientItem [MFC], OnUpdateFrameTitle
- COleClientItem [MFC], ReactivateAndUndo
- COleClientItem [MFC], Release
- COleClientItem [MFC], Reload
- COleClientItem [MFC], Run
- COleClientItem [MFC], SetDrawAspect
- COleClientItem [MFC], SetExtent
- COleClientItem [MFC], SetHostNames
- COleClientItem [MFC], SetIconicMetafile
- COleClientItem [MFC], SetItemRects
- COleClientItem [MFC], SetLinkUpdateOptions
- COleClientItem [MFC], SetPrintDevice
- COleClientItem [MFC], UpdateLink
- COleClientItem [MFC], CanActivate
- COleClientItem [MFC], OnChangeItemPosition
- COleClientItem [MFC], OnDeactivateAndUndo
- COleClientItem [MFC], OnDiscardUndoState
- COleClientItem [MFC], OnGetClipRect
- COleClientItem [MFC], OnGetItemPosition
- COleClientItem [MFC], OnGetWindowContext
- COleClientItem [MFC], OnScrollBy
- COleClientItem [MFC], OnShowItem
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89a277293cd4b192af0a8a069b82b1b1614490a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378762"
---
# <a name="coleclientitem-class"></a>COleClientItem クラス
OLE アイテムへのコンテナー インターフェイスを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|`COleClientItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|操作が OLE 項目を開き、指定された動詞を実行します。|  
|[COleClientItem::ActivateAs](#activateas)|別の種類として、項目をアクティブにします。|  
|[COleClientItem::AttachDataObject](#attachdataobject)|OLE オブジェクトのデータにアクセスします。|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|コンテナー アプリケーションが、埋め込みオブジェクトを作成できるかどうかを示します。|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|コンテナー アプリケーションが、リンク オブジェクトを作成できるかどうかを示します。|  
|[置き換えるには](#canpaste)|埋め込み可能なまたは静的 OLE 項目が、クリップボードに含まれているかどうかを示します。|  
|[置き換えるには](#canpastelink)|クリップボードにリンク可能な OLE 項目が含まれるかどうかを示します。|  
|[COleClientItem::Close](#close)|サーバーへのリンクを閉じますが、OLE アイテムは破棄しません。|  
|[COleClientItem::ConvertTo](#convertto)|アイテムを別の型に変換します。|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|OLE 項目をクリップボードにコピーします。|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|既存の項目の複製を作成します。|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|クリップボードから埋め込みアイテムを作成します。|  
|[COleClientItem::CreateFromData](#createfromdata)|データ オブジェクトから埋め込みアイテムを作成します。|  
|[COleClientItem::CreateFromFile](#createfromfile)|ファイルから埋め込みアイテムを作成します。|  
|[リンク](#createlinkfromclipboard)|クリップボードからリンクされた項目を作成します。|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|データ オブジェクトからリンクされた項目を作成します。|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|ファイルからリンクされた項目を作成します。|  
|[COleClientItem::CreateNewItem](#createnewitem)|サーバー アプリケーションを起動して新しい埋め込み項目を作成します。|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|クリップボードから、静的な項目を作成します。|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|データ オブジェクトから、静的な項目を作成します。|  
|[COleClientItem::Deactivate](#deactivate)|アイテムを非アクティブ化します。|  
|[COleClientItem::DeactivateUI](#deactivateui)|コンテナー アプリケーションのユーザー インターフェイスは、元の状態に復元します。|  
|[COleClientItem::Delete](#delete)|削除するか、またはリンクされた項目があった場合は、OLE 項目を閉じます。|  
|[クラス](#dodragdrop)|ドラッグ アンド ドロップ操作を実行します。|  
|[COleClientItem::DoVerb](#doverb)|指定された動詞を実行します。|  
|[値](#draw)|OLE 項目を描画します。|  
|[COleClientItem::GetActiveView](#getactiveview)|場所にいるアイテムがアクティブ化されたビューを取得します。|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|OLE アイテムの四角形の境界を返します。|  
|[COleClientItem::GetClassID](#getclassid)|現在のアイテムのクラス ID を取得します|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|クリップボードに呼び出すことによって、データの取得、`CopyToClipboard`メンバー関数。|  
|[COleClientItem::GetDocument](#getdocument)|返します、`COleDocument`を現在のアイテムを含むオブジェクト。|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|表示するためには、アイテムの現在のビューを取得します。|  
|[COleClientItem::GetExtent](#getextent)|OLE アイテムの四角形の境界を返します。|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|特定の CLSID のサーバーに関連付けられているアイコンへのハンドルを取得します。|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|項目のアイコンを描画するために使われるメタファイルを取得します。|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|項目の一括編集ウィンドウへのポインターを返します。|  
|[COleClientItem::GetItemState](#getitemstate)|アイテムの現在の状態を取得します。|  
|[COleClientItem::GetLastStatus](#getlaststatus)|最後の OLE 操作の状態を返します。|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|リンクされた項目 (高度な機能) の更新モードを返します。|  
|[COleClientItem::GetType](#gettype)|OLE 項目の種類 (埋め込み、リンク、または静的) を返します。|  
|[COleClientItem::GetUserType](#getusertype)|項目の種類を説明する文字列を取得します。|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|返します`TRUE`アイテムが、インプレース アクティブである場合。|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|返します**TRUE**リンクされた項目がソース ドキュメント内で最新の状態の場合。|  
|[COleClientItem::IsModified](#ismodified)|返します`TRUE`最後に保存してから、項目が変更された場合。|  
|[COleClientItem::IsOpen](#isopen)|返します`TRUE`項目がサーバー アプリケーションで現在開いている場合。|  
|[COleClientItem::IsRunning](#isrunning)|返します`TRUE`項目のサーバー アプリケーションが実行されている場合。|  
|[COleClientItem::OnActivate](#onactivate)|アクティブ化されるアイテムを通知するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnActivateUI](#onactivateui)|アクティブになり、そのユーザー インターフェイスを表示する必要がありますが、アイテムを通知するためにフレームワークによって呼び出されます。|  
|[として](#onchange)|サーバーに OLE 項目が変更されたときに呼び出されます。 必要な実装です。|  
|[COleClientItem::OnDeactivate](#ondeactivate)|項目が非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|サーバーが、インプレースでのユーザー インターフェイスを削除すると、フレームワークによって呼び出されます。|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|クリップボードにコピーするデータを取得するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|コンポジット メニューを作成するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|コンポジット メニューから、コンテナーのメニューを削除するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnSetMenu](#onsetmenu)|インストールおよびコンポジット メニューを削除するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|コントロール バーを非表示にしたりするためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|フレーム ウィンドウのタイトル バーを更新するためにフレームワークによって呼び出されます。|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|アイテムを再アクティブ化し、最後のインプレース編集操作を元に戻します。|  
|[COleClientItem::Release](#release)|OLE 項目にリンクへの接続を解放しが開いていた場合に終了します。 クライアント アイテムは破棄されません。|  
|[COleClientItem::Reload](#reload)|呼び出しの後に、項目を再読み込み`ActivateAs`です。|  
|[COleClientItem::Run](#run)|アイテムに関連付けられているアプリケーションを実行します。|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|表示するため、項目の現在のビューを設定します。|  
|[COleClientItem::SetExtent](#setextent)|OLE 項目の外接する四角形を設定します。|  
|[COleClientItem::SetHostNames](#sethostnames)|OLE 項目を編集するときに、サーバーが表示名を設定します。|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|項目のアイコンを描画するために使われるメタファイルをキャッシュします。|  
|[COleClientItem::SetItemRects](#setitemrects)|項目の外接する四角形を設定します。|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|リンクされた項目 (高度な機能) の更新モードを設定します。|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|クライアントは、この項目の出力先のデバイスを設定します。|  
|[COleClientItem::UpdateLink](#updatelink)|項目のプレゼンテーション キャッシュを更新します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleClientItem::CanActivate](#canactivate)|インプレース アクティブ化が許可されているかどうかを判断するためにフレームワークによって呼び出されます。|  
|[に](#onchangeitemposition)|アイテムの位置が変更されたときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|アクティブ化の後に元に戻すために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|項目の元に戻す状態情報を破棄するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|アイテムのクリッピング四角形の座標を取得するためにフレームワークによって呼び出されます。|  
|[状態](#ongetitemposition)|ビューに対する相対的なアイテムの位置を取得するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|場所に項目がアクティブになったときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnScrollBy](#onscrollby)|項目をスクロールして表示するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnShowItem](#onshowitem)|OLE 項目を表示するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 OLE 項目では、作成および「シームレスに」に組み込むできるドキュメントを 1 つのドキュメントであることをユーザーに表示されないように、サーバーのアプリケーションによって管理される、データを表します。 結果は、「複合ドキュメント」OLE アイテムとを含むドキュメントから成ります。  
  
 OLE 項目は、いずれか埋め込みまたはリンクされています。 埋め込まれている場合、そのデータは、複合ドキュメントの一部として格納されます。 リンクされている場合は、別のサーバー アプリケーションによって作成されたファイルの一部として、データが保存され、複合ドキュメントにそのファイルへのリンクのみが格納されています。 すべての OLE 項目には、それらを編集するために呼び出す必要がありますサーバー アプリケーションを指定する情報が含まれます。  
  
 `COleClientItem` サーバー アプリケーションからの要求に対する応答と呼ばれるいくつかのオーバーライド可能な関数を定義しますこれらのオーバーライド可能な関数は、通常、通知として機能します。 これにより、サーバー アプリケーションは OLE 項目を編集するときに、ユーザーが行った変更のコンテナーに通知する、または編集するときに必要な情報を取得します。  
  
 `COleClientItem` いずれかで使用できる、 [COleDocument](../../mfc/reference/coledocument-class.md)、[直接](../../mfc/reference/colelinkingdoc-class.md)、または[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)クラスです。 使用する`COleClientItem`、クラスの派生、および実装、 [OnChange](#onchange)メンバー関数は、コンテナーが、項目に加えられた変更に応答する方法を定義します。 インプレース アクティブ化をサポートするためにオーバーライド、 [:ongetitemposition](#ongetitemposition)メンバー関数。 この関数は、OLE アイテムの表示位置に関する情報を提供します。  
  
 詳細については、コンテナー インターフェイスを使用して、記事を参照してください。[コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md)と[アクティブ化](../../mfc/activation-cpp.md)です。  
  
> [!NOTE]
>  Windows SDK は、「オブジェクト」として埋め込みまたはリンクされた項目を参照し、「クラス」と項目の種類を参照 このリファレンスでは、"item"という用語を使用して、対応する C++ オブジェクトと、C++ クラスと OLE カテゴリを区別するには、"type"という用語と OLE のエンティティを区別します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="activate"></a>  COleClientItem::Activate  
 代わりに指定された動詞を実行するには、この関数を呼び出す[DoVerb](#doverb)例外がスローされたときに、独自の処理を実行できるようにします。  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nVerb`  
 実行する動詞を指定します。 次のいずれかを指定できます。  
  
|[値]|説明|シンボル|  
|-----------|-------------|------------|  
|- 0|主動詞|`OLEIVERB_PRIMARY`|  
|- 1|セカンダリの動詞|(なし)|  
|- 1|編集するための表示項目|`OLEIVERB_SHOW`|  
|- 2|別のウィンドウで項目を編集します。|`OLEIVERB_OPEN`|  
|- 3|アイテムを非表示します。|`OLEIVERB_HIDE`|  
  
 -1 の値は、通常、他の動詞のエイリアスです。 開いている編集はサポートされていない、-2 は-1 と同じ効果がします。 追加の値を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK に含まれています。  
  
 `pView`  
 OLE アイテムを含むコンテナーの表示ウィンドウへのポインターこの操作は、インプレース アクティブ化のサーバー アプリケーションが使用されます。 このパラメーターを指定する必要があります**NULL**コンテナーは、インプレース アクティブ化をサポートしていない場合。  
  
 `lpMsg`  
 アクティブ化する項目を原因となったメッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数は、サーバー アプリケーションでは、Microsoft Foundation Class ライブラリを使用して書き込まれますが場合、 [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb)の対応するメンバー関数`COleServerItem`を実行するオブジェクト。  
  
 主動詞し、で 0 が指定されているかどうか、 `nVerb` OLE 項目を編集することを許可するパラメーター、サーバー アプリケーションを起動します。 コンテナー アプリケーションでは、インプレース アクティブ化をサポートする場合は、インプレース編集を実行できます。 コンテナーは、インプレース アクティブ化 (または Open 動詞を指定するかどうか) をサポートしていない場合、は、別のウィンドウで、サーバーが起動され、編集し、あることができます。 通常、コンテナー アプリケーションのユーザーをダブルクリック OLE アイテム、プライマリの動詞には、値、`nVerb`パラメーターは、ユーザーが実行するアクションを決定します。 ただし、サーバーは、1 つだけのアクションをサポートする場合は、その操作で指定された値に関係なく、`nVerb`パラメーター。  
  
 詳細については、次を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK に含まれています。  
  
##  <a name="activateas"></a>  COleClientItem::ActivateAs  
 OLE のオブジェクトの変換機能を使用して、あたかも項目で指定された型の項目をアクティブに`clsidNew`です。  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszUserType*  
 「Word 文書」など、ターゲット ユーザーの種類を表す文字列へのポインター  
  
 *clsidOld*  
 アイテムの現在のクラスへの参照の id。 クラス ID にリンクがある場合を除きは、格納されている実際のオブジェクトの種類を表す必要があります。 その場合は、リンクを参照する項目の CLSID になります。 [メンバー](../../mfc/reference/coleconvertdialog-class.md)正しいクラスの ID を項目を自動的に提供します。  
  
 `clsidNew`  
 対象のクラス ID への参照  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、によって自動的と呼ばれる[COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert)です。 これは通常呼び出されません直接。  
  
##  <a name="attachdataobject"></a>  COleClientItem::AttachDataObject  
 初期化するためには、この関数を呼び出して、 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 項目内のデータにアクセスするためです。  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *rDataObject*  
 参照、 `COleDataObject` OLE 項目のデータへのアクセスを許可する初期化されるオブジェクト。  
  
##  <a name="canactivate"></a>  COleClientItem::CanActivate  
 ユーザーが OLE 項目のインプレース アクティブ化を要求するときに、フレームワークによって呼び出されますこの関数の戻り値は、インプレース アクティブ化が許可されているかどうかを判断します。  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>戻り値  
 インプレース アクティブ化が使用できる場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、コンテナーには、有効なウィンドウが含まれて、インプレース アクティブ化が許可されます。 受け入れるか、またはアクティブ化要求を拒否していますの特別なロジックを実装するには、この関数をオーバーライドします。 たとえば、OLE 項目が小さすぎるか、現在表示されていない場合は、ライセンス認証要求を拒否する可能性がします。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236) Windows SDK に含まれています。  
  
##  <a name="cancreatefromdata"></a>  COleClientItem::CanCreateFromData  
 コンテナー アプリケーションの埋め込みオブジェクトを作成できるかどうかを調べます、指定された`COleDataObject`オブジェクト。  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)元となる OLE 項目を作成するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 コンテナーがから埋め込みオブジェクトを作成できる場合は 0 以外、`COleDataObject`オブジェクト以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 `COleDataObject`クラスがドラッグ アンド ドロップをクリップボードや OLE 埋め込みアイテムからさまざまな形式でデータを取得するデータ転送に使用します。  
  
 コンテナーは、有効にするにまたは、貼り付けの編集および編集貼り付けコマンドを無効にするのにことをこの関数を使用できます。  
  
 詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)です。  
  
##  <a name="cancreatelinkfromdata"></a>  COleClientItem::CanCreateLinkFromData  
 コンテナー アプリケーションからのリンク オブジェクトを作成できるかどうかを調べます、指定された`COleDataObject`オブジェクト。  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)元となる OLE 項目を作成するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 コンテナーからのリンク オブジェクトを作成できる場合は 0 以外、`COleDataObject`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `COleDataObject`クラスがドラッグ アンド ドロップをクリップボードや OLE 埋め込みアイテムからさまざまな形式でデータを取得するデータ転送に使用します。  
  
 コンテナーは、有効または無効にそれを編集して貼り付け、編集リンク貼り付けコマンドを決定するのに、この関数を使用できます。  
  
 詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)です。  
  
##  <a name="canpaste"></a>  置き換えるには  
 この関数では、OLE 埋め込みアイテムをクリップボードから貼り付けできるかどうかを参照してください。  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>戻り値  
 OLE 埋め込みアイテムをクリップボードから貼り付けできる場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778)と[OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739) Windows SDK に含まれています。  
  
##  <a name="canpastelink"></a>  置き換えるには  
 この関数では、リンクされた OLE 項目をクリップボードから貼り付けできるかどうかを参照してください。  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>戻り値  
 リンクされた OLE 項目をクリップボードから貼り付けできる場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778)と[OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244) Windows SDK に含まれています。  
  
##  <a name="close"></a>  COleClientItem::Close  
 メモリ内には、そのハンドラーが実行されていないサーバーをロードは、読み込まれた状態に実行中の状態から OLE 項目の状態を変更するには、この関数を呼び出します。  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCloseOption`  
 読み込み済み状態に戻ったときに、OLE 項目を保存どのような状況を指定するフラグを設定します。 次の値のいずれかを取ります。  
  
- `OLECLOSE_SAVEIFDIRTY` OLE 項目を保存します。  
  
- `OLECLOSE_NOSAVE` OLE 項目を保存できません。  
  
- `OLECLOSE_PROMPTSAVE` OLE 項目を保存するかどうかをユーザーに問い合わせます。  
  
### <a name="remarks"></a>コメント  
 OLE 項目が実行されていない場合は、この関数を指定しても効果はありません。  
  
 詳細については、次を参照してください。 [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) Windows SDK に含まれています。  
  
##  <a name="coleclientitem"></a>  COleClientItem::COleClientItem  
 構築、`COleClientItem`オブジェクトを C++ オブジェクトのみを構築し、OLE の初期化は行われませんが、ドキュメント アイテムのコンテナー ドキュメントのコレクションに追加します。  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pContainerDoc`  
 この項目を格納するコンテナーのドキュメントへのポインター。 [COleDocument](../../mfc/reference/coledocument-class.md)から派生します。  
  
### <a name="remarks"></a>コメント  
 渡す場合、 **NULL**ポインター、追加は行われません、コンテナー ドキュメントにします。 明示的に呼び出す必要があります[COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)です。  
  
 OLE 項目を使用する前に、次の作成のメンバー関数のいずれかを呼び出す必要があります。  
  
- [一般的に](#createfromclipboard)  
  
- [CreateFromData](#createfromdata)  
  
- [CreateFromFile](#createfromfile)  
  
- [関数](#createstaticfromclipboard)  
  
- [CreateStaticFromData](#createstaticfromdata)  
  
- [CreateLinkFromClipboard](#createlinkfromclipboard)  
  
- [CreateLinkFromData](#createlinkfromdata)  
  
- [CreateLinkFromFile](#createlinkfromfile)  
  
- [CreateNewItem](#createnewitem)  
  
- [CreateCloneFrom](#createclonefrom)  
  
##  <a name="convertto"></a>  COleClientItem::ConvertTo  
 このメンバー関数で指定された型に変換して`clsidNew`です。  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsidNew`  
 対象の型のクラス ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、によって自動的と呼ばれる[メンバー](../../mfc/reference/coleconvertdialog-class.md)です。 メソッドを直接呼び出す必要はありません。  
  
##  <a name="copytoclipboard"></a>  COleClientItem::CopyToClipboard  
 OLE 項目をクリップボードにコピーするには、この関数を呼び出します。  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIncludeLink`  
 **TRUE**リンクについては、クリップボードにコピーするか場合、は、それ以外の貼り付けられたにリンクされた項目を許可する**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 通常、[編集] メニューから切り取りまたはコピー コマンドのメッセージ ハンドラーを記述する場合、この関数を呼び出します。 コピーまたは切り取りコマンドを実装する場合は、コンテナー アプリケーションで項目の選択を実装する必要があります。  
  
 詳細については、次を参照してください。 [OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623) Windows SDK に含まれています。  
  
##  <a name="createclonefrom"></a>  COleClientItem::CreateCloneFrom  
 指定した OLE 項目のコピーを作成するには、この関数を呼び出します。  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSrcItem*  
 重複する OLE アイテムへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コピーは、元の項目と同じです。 この関数は、元に戻す操作をサポートするために使用することができます。  
  
##  <a name="createfromclipboard"></a>  COleClientItem::CreateFromClipboard  
 クリップボードの内容から埋め込みアイテムを作成するには、この関数を呼び出します。  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常の編集 メニューの 貼り付け コマンドからメッセージ ハンドラーは、この関数を呼び出します。 (場合に、フレームワークによって [貼り付け] コマンドが有効になって、 [CanPaste](#canpaste)メンバー関数は 0 以外を返します)。  
  
 詳細については、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createfromdata"></a>  COleClientItem::CreateFromData  
 埋め込みアイテムを作成するには、この関数を呼び出して、`COleDataObject`オブジェクト。  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)元となる OLE 項目を作成するオブジェクト。  
  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 データ転送操作で、クリップボード操作やドラッグ アンド ドロップ操作からの貼り付けなどの提供`COleDataObject`サーバー アプリケーションによって提供される情報を含むオブジェクトします。 通常は、オーバーライド、使用[この関数](../../mfc/reference/cview-class.md#ondrop)です。  
  
 詳細については、次を参照してください。 [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createfromfile"></a>  COleClientItem::CreateFromFile  
 ファイルから埋め込み OLE アイテムを作成するには、この関数を呼び出します。  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 OLE 項目の作成元のファイルの名前へのポインター。  
  
 `clsid`  
 将来使用するために予約されています。  
  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークからこの関数を呼び出します[クリック](../../mfc/reference/coleinsertdialog-class.md#createitem)場合は、ファイルから作成 を選択すると、ユーザーがオブジェクトの挿入 ダイアログ ボックスから [ok] を選択します。  
  
 詳細については、次を参照してください。 [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createlinkfromclipboard"></a>  リンク  
 クリップボードの内容からリンクされた項目を作成するには、この関数を呼び出します。  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常の編集] メニューの [リンク貼り付けコマンド メッセージ ハンドラーからこの関数を呼び出します。 (既定の実装でリンク貼り付け コマンドが有効になっている[COleDocument](../../mfc/reference/coledocument-class.md) OLE 項目にリンクできますが、クリップボードに含まれている場合)。  
  
 詳細については、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createlinkfromdata"></a>  COleClientItem::CreateLinkFromData  
 リンクされた項目を作成するには、この関数を呼び出して、`COleDataObject`オブジェクト。  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)元となる OLE 項目を作成するオブジェクト。  
  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出しがこのユーザーには、リンクが示されている場合は、ドロップ操作中に作成する必要があります。 貼り付けコマンドを処理するも使用できます。 メソッドにフレームワークによって呼び出されます`COleClientItem::CreateLinkFromClipboard`し、[静的オブジェクト](../../mfc/reference/colepastespecialdialog-class.md#createitem)リンク オプションが選択されたときにします。  
  
 詳細については、次を参照してください。 [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createlinkfromfile"></a>  COleClientItem::CreateLinkFromFile  
 この関数では、ファイルからリンクされている OLE 項目を作成します。  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 OLE 項目の作成元のファイルの名前へのポインター。  
  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ファイルから作成 が選択されているし、リンク チェック ボックスをオンになって、ユーザーがオブジェクトの挿入 ダイアログ ボックスから ok を選択すると、この関数を呼び出します。 呼び出された[クリック](../../mfc/reference/coleinsertdialog-class.md#createitem)です。  
  
 詳細については、次を参照してください。 [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createnewitem"></a>  COleClientItem::CreateNewItem  
 埋め込みアイテム; を作成するには、この関数を呼び出すこの関数は、ユーザーが OLE 項目を作成できるサーバー アプリケーションを起動します。  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 作成する OLE 項目の種類を一意に識別する ID です。  
  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、新規作成 ボタンを選択すると、ユーザーがオブジェクトの挿入 ダイアログ ボックスから ok を選択する場合、この関数を呼び出します。  
  
 詳細については、次を参照してください。 [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createstaticfromclipboard"></a>  COleClientItem::CreateStaticFromClipboard  
 クリップボードの内容から、静的な項目を作成するには、この関数を呼び出します。  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 静的項目には、プレゼンテーション データがネイティブのデータではなく; が含まれています。そのため編集できません。 通常この関数を呼び出す場合、[一般的に](#createfromclipboard)メンバー関数は失敗します。  
  
 詳細については、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="createstaticfromdata"></a>  COleClientItem::CreateStaticFromData  
 静的な項目を作成するには、この関数を呼び出して、`COleDataObject`オブジェクト。  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)元となる OLE 項目を作成するオブジェクト。  
  
 *レンダリング*  
 サーバーが OLE 項目を表示する方法を指定するフラグ。 可能な値は、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK に含まれています。  
  
 `cfFormat`  
 OLE 項目を作成するときにキャッシュされるように、クリップボードのデータ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**です。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 静的項目には、プレゼンテーション データがネイティブのデータではなく; が含まれています。そのため、編集できません。 これは、基本的に同じ[関数](#createstaticfromclipboard)任意から静的な項目を作成できる点を除いて`COleDataObject`クリップボードからだけでなく、します。  
  
 使用される[静的オブジェクト](../../mfc/reference/colepastespecialdialog-class.md#createitem)静的が選択されている場合。  
  
 詳細については、次を参照してください。 [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
##  <a name="deactivate"></a>  COleClientItem::Deactivate  
 OLE 項目を非アクティブ化し、関連付けられているリソースを解放するには、この関数を呼び出します。  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>コメント  
 通常非アクティブ化する、インプレース アクティブ OLE 項目、ユーザーがアイテムの境界外のクライアント領域上にマウス ポインターをクリックします。 OLE 項目を非アクティブ化を呼び出すことができない、元に戻す状態は破棄ことに注意してください、[ので](#reactivateandundo)メンバー関数。  
  
 アプリケーションでは、元に戻すをサポートする場合を呼び出さないで`Deactivate`。 代わりに、呼び出す[DeactivateUI](#deactivateui)です。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) Windows SDK に含まれています。  
  
##  <a name="deactivateui"></a>  COleClientItem::DeactivateUI  
 ユーザーには、インプレース アクティブになったアイテムが非アクティブ化時に、この関数を呼び出します。  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスをメニューや、インプレース アクティブ化用に作成されたその他のコントロールを非表示にする、元の状態に復元します。  
  
 この関数は、項目の状態情報を元に戻すにはフラッシュしません。 情報が保存されているように[ので](#reactivateandundo)アイテムを非アクティブ化の直後に、コンテナーの元に戻すコマンドを選択した場合に後で、サーバー アプリケーションで元に戻すコマンドを実行するに使用できます。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) Windows SDK に含まれています。  
  
##  <a name="delete"></a>  COleClientItem::Delete  
 コンテナー ドキュメントから OLE 項目を削除するには、この関数を呼び出します。  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutoDelete`  
 アイテムをドキュメントから削除するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出して、[リリース](#release)メンバー関数は、さらに、項目、永続的に項目を削除する OLE ドキュメントからの C++ オブジェクトを削除します。 OLE 項目が埋め込まれている場合、項目のネイティブのデータは削除されます。 実行中のサーバーが常に閉じられますそのため、項目が開いているリンクの場合は、それを閉じます。  
  
##  <a name="dodragdrop"></a>  クラス  
 呼び出す、`DoDragDrop`メンバー関数をドラッグ アンド ドロップ操作を実行します。  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpItemRect`  
 クライアント座標 (ピクセル単位) で画面上のアイテムの四角形。  
  
 `ptOffset`  
 オフセット`lpItemRect`時のドラッグが、マウスの位置であります。  
  
 `bIncludeLink`  
 これを設定して**TRUE**場合は、リンクのデータをクリップボードにコピーする必要があります。 設定**FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
 `dwEffects`  
 ドラッグ操作で、ドラッグ ソースを使用できる効果を指定します。  
  
 `lpRectStartDrag`  
 実際には、ドラッグの開始位置を定義する四角形を指すポインター。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 `DROPEFFECT` 値。 場合は`DROPEFFECT_MOVE`、元のデータを削除する必要があります。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作がすぐに開始しません。 によって指定される四角形をマウス カーソルが離れるまで待機して`lpRectStartDrag`または指定したミリ秒数が経過するまでです。 場合`lpRectStartDrag`は**NULL**、四角形のサイズは 1 ピクセルです。  
  
 遅延時間は、レジストリ キー設定によって指定されます。 遅延時間を変更するには呼び出すことによって[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)です。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグの遅延時間は、次のように格納されます。  
  
-   Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。  
  
-   Windows 3.x ドラッグ遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクションです。  
  
-   Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI です。  
  
 遅延の情報は、レジストリに格納されている方法の詳細についてドラッグのまたはします。INI ファイルを参照してください[WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows SDK に含まれています。  
  
##  <a name="doverb"></a>  COleClientItem::DoVerb  
 呼び出す`DoVerb`を指定した動詞を実行します。  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nVerb`  
 実行する動詞を指定します。 これは、次のいずれかを含めることができます。  
  
|[値]|説明|シンボル|  
|-----------|-------------|------------|  
|- 0|主動詞|`OLEIVERB_PRIMARY`|  
|- 1|セカンダリの動詞|(なし)|  
|- 1|編集するための表示項目|`OLEIVERB_SHOW`|  
|- 2|別のウィンドウで項目を編集します。|`OLEIVERB_OPEN`|  
|- 3|アイテムを非表示します。|`OLEIVERB_HIDE`|  
  
 -1 の値は、通常、他の動詞のエイリアスです。 開いている編集はサポートされていない、-2 は-1 と同じ効果がします。 追加の値を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK に含まれています。  
  
 `pView`  
 表示ウィンドウへのポインターインプレースでライセンス認証のため、サーバーによって使用されます。 このパラメーターを指定する必要があります**NULL**コンテナー アプリケーションは、インプレース アクティブ化を許可していない場合。  
  
 `lpMsg`  
 アクティブ化する項目を原因となったメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 動詞が正常に実行される; 場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出して、 [Activate](#activate)動詞を実行するメンバー関数。 また、例外をキャッチし、いずれかがスローされた場合、ユーザーにメッセージ ボックスを表示します。  
  
 主動詞し、で 0 が指定されているかどうか、 `nVerb` OLE 項目を編集することを許可するパラメーター、サーバー アプリケーションを起動します。 コンテナー アプリケーションでは、インプレース アクティブ化をサポートする場合は、インプレース編集を実行できます。 コンテナーは、インプレース アクティブ化 (または Open 動詞を指定するかどうか) をサポートしていない場合、は、別のウィンドウで、サーバーが起動され、編集し、あることができます。 通常、コンテナー アプリケーションのユーザーをダブルクリック OLE アイテム、プライマリの動詞には、値、`nVerb`パラメーターは、ユーザーが実行するアクションを決定します。 ただし、サーバーは、1 つだけのアクションをサポートする場合は、その操作で指定された値に関係なく、`nVerb`パラメーター。  
  
##  <a name="draw"></a>  値  
 指定したデバイス コンテキストを使用して、指定された外接する四角形に OLE 項目を描画するには、この関数を呼び出します。  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md) OLE 項目を描画するために使用されるオブジェクト。  
  
 `lpBounds`  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは`RECT`(論理単位で、デバイス コンテキストによって決まります)、OLE 項目を描画するための外接する四角形を定義する構造体。  
  
 `nDrawAspect`  
 OLE の縦横比項目は、表示方法を指定します。 場合`nDrawAspect`-1 で、設定を使用して最後の縦横比[外観](#setdrawaspect)を使用します。 このフラグの使用可能な値の詳細については、次を参照してください。[外観](#setdrawaspect)です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数は、によって作成された OLE 項目のメタファイル表現を使用して可能性があります、 [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw)のメンバー関数`COleServerItem`です。  
  
 通常使用**描画**画面表示のコンテキストを渡すこと、画面デバイスとして`pDC`です。 この場合、最初の 2 つのパラメーターのみを指定する必要があります。  
  
 `lpBounds`パラメーターは、ターゲット デバイス コンテキスト (現在のマップ モード) の四角形を識別します。 レンダリングでは、画像を拡大/縮小する必要があり、表示されているビューと最終的な印刷されたイメージの拡大縮小表示を強制するコンテナー アプリケーションで使用できます。  
  
 詳細については、次を参照してください。 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) Windows SDK に含まれています。  
  
##  <a name="getactiveview"></a>  COleClientItem::GetActiveView  
 項目が、インプレース アクティブ化されているビューを返します。  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビューへのポインターそれ以外の場合**NULL**場合は、アイテムは、インプレース アクティブ化ではありません。  
  
##  <a name="getcachedextent"></a>  COleClientItem::GetCachedExtent  
 OLE 項目のサイズを取得するには、この関数を呼び出します。  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 ポインター、**サイズ**構造体、または[CSize](../../atl-mfc-shared/reference/csize-class.md)サイズの情報を受け取るオブジェクト。  
  
 `nDrawAspect`  
 境界を取得する OLE アイテムの縦横比を指定します。 使用可能な値は、次を参照してください。[外観](#setdrawaspect)です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。OLE 項目が空白の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数と同じ情報を提供する[GetExtent](#getextent)です。 ただし、呼び出す`GetCachedExtent`エクステントの情報を取得、処理中に他の OLE ハンドラーなど[OnChange](#onchange)です。 ディメンションが、`MM_HIMETRIC`単位です。  
  
 これは、考えられるため`GetCachedExtent`を使用して、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)を使用するのではなく、インターフェイス、 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709)この項目の範囲を取得するインターフェイスです。 **IViewObject2** COM オブジェクトが前の呼び出しで使用されているエクステントの情報をキャッシュ[IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)です。  
  
 詳細については、次を参照してください。 [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) Windows SDK に含まれています。  
  
##  <a name="getclassid"></a>  COleClientItem::GetClassID  
 指すメモリに、アイテムのクラス ID を返します`pClassID`です。  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pClassID`  
 型の識別子へのポインター [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424)クラス ID を取得するには 詳細について**CLSID**、Windows SDK を参照してください。  
  
### <a name="remarks"></a>コメント  
 クラス ID は、項目を編集するアプリケーションを一意に識別する 128 ビットの数値です。  
  
 詳細については、次を参照してください。 [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK に含まれています。  
  
##  <a name="getclipboarddata"></a>  COleClientItem::GetClipboardData  
 取得するには、この関数を呼び出す、`COleDataSource`オブジェクトを含むすべてのデータへの呼び出しによって、クリップボードに配置されますが、 [CopyToClipboard](#copytoclipboard)メンバー関数。  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataSource`  
 ポインター、 [COleDataSource](../../mfc/reference/coledatasource-class.md) OLE アイテムに含まれるデータを受け取るオブジェクト。  
  
 `bIncludeLink`  
 **TRUE**リンク データが含まれます。 それ以外の場合にする必要があります場合**FALSE**です。  
  
 `lpOffset`  
 マウス ポインターのピクセル単位でオブジェクトの原点からのオフセット。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="remarks"></a>コメント  
 `GetClipboardData` 既定の実装として呼び出される[OnGetClipboardData](#ongetclipboarddata)です。 オーバーライド`OnGetClipboardData`により提供されるだけでなく、データ形式を提供する場合にのみ`CopyToClipboard`です。 それらの形式での配置、`COleDataSource`オブジェクト呼び出しの前後に`CopyToClipboard`、しに渡す、`COleDataSource`オブジェクトを[COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard)関数。 たとえば、OLE 項目の位置にクリップボードに添えるコンテナー ドキュメントの場合はその情報を渡すための独自の形式を定義してそれを配置、`COleDataSource`呼び出す前に`CopyToClipboard`です。  
  
##  <a name="getdocument"></a>  COleClientItem::GetDocument  
 OLE 項目を含むドキュメントへのポインターを取得するには、この関数を呼び出します。  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目を含むドキュメントへのポインター。 **NULL**場合は、項目は、ドキュメントの一部ではありません。  
  
### <a name="remarks"></a>コメント  
 このポインターへのアクセスを許可する、`COleDocument`への引数として渡されるオブジェクト、`COleClientItem`コンス トラクターです。  
  
##  <a name="getdrawaspect"></a>  COleClientItem::GetDrawAspect  
 呼び出す、`GetDrawAspect`を現在の「側面」または項目のビューを調べます。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 値、`DVASPECT`列挙型、値を持つがのリファレンスに一覧されて[外観](#setdrawaspect)です。  
  
### <a name="remarks"></a>コメント  
 縦横比は、アイテムがレンダリングされる方法を指定します。  
  
##  <a name="getextent"></a>  COleClientItem::GetExtent  
 OLE 項目のサイズを取得するには、この関数を呼び出します。  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 ポインター、**サイズ**構造体、または`CSize`サイズの情報を受け取るオブジェクト。  
  
 `nDrawAspect`  
 境界を取得する OLE アイテムの縦横比を指定します。 使用可能な値は、次を参照してください。[外観](#setdrawaspect)です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。OLE 項目が空白の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、サーバー アプリケーションでは、Microsoft Foundation Class ライブラリを使用して書き込まれますが場合、 [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)の対応するメンバー関数`COleServerItem`に呼び出されるオブジェクト。 最後に設定されているサイズから取得したサイズが異なる場合があることに注意してください、 [SetExtent](#setextent)メンバー関数は; で指定されたサイズ`SetExtent`修正案として扱われます。 ディメンションが、`MM_HIMETRIC`単位です。  
  
> [!NOTE]
>  呼び出す必要はありません`GetExtent`OLE ハンドラーの処理中になど[OnChange](#onchange)です。 呼び出す[GetCachedExtent](#getcachedextent)代わりにします。  
  
 詳細については、次を参照してください。 [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) Windows SDK に含まれています。  
  
##  <a name="geticonfromregistry"></a>  COleClientItem::GetIconFromRegistry  
 特定の CLSID のサーバーに関連付けられているアイコン リソースへのハンドルを取得するには、このメンバー関数を呼び出します。  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 アイコンに関連付けられているサーバーの CLSID への参照。  
  
### <a name="return-value"></a>戻り値  
 有効なリソースへのハンドル、アイコン、または**NULL**サーバーのアイコン、または既定のアイコンが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、サーバーを起動したり、サーバーが既に実行されている場合でも、アイコンを動的に取得。 代わりに、このメンバー関数は、サーバーの実行可能イメージを表示しが登録されているとおりに、サーバーに関連付けられた、静的なアイコンを取得します。  
  
##  <a name="geticonicmetafile"></a>  COleClientItem::GetIconicMetafile  
 項目のアイコンを描画するために使われるメタファイルを取得します。  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、メタファイルへのハンドルそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 現在のアイコンがない場合、既定のアイコンが返されます。 これは、MFC/OLE ダイアログによって自動的に呼び出され、通常直接呼び出されることです。  
  
 この関数を呼び出しても[SetIconicMetafile](#seticonicmetafile)を後で使用するのメタファイルをキャッシュします。  
  
##  <a name="getinplacewindow"></a>  COleClientItem::GetInPlaceWindow  
 呼び出す、`GetInPlaceWindow`で埋め込み先編集のアイテムが開かれているウィンドウへのポインターを取得するメンバー関数。  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>戻り値  
 項目の一括編集ウィンドウへのポインター**NULL**アイテムがアクティブでない場合、またはそのサーバーが利用できない場合。  
  
### <a name="remarks"></a>コメント  
 この関数は、インプレース アクティブである項目に対してのみ呼び出す必要があります。  
  
##  <a name="getitemstate"></a>  COleClientItem::GetItemState  
 OLE 項目の現在の状態を取得するには、この関数を呼び出します。  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COleClientItem::ItemState**列挙値で、次のいずれかになります: `emptyState`、 **loadedState**、 `openState`、 `activeState`、`activeUIState`です。 これらの状態については、記事を参照してください。[コンテナー: クライアント アイテムの状態](../../mfc/containers-client-item-states.md)です。  
  
### <a name="remarks"></a>コメント  
 OLE 項目の状態が変更されたときに通知するを使用して、 [OnChange](#onchange)メンバー関数。  
  
 詳細については、記事を参照してください。[コンテナー: クライアント アイテムの状態](../../mfc/containers-client-item-states.md)です。  
  
##  <a name="getlaststatus"></a>  COleClientItem::GetLastStatus  
 OLE の最後の操作のステータス コードを返します。  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `SCODE` 値。  
  
### <a name="remarks"></a>コメント  
 メンバー関数が返す、 **BOOL**値**FALSE**、またはその他のメンバー関数が返す**NULL**、`GetLastStatus`より詳細な障害情報を返します。 ほとんどの OLE メンバー関数がより重大なエラーに対して例外をスローすることに注意してください。 特定の情報の解釈について、`SCODE`最後に返される基になる OLE 呼び出しによって異なります、`SCODE`値。  
  
 詳細については`SCODE`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)Windows SDK のドキュメントです。  
  
##  <a name="getlinkupdateoptions"></a>  COleClientItem::GetLinkUpdateOptions  
 OLE 項目に対するリンク更新オプションの現在の値を取得するには、この関数を呼び出します。  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
- `OLEUPDATE_ALWAYS` 可能な場合は、リンクされた項目を更新します。 このオプションは、リンク ダイアログ ボックスで、リンクの自動更新オプション ボタンをサポートします。  
  
- `OLEUPDATE_ONCALL` コンテナー アプリケーションからの要求でのみリンク アイテムを更新 (ときに、 [UpdateLink](#updatelink)メンバー関数が呼び出されます)。 このオプションは、リンク ダイアログ ボックスで、リンクの手動更新オプション ボタンをサポートします。  
  
### <a name="remarks"></a>コメント  
 これは、高度な操作です。  
  
 この関数はによって自動的に呼び出されます、[関数](../../mfc/reference/colelinksdialog-class.md)クラスです。  
  
 詳細については、次を参照してください。 [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100) Windows SDK に含まれています。  
  
##  <a name="gettype"></a>  COleClientItem::GetType  
 OLE 項目が埋め込みまたはリンクされているかどうか、または静的なを判断するには、この関数を呼び出します。  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 次の値のいずれかの符号なし整数。  
  
- `OT_LINK` OLE 項目は、リンクです。  
  
- `OT_EMBEDDED` OLE 項目が埋め込まれます。  
  
- `OT_STATIC` OLE 項目が静的では、つまり、いないネイティブ データは、プレゼンテーション データのみが格納され、そのため、編集することはできません。  
  
##  <a name="getusertype"></a>  COleClientItem::GetUserType  
 「Word 文書」などの OLE 項目の型を記述するユーザーに表示される文字列を取得するには、この関数を呼び出す  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>パラメーター  
 *nUserClassType*  
 OLE 項目の型を記述する文字列の目的のバリエーションを示す値。 これは、次の値のいずれかを持つことができます。  
  
- `USERCLASSTYPE_FULL` 完全な型名をユーザーに表示されます。  
  
- `USERCLASSTYPE_SHORT` ポップアップ メニューとリンクの編集 ダイアログ ボックスで使用する短い名前 (15 文字以内)。  
  
- `USERCLASSTYPE_APPNAME` クラスをサービス アプリケーションの名前。  
  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md) OLE 項目の型を記述する文字列が返されるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 これは、システムの登録データベース内のエントリでは多くの場合です。  
  
 完全な型名が要求されましたが、使用不可の場合は、短い名前が使用されます。 登録データベース内で OLE 項目の種類のエントリが見つからないか、または OLE 項目の種類に登録されているユーザー型がない場合、ユーザーの種類に格納されている場合は、OLE アイテムが使用されます。 そのユーザーの種類名が空の文字列の場合は、「不明なオブジェクト」が使用されます。  
  
 詳細については、次を参照してください。 [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) Windows SDK に含まれています。  
  
##  <a name="isinplaceactive"></a>  COleClientItem::IsInPlaceActive  
 OLE 項目が、インプレース アクティブであるかどうかを確認するには、この関数を呼び出します。  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目が、インプレース アクティブ; である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 一般的で、項目を編集するかどうかに応じて異なるロジックを実行します。 関数は、現在の項目の状態がいずれかに等しいかどうかを確認、`activeState`または`activeUIState`です。  
  
##  <a name="islinkuptodate"></a>  COleClientItem::IsLinkUpToDate  
 OLE 項目が最新かどうかを表示するには、この関数を呼び出します。  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目が最新の状態の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 リンクされた項目は、古いは元のドキュメントが更新されている場合に指定できます。 内のリンクを含む埋め込みアイテムは、古くなんだ同様にことができます。 関数は、OLE アイテムのチェックを再帰的です。 OLE 項目が最新かどうかを決定できる更新を実際に実行する高価に注意してください。  
  
 これは、によって自動的と呼ばれる、[関数](../../mfc/reference/colelinksdialog-class.md)実装します。  
  
 詳細については、次を参照してください。 [:isuptodate](http://msdn.microsoft.com/library/windows/desktop/ms686624) Windows SDK に含まれています。  
  
##  <a name="ismodified"></a>  COleClientItem::IsModified  
 この関数では、かどうか OLE 項目がダーティ (最後に保存して以降に変更) を参照してください。  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目がダーティの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) Windows SDK に含まれています。  
  
##  <a name="isopen"></a>  COleClientItem::IsOpen  
 OLE 項目が開いているかどうかを表示するには、この関数を呼び出すつまり、別のウィンドウで実行されているサーバー アプリケーションのインスタンスで開かれます。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目が開いている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 () の陰影パターンを持つオブジェクトを描画する場合の判別に使用されます。 開いているオブジェクト、オブジェクトの上に描画されるハッチ パターンが必要です。 使用することができます、 [CRectTracker](../../mfc/reference/crecttracker-class.md)これを実現するオブジェクト。  
  
##  <a name="isrunning"></a>  COleClientItem::IsRunning  
 OLE 項目が実行中かどうかを表示するには、この関数を呼び出すつまり、かどうか、項目が読み込まれ、サーバー アプリケーションの実行中です。  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目が実行されている; 場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705) Windows SDK に含まれています。  
  
##  <a name="onactivate"></a>  COleClientItem::OnActivate  
 インプレース アクティブされただけのアイテムを通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>コメント  
 この関数が、サーバーが実行されている、そのユーザー インターフェイスはコンテナー アプリケーションのインストールされていることを示すためにないを示すためと呼ばれることに注意してください。 この時点で、オブジェクトには、アクティブなユーザー インターフェイスはありません (は`activeUIState`)。 メニューまたはツールバーのインストールされていません。 [入った](#onactivateui)が発生したときに、メンバー関数が呼び出されます。  
  
 既定の実装、 [OnChange](#onchange)メンバー関数が**OLE_CHANGEDSTATE**をパラメーターとして。 項目が、インプレース アクティブになったときに、カスタム処理を実行するには、この関数をオーバーライドします。  
  
##  <a name="onactivateui"></a>  COleClientItem::OnActivateUI  
 フレームワークによって`OnActivateUI`オブジェクトがアクティブな UI 状態に入ったときにします。  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトは、ツールバーとメニューはインストールされました。  
  
 既定の実装が記憶しているサーバーの`HWND`後で**で**呼び出しです。  
  
##  <a name="onchange"></a>  として  
 ユーザーを変更、保存すると、または OLE 項目を終了するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCode`  
 サーバーの理由には、この項目が変更されました。 次の値のいずれかを取ります。  
  
- `OLE_CHANGED` OLE 項目の外観が変更されました。  
  
- `OLE_SAVED` OLE 項目が保存されました。  
  
- `OLE_CLOSED` OLE 項目が閉じられました。  
  
- `OLE_CHANGED_STATE` OLE 項目は、別の 1 つの状態から変更されました。  
  
 `dwParam`  
 場合`nCode`は`OLE_SAVED`または`OLE_CLOSED`、このパラメーターは使用されません。 場合`nCode`は`OLE_CHANGED`、このパラメーターが変更された OLE 項目の外観を指定します。 使用可能な値は、次を参照してください。、`dwParam`のパラメーター[値](#draw)です。 場合`nCode`は`OLE_CHANGED_STATE`、このパラメーターは、 **COleClientItem::ItemState**値が列挙され、入力されている状態を説明します。 次の値の 1 つ持つことができます: `emptyState`、 **loadedState**、 `openState`、 `activeState`、または`activeUIState`です。  
  
### <a name="remarks"></a>コメント  
 (この関数がへの応答と呼ばれる Microsoft Foundation Class ライブラリを使用して、サーバー アプリケーションが記述されている場合、`Notify`のメンバー関数は`COleServerDoc`または`COleServerItem`)。場合は、変更として、既定の実装は、コンテナー ドキュメントをマーク`nCode`は`OLE_CHANGED`または`OLE_SAVED`です。  
  
 `OLE_CHANGED_STATE`から返された現在の状態[GetItemState](#getitemstate)以前の状態、つまり、この状態の変更の前に現在の状態ができます。  
  
 OLE 項目の状態の変更に応答するには、この関数をオーバーライドします。 通常、項目が表示されている領域を無効にして、項目の外観を更新します。 オーバーライドの先頭に基底クラスの実装を呼び出します。  
  
##  <a name="onchangeitemposition"></a>  に  
 コンテナーに、インプレース アクティブ化中に OLE 項目の範囲が変更されたことを通知するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectPos*  
 コンテナー アプリケーションのクライアント領域と相対的アイテムの位置を示します。  
  
### <a name="return-value"></a>戻り値  
 アイテムの位置が正常に変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装を呼び出し、OLE 項目の新しい表示四角形を決定[SetItemRects](#setitemrects)を新しい値。 既定の実装では、アイテムの表示の四角形を計算し、その情報をサーバーに渡します。  
  
 サイズ変更/移動操作に特別な規則を適用するには、この関数をオーバーライドします。 この呼び出しの結果、サーバーが呼び出されるため、アプリケーションは、MFC で記述された場合、[から](../../mfc/reference/coleserverdoc-class.md#requestpositionchange)です。  
  
##  <a name="ondeactivate"></a>  COleClientItem::OnDeactivate  
 OLE 項目が、インプレース アクティブ状態から遷移するときに、フレームワークによって呼び出されます ( `activeState`) 読み込み済みの状態、つまり、インプレース アクティブ化の後に非アクティブにします。  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>コメント  
 この関数が閉じたことを示す OLE アイテムは、いないコンテナー アプリケーションから削除された、ユーザー インターフェイスと呼ばれることに注意してください。 発生したときに、 [OnDeactivateUI](#ondeactivateui)メンバー関数が呼び出されます。  
  
 既定の実装、 [OnChange](#onchange)メンバー関数が**OLE_CHANGEDSTATE**をパラメーターとして。 インプレース アクティブな項目が非アクティブ化されたときに、カスタム処理を実行するには、この関数をオーバーライドします。 たとえば、コンテナー アプリケーションで元に戻すコマンドをサポートする場合ことができます関数をオーバーライドするこの元に戻す状態を破棄する項目が非アクティブ化する OLE 項目に対して実行される最後の操作が元に戻すことはできませんするを示すです。  
  
##  <a name="ondeactivateandundo"></a>  COleClientItem::OnDeactivateAndUndo  
 ユーザーは、インプレース OLE 項目をアクティブにした後、元に戻すコマンドを呼び出したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装[DeactivateUI](#deactivateui)サーバーのユーザー インターフェイスを非アクティブ化します。 コンテナー アプリケーションで元に戻すコマンドを実装する場合は、この関数をオーバーライドします。 オーバーライドの中で関数の基底クラスのバージョンを呼び出すし、最後のコマンドは、アプリケーションで実行を元に戻します。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743) Windows SDK に含まれています。  
  
##  <a name="ondeactivateui"></a>  COleClientItem::OnDeactivateUI  
 ユーザーには、インプレース アクティブになったアイテムが非アクティブ化時に呼び出されます。  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUndoable`  
 編集の変更が元に戻せるがないかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスをメニューや、インプレース アクティブ化用に作成されたその他のコントロールを非表示にする、元の状態に復元します。  
  
 場合`bUndoable`は**FALSE**コンテナーには、元に戻すコマンドが無効にする必要があります、サーバーによって、最後の操作が実行されることを示すために、有効で、コンテナーの元に戻す状態を破棄することができません。  
  
##  <a name="ondiscardundostate"></a>  COleClientItem::OnDiscardUndoState  
 ユーザーが OLE 項目の編集中に元に戻す状態を破棄するアクションを実行するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 コンテナー アプリケーションで元に戻すコマンドを実装する場合は、この関数をオーバーライドします。 オーバーライドの中では、コンテナー アプリケーションの元に戻す状態を破棄します。  
  
 サーバーでこの関数の呼び出しによって呼び出される可能性がある場合は、サーバーは、Microsoft Foundation Class ライブラリで書き込まれましたが、 [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate)です。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642) Windows SDK に含まれています。  
  
##  <a name="ongetclipboarddata"></a>  COleClientItem::OnGetClipboardData  
 取得するためにフレームワークによって呼び出されます、`COleDataSource`がいずれかへの呼び出しでクリップボードに配置されるすべてのデータを格納しているオブジェクト、 [CopyToClipboard](#copytoclipboard)または[(dodragdrop を)](#dodragdrop)メンバー関数。  
  
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
 ピクセル単位でオブジェクトの原点からのマウス カーソルのオフセットへのポインター。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クリップボード データを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を呼び出す[GetClipboardData](#getclipboarddata)です。  
  
##  <a name="ongetcliprect"></a>  COleClientItem::OnGetClipRect  
 フレームワークによって、`OnGetClipRect`インプレース編集されているアイテムのクリッピング四角形の座標を取得します。  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rClipRect*  
 クラスのオブジェクトへのポインター [CRect](../../atl-mfc-shared/reference/crect-class.md)アイテムのクリッピング四角形の座標を保持します。  
  
### <a name="remarks"></a>コメント  
 座標はコンテナー アプリケーション ウィンドウのクライアント領域と相対的ピクセルで表します。  
  
 既定の実装は、単に、項目が、インプレース アクティブ ビューのクライアントの四角形を返します。  
  
##  <a name="ongetitemposition"></a>  状態  
 フレームワークによって、`OnGetItemPosition`インプレース編集されている項目の座標を取得します。  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)アイテムの位置座標を格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 座標はコンテナー アプリケーション ウィンドウのクライアント領域と相対的ピクセルで表します。  
  
 この関数の既定の実装は、何も行いません。 インプレース編集をサポートするアプリケーションでは、その実装が必要です。  
  
##  <a name="ongetwindowcontext"></a>  COleClientItem::OnGetWindowContext  
 場所に項目がアクティブになったときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppMainFrame`  
 メイン フレーム ウィンドウへのポインターへのポインター。  
  
 `ppDocFrame`  
 ドキュメント フレーム ウィンドウへのポインターへのポインター。  
  
 `lpFrameInfo`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/ms693737)フレーム ウィンドウの情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、OLE アイテムの親ウィンドウに関する情報を取得します。  
  
 既定の実装がへのポインターを返します、コンテナーが MDI アプリケーションの場合、 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)オブジェクトに`ppMainFrame`と、アクティブなへのポインター [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 内のオブジェクト`ppDocFrame`. コンテナーが SDI アプリケーションの場合は、既定の実装がへのポインターを返します、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)オブジェクトに`ppMainFrame`し、返します**NULL**で`ppDocFrame`です。 既定の実装がのメンバーにおいても塗りつぶします`lpFrameInfo`です。  
  
 既定の実装は、アプリケーションを適合しない場合にのみ、この関数をオーバーライドします。たとえば、次のように、アプリケーションがあるユーザー インターフェイスのパラダイム SDI または MDI とは異なる場合です。 これは、高度なオーバーライド可能です。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::GetWindowContext](http://msdn.microsoft.com/library/windows/desktop/ms694366)と[受け取る](http://msdn.microsoft.com/library/windows/desktop/ms693737)Windows SDK 内の構造。  
  
##  <a name="oninsertmenus"></a>  COleClientItem::OnInsertMenus  
 空のメニューに、コンテナー アプリケーションのメニューを挿入する、インプレース アクティブ化時に、フレームワークによって呼び出されます。  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenuShared`  
 空のメニューへのポインター。  
  
 `lpMenuWidths`  
 6 つの配列を指す**長い**で次のメニュー グループの各メニューの数を示す値: ファイル、編集、コンテナー、オブジェクト、ウィンドウのヘルプ。 コンテナー アプリケーションは、ファイル、コンテナー、およびウィンドウ] メニューの [グループの 0、2、およびこの配列の 4 要素に対応します。  
  
### <a name="remarks"></a>コメント  
 このメニューは、コンポジット メニューを作成する独自のメニューを挿入すると、サーバーに渡されます。 この関数は、いくつかの複合メニューをビルドする繰り返し呼び出すことができます。  
  
 既定の実装を挿入`pMenuShared`インプレースでコンテナーのメニューです。 つまり、ファイル、コンテナー、およびウィンドウ メニュー グループ。 [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo)このメニュー リソースを設定するために使用します。 また、既定の実装は要素 0、2、および 4 に適切な値を割り当てます`lpMenuWidths`メニュー リソースに応じて、します。 既定の実装がアプリケーションに適していない場合は、この関数をオーバーライドします。たとえば、次のように、アプリケーションがドキュメントの種類とリソースの関連付けのドキュメント テンプレートを使用しない場合です。 この関数をオーバーライドする場合は上書きすることがも[とき](#onsetmenu)と[OnRemoveMenus](#onremovemenus)です。 これは、高度なオーバーライド可能です。  
  
 詳細については、次を参照してください。 [IOleInPlaceFrame::InsertMenus](http://msdn.microsoft.com/library/windows/desktop/ms683987) Windows SDK に含まれています。  
  
##  <a name="onremovemenus"></a>  COleClientItem::OnRemoveMenus  
 インプレース アクティブ化が終了すると、指定された複合メニューからコンテナーのメニューを削除するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenuShared`  
 呼び出しによって構築されたコンポジット メニューが指す、[とき](#oninsertmenus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 既定の実装はから削除`pMenuShared`インプレースでコンテナーのメニューは、ファイル、コンテナー、およびウィンドウのメニュー グループ。 既定の実装がアプリケーションに適していない場合は、この関数をオーバーライドします。たとえば、次のように、アプリケーションがドキュメントの種類とリソースの関連付けのドキュメント テンプレートを使用しない場合です。 この関数をオーバーライドする場合はおそらくをオーバーライドする[とき](#oninsertmenus)と[とき](#onsetmenu)もします。 これは、高度なオーバーライド可能です。  
  
 サブメニュー`pMenuShared`サーバーが繰り返し呼び出された場合、1 つ以上のコンポジット メニューで共有することが`OnInsertMenus`です。 そのため削除しないでサブメニューのオーバーライドで`OnRemoveMenus`; のみデタッチする必要があります。  
  
 詳細については、次を参照してください。 [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685) Windows SDK に含まれています。  
  
##  <a name="onscrollby"></a>  COleClientItem::OnScrollBy  
 サーバーからの要求に応えて OLE 項目をスクロールするためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>パラメーター  
 *sizeExtent*  
 (ピクセル単位) を x と y の方向のスクロール、距離を指定します。  
  
### <a name="return-value"></a>戻り値  
 項目がスクロールされた場合は 0 以外。項目がスクロールできない場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば、OLE アイテムが部分的に表示されると、ユーザーが、インプレース編集を実行中には表示領域外に移動、この関数は、カーソルを表示したままに呼び出されます。 既定の実装では、何も行われません。 指定した量によって、項目をスクロールするには、この関数をオーバーライドします。 スクロール、結果として OLE 項目の表示部分を変更できることに注意してください。 呼び出す[SetItemRects](#setitemrects)をアイテムの表示の四角形を更新します。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291) Windows SDK に含まれています。  
  
##  <a name="onsetmenu"></a>  COleClientItem::OnSetMenu  
 フレームワークによって呼び出されます、2 回、インプレース アクティブ化が開始され、終了するか。コンポジット メニューと、2 回目をインストールする最初の時間 (で`holemenu`と等しい**NULL**) を削除します。  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenuShared`  
 呼び出しによって構築されたコンポジット メニューへのポインター、[とき](#oninsertmenus)メンバー関数および`InsertMenu`関数。  
  
 `holemenu`  
 によって返されたメニュー記述子へのハンドル、 **OleCreateMenuDescriptor**関数、または**NULL**ディスパッチのコードを削除する場合。  
  
 *hwndActiveObject*  
 OLE 項目の編集ウィンドウへのハンドルします。 これは、OLE から編集コマンドを受信するウィンドウです。  
  
### <a name="remarks"></a>コメント  
 既定の実装をインストールまたはコンポジット メニューを削除してから、[その](http://msdn.microsoft.com/library/windows/desktop/ms692831)関数をインストールまたはディスパッチのコードを削除します。 既定の実装は、アプリケーションに適していない場合は、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくをオーバーライドする[とき](#oninsertmenus)と[OnRemoveMenus](#onremovemenus)もします。 これは、高度なオーバーライド可能です。  
  
 詳細については、次を参照してください。 [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415)、[その](http://msdn.microsoft.com/library/windows/desktop/ms692831)、および[IOleInPlaceFrame::SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713) Windows SDK に含まれています。  
  
##  <a name="onshowcontrolbars"></a>  COleClientItem::OnShowControlBars  
 コンテナー アプリケーションのコントロール バーを非表示にしたりするためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrameWnd`  
 コンテナー アプリケーションのフレーム ウィンドウへのポインター。 メイン フレーム ウィンドウまたは MDI 子ウィンドウのいずれかを指定できます。  
  
 `bShow`  
 コントロール バーを表示するか非表示にするかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 関数呼び出しのコントロール バーの状態の変更が発生した場合は 0 以外。0 呼び出すには、変更がない場合、または`pFrameWnd`がコンテナーのフレーム ウィンドウを指していません。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロール バーがで指定された状態で既に場合に 0 を返します*bShow です。* これが発生、たとえば、コントロール バーが非表示の場合と`bShow`は**FALSE**です。  
  
 既定の実装では、最上位のフレーム ウィンドウから、ツールバーを削除します。  
  
##  <a name="onshowitem"></a>  COleClientItem::OnShowItem  
 編集中に総合的に表示されていること、OLE アイテムを表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、埋め込みアイテムへのリンクをサポートしている場合に使用されます (からドキュメント クラスを派生する場合は、[直接](../../mfc/reference/colelinkingdoc-class.md))。 この関数は、インプレース アクティブ化または OLE 項目がリンク元と、ユーザーがそれを編集する時に呼び出されます。 既定の実装には、コンテナー ドキュメントの最初のビューがアクティブにします。 OLE 項目が表示されるようにドキュメントをスクロールするには、この関数をオーバーライドします。  
  
##  <a name="onupdateframetitle"></a>  COleClientItem::OnUpdateFrameTitle  
 フレーム ウィンドウのタイトル バーを更新する、インプレース アクティブ化時に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外の関数は、フレームのタイトルを正常に更新されました、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、フレーム ウィンドウのタイトルは変更されません。 この関数をオーバーライドする場合、別のフレームのタイトル、アプリケーションの例"*サーバー アプリ* - *項目*で*docname*"(と同様に、"MicrosoftExcel のスプレッドシートにレポートします。DOC") です。 これは、高度なオーバーライド可能です。  
  
##  <a name="reactivateandundo"></a>  COleClientItem::ReactivateAndUndo  
 OLE 項目を再アクティブ化して、一括編集するときに、ユーザーによって実行される最後の操作を元に戻すには、この関数を呼び出します。  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションでは、元に戻すコマンドをサポートする場合は、ユーザーは、OLE アイテムを非アクティブ化の直後に元に戻すコマンドを選択した場合、この関数を呼び出します。  
  
 Microsoft Foundation クラス ライブラリとサーバー アプリケーションが書き込まれると、この関数と、サーバーを呼び出す[されて](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo)です。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) Windows SDK に含まれています。  
  
##  <a name="release"></a>  COleClientItem::Release  
 OLE アイテムによって使用されているリソースをクリーンアップするのには、この関数を呼び出します。  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCloseOption`  
 読み込み済み状態に戻ったときに、OLE 項目を保存どのような状況を指定するフラグを設定します。 使用可能な値の一覧は、次を参照してください。 [COleClientItem::Close](#close)です。  
  
### <a name="remarks"></a>コメント  
 **リリース**によって呼び出される、`COleClientItem`デストラクターです。  
  
 詳細については、次を参照してください。 [iunknown::release](http://msdn.microsoft.com/library/windows/desktop/ms682317) Windows SDK に含まれています。  
  
##  <a name="reload"></a>  COleClientItem::Reload  
 閉じ、項目を再読み込みします。  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す、`Reload`関数への呼び出しによって別の型の項目として、項目をアクティブ化したら[ActivateAs](#activateas)です。  
  
##  <a name="run"></a>  COleClientItem::Run  
 この項目に関連付けられているアプリケーションを実行します。  
  
```  
void Run();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す、**実行**メンバー関数、項目をアクティブ化する前に、サーバー アプリケーションを起動します。 これは、によって自動的に[Activate](#activate)と[DoVerb](#doverb)いないこの関数を呼び出すために必要なことは通常、します。 アイテムの属性を設定するために、サーバーを実行する必要がある場合は、この関数を呼び出す[SetExtent](#setextent)、実行する前に[DoVerb](#doverb)です。  
  
##  <a name="setdrawaspect"></a>  COleClientItem::SetDrawAspect  
 呼び出す、 `SetDrawAspect` 「方法」と表示、または項目のビューを設定します。  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 `DVASPECT` 列挙体の値。 このパラメーターには、次のいずれかの値を指定できます。  
  
- `DVASPECT_CONTENT` 項目は、コンテナー内の埋め込みオブジェクトとして表示されること、このような方法で表されます。  
  
- `DVASPECT_THUMBNAIL` 参照ツールで表示できるように、「サムネイル」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON` 項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT` 項目は、[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように表されます。  
  
### <a name="remarks"></a>コメント  
 縦横比方法を指定した項目によって表示される[描画](#draw)その関数のための既定の値と`nDrawAspect`引数を使用します。  
  
 この関数はアイコンの変更 (およびその他のダイアログ ボックス、アイコンの変更 ダイアログ ボックスを直接呼び出すこと) によって自動的に呼び出されます。 ユーザーによって要求されたときに表示の外観の縦横比を有効にします。  
  
##  <a name="setextent"></a>  COleClientItem::SetExtent  
 OLE 項目を使用可能な領域の量を指定するには、この関数を呼び出します。  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)サイズの情報を含むオブジェクトです。  
  
 `nDrawAspect`  
 境界を設定する OLE アイテムの縦横比を指定します。 使用可能な値は、次を参照してください。[外観](#setdrawaspect)です。  
  
### <a name="remarks"></a>コメント  
 これにより、サーバー アプリケーションでは、Microsoft Foundation Class ライブラリを使用して書き込まれますが場合、 [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent)の対応するメンバー関数`COleServerItem`に呼び出されるオブジェクト。 OLE 項目は、その表示を適宜調整することができますし。 ディメンションがである必要があります`MM_HIMETRIC`単位です。 ユーザー OLE 項目のサイズを変更するとき、または何らかの形式のレイアウトのネゴシエーションをサポートする場合は、この関数を呼び出します。  
  
 詳細については、次を参照してください。 [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) Windows SDK に含まれています。  
  
##  <a name="sethostnames"></a>  COleClientItem::SetHostNames  
 コンテナー アプリケーションの名前と OLE 埋め込みアイテムのコンテナーの名前を指定するには、この関数を呼び出します。  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszHost`  
 コンテナー アプリケーションのユーザーに表示される名前へのポインター。  
  
 `lpszHostObj`  
 OLE 項目を含むコンテナーの識別文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出す場合は、Microsoft Foundation Class ライブラリを使用して、サーバー アプリケーションが書き込んだ、[されていると](../../mfc/reference/coleserverdoc-class.md#onsethostnames)のメンバー関数、 `COleServerDoc` OLE 項目が含まれるドキュメント。 この情報は、OLE 項目を編集するときにウィンドウのタイトルに使用されます。 コンテナー ドキュメントが読み込まれるたびに、フレームワークは、ドキュメント内のすべての OLE 項目に対してこの関数を呼び出します。 `SetHostNames` 埋め込みアイテムにのみ適用されます。 編集用 OLE 埋め込みアイテムがアクティブ化するたびにこの関数を呼び出す必要はありません。  
  
 これも自動的に呼び出されますドキュメント名とアプリケーションの名前でオブジェクトが読み込まれるときに、または別の名前でファイルを保存します。 したがって、この関数を直接呼び出す通常必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) Windows SDK に含まれています。  
  
##  <a name="seticonicmetafile"></a>  COleClientItem::SetIconicMetafile  
 項目のアイコンを描画するために使われるメタファイルをキャッシュします。  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMetaPict`  
 項目のアイコンを描画するために使われるメタファイルへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して[GetIconicMetafile](#geticonicmetafile)メタファイルを取得します。  
  
 `hMetaPict`パラメーターが、項目にコピーされたため、`hMetaPict`呼び出し元によって解放する必要があります。  
  
##  <a name="setitemrects"></a>  COleClientItem::SetItemRects  
 外接する四角形または OLE 項目の表示の四角形を設定するには、この関数を呼び出します。  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lprcPosRect*  
 クライアント座標で、その親ウィンドウの基準とした OLE 項目の境界を含む四角形を指すポインター。  
  
 *lprcClipRect*  
 クライアント座標で、その親ウィンドウの基準とした OLE 項目の表示部分の境界を含む四角形を指すポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、既定の実装によって呼び出す、 [:onchangeitemposition](#onchangeitemposition)メンバー関数。 位置または表示部分の OLE 項目が変更されたときに、この関数を呼び出す必要があります。 つまり通常、ビューから呼び出すこと[OnSize](../../mfc/reference/cwnd-class.md#onsize)と[OnScrollBy](../../mfc/reference/cview-class.md#onscrollby)メンバー関数。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) Windows SDK に含まれています。  
  
##  <a name="setlinkupdateoptions"></a>  COleClientItem::SetLinkUpdateOptions  
 指定したリンク アイテムの表示のリンクの更新オプションを設定するには、この関数を呼び出します。  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwUpdateOpt*  
 この項目に対するリンク更新オプションの値です。 この値は、次のいずれかにする必要があります。  
  
- `OLEUPDATE_ALWAYS` 可能な場合は、リンクされた項目を更新します。 このオプションは、リンク ダイアログ ボックスで、リンクの自動更新オプション ボタンをサポートします。  
  
- `OLEUPDATE_ONCALL` コンテナー アプリケーションからの要求でのみリンク アイテムを更新 (ときに、 [UpdateLink](#updatelink)メンバー関数が呼び出されます)。 このオプションは、リンク ダイアログ ボックスで、リンクの手動更新オプション ボタンをサポートします。  
  
### <a name="remarks"></a>コメント  
 通常、リンク ダイアログ ボックスでユーザーが選択した更新オプションを変更する必要がありません。  
  
 詳細については、次を参照してください。 [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120) Windows SDK に含まれています。  
  
##  <a name="setprintdevice"></a>  COleClientItem::SetPrintDevice  
 この項目の出力先のデバイスを変更するには、この関数を呼び出します。  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptd`  
 ポインター、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)データ構造は、新しい出力先デバイスに関する情報が含まれています。 指定できます**NULL**です。  
  
 `ppd`  
 ポインター、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940)データ構造は、新しい出力先デバイスに関する情報が含まれています。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、項目の出力先デバイス ソフトウェア更新プログラムが、プレゼンテーション キャッシュは更新しません。 アイテムのプレゼンテーションのキャッシュを更新するには、呼び出す[UpdateLink](#updatelink)です。  
  
 この関数の引数には、ターゲット デバイスを識別する OLE システムが使用されている情報が含まれています。 **PRINTDLG**構造体には、Windows に共通の印刷 ダイアログ ボックスを初期化するために使用する情報が含まれています。 ユーザーは、ダイアログ ボックスを閉じ、後に、Windows はこの構造体でユーザーの選択に関する情報を返します。 `m_pd`のメンバー、 [CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトが、 **PRINTDLG**構造体。  
  
 この構造体の詳細については、次を参照してください。 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Windows SDK に含まれています。  
  
##  <a name="updatelink"></a>  COleClientItem::UpdateLink  
 OLE 項目のプレゼンテーション データを直ちに更新するには、この関数を呼び出します。  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 リンクされた項目は、関数は OLE 項目の新しいプレゼンテーションを取得するリンクのソースを検索します。 このプロセスでは、時間がかかる可能性がありますが、1 つまたは複数のサーバー アプリケーションを実行する必要があります。 埋め込みアイテムの関数の再帰的に、埋め込み項目が期限切れになる可能性があるリンクを含めるかどうかをチェックして、それらの更新動作します。 ユーザーは、リンク ダイアログ ボックスを使用して個々 のリンクを手動で更新できます。  
  
 詳細については、次を参照してください。 [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660) Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCBIND](../../visual-cpp-samples.md)   
 [MFC サンプル OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem クラス](../../mfc/reference/cdocitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)

---
title: COleDocument クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
dev_langs:
- C++
helpviewer_keywords:
- COleDocument [MFC], COleDocument
- COleDocument [MFC], AddItem
- COleDocument [MFC], ApplyPrintDevice
- COleDocument [MFC], EnableCompoundFile
- COleDocument [MFC], GetInPlaceActiveItem
- COleDocument [MFC], GetNextClientItem
- COleDocument [MFC], GetNextItem
- COleDocument [MFC], GetNextServerItem
- COleDocument [MFC], GetPrimarySelectedItem
- COleDocument [MFC], GetStartPosition
- COleDocument [MFC], HasBlankItems
- COleDocument [MFC], OnShowViews
- COleDocument [MFC], RemoveItem
- COleDocument [MFC], UpdateModifiedFlag
- COleDocument [MFC], OnEditChangeIcon
- COleDocument [MFC], OnEditConvert
- COleDocument [MFC], OnEditLinks
- COleDocument [MFC], OnFileSendMail
- COleDocument [MFC], OnUpdateEditChangeIcon
- COleDocument [MFC], OnUpdateEditLinksMenu
- COleDocument [MFC], OnUpdateObjectVerbMenu
- COleDocument [MFC], OnUpdatePasteLinkMenu
- COleDocument [MFC], OnUpdatePasteMenu
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6317d7c14f76355df908c9809df633533df3fb61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377123"
---
# <a name="coledocument-class"></a>COleDocument クラス
ビジュアル編集をサポートする OLE ドキュメントの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|`COleDocument` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|文書で保持されている項目の一覧に項目を追加します。|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|ドキュメントのすべてのクライアント アイテムの出力先のデバイスを設定します。|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|OLE 構造化ストレージ ファイル形式を使用して保存するドキュメントが発生します。|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|現在、インプレース アクティブである OLE 項目を返します。|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|反復処理するためには、クライアントの次の項目を取得します。|  
|[COleDocument::GetNextItem](#getnextitem)|反復処理するためには、ドキュメントの次の項目を取得します。|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|反復処理するためには、サーバーの次の項目を取得します。|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|ドキュメント内のプライマリ選択されている OLE 項目を返します。|  
|[COleDocument::GetStartPosition](#getstartposition)|初期のイテレーションを開始する位置を取得します。|  
|[COleDocument::HasBlankItems](#hasblankitems)|ドキュメント内の空白の項目を確認します。|  
|[COleDocument::OnShowViews](#onshowviews)|表示または非表示、ドキュメントはときに呼び出されます。|  
|[COleDocument::RemoveItem](#removeitem)|文書で保持されている項目の一覧から項目を削除します。|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|内包されている OLE 項目のいずれかが変更された場合に変更されたドキュメントをマークします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|アイコンの変更のメニュー コマンドのイベントを処理します。|  
|[COleDocument::OnEditConvert](#oneditconvert)|別の型に埋め込みまたはリンクされたオブジェクトの変換を処理します。|  
|[COleDocument::OnEditLinks](#oneditlinks)|[編集] メニューへのリンク コマンド内のイベントを処理します。|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|ドキュメントを添付して、メッセージを送信します。|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|アイコンの変更/編集 メニュー オプションのコマンド UI を更新するためにフレームワークによって呼び出されます。|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|コマンド UI/リンクの編集 メニュー オプションを更新するためにフレームワークによって呼び出されます。|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|編集のためコマンド UI を更新するためにフレームワークによって呼び出されます/ *ObjectName*メニュー オプションを編集からアクセスされる動詞 サブメニュー/ *ObjectName*です。|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|貼り付けメニュー オプションのコマンド UI を更新するためにフレームワークによって呼び出されます。|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|貼り付けのメニュー オプションをコマンド UI を更新するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 `COleDocument` 派生した**CDocument**、これにより、Microsoft Foundation Class ライブラリによって提供されるドキュメント/ビュー アーキテクチャを使用する OLE アプリケーションです。  
  
 `COleDocument` コレクションとして、ドキュメントを扱う[CDocItem](../../mfc/reference/cdocitem-class.md) OLE 項目を処理するオブジェクト。 コンテナーとサーバーの両方のアプリケーションでは、自分のドキュメントは、OLE アイテムを格納することでなければならないために、このようなアーキテクチャが必要があります。 [COleServerItem](../../mfc/reference/coleserveritem-class.md)と[COleClientItem](../../mfc/reference/coleclientitem-class.md)両方から派生したクラス、`CDocItem`アプリケーションと OLE アイテム間の相互作用を管理します。  
  
 単純なコンテナー アプリケーションを作成している場合からドキュメント クラスを派生させる`COleDocument`です。 ドキュメントが含まれている埋め込みアイテムへのリンクをサポートするコンテナー アプリケーションを作成している場合からドキュメント クラスを派生させる[直接](../../mfc/reference/colelinkingdoc-class.md)です。 作成する場合、サーバー アプリケーションまたは組み合わせのコンテナー/サーバー、クラス、ドキュメントから[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)です。 `COleLinkingDoc` および`COleServerDoc`から派生した`COleDocument`ので、これらのクラスは継承で使用できるすべてのサービス、`COleDocument`と**CDocument**です。  
  
 使用する`COleDocument`クラスの派生、およびアプリケーションの非 OLE データだけでなく埋め込みまたはリンクされた項目を管理する機能を追加します。 定義した場合`CDocItem`-アプリケーションのネイティブ データを格納するクラスを派生によって定義された既定の実装を使用することができます`COleDocument`OLE と非 OLE データの両方を格納します。 OLE 項目から個別に非 OLE データを格納するための独自のデータ構造を設計することもできます。 詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md)..  
  
 **CDocument**メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 `COleDocument` 更新が[OnFileSendMail](#onfilesendmail)複合ドキュメントを正しく処理します。 詳細については、記事を参照してください[MAPI](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)..  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="additem"></a>  COleDocument::AddItem  
 ドキュメントに項目を追加するには、この関数を呼び出します。  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 追加されるドキュメント項目へのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出された場合に、この関数を明示的に呼び出す必要はありません、`COleClientItem`または`COleServerItem`ドキュメントへのポインターを受け取るコンス トラクターです。  
  
##  <a name="applyprintdevice"></a>  COleDocument::ApplyPrintDevice  
 埋め込まれたすべての出力先デバイスを変更するには、この関数を呼び出す[COleClientItem](../../mfc/reference/coleclientitem-class.md)アプリケーションのコンテナー ドキュメント内の項目。  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptd`  
 ポインター、 **DVTARGETDEVICE**データ構造は、新しい出力先デバイスに関する情報が含まれています。 指定できます**NULL**です。  
  
 `ppd`  
 ポインター、 **PRINTDLG**データ構造は、新しい出力先デバイスに関する情報が含まれています。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、すべての項目の出力先デバイス ソフトウェア更新プログラムが、それらのアイテムのプレゼンテーション キャッシュは更新しません。 アイテムのプレゼンテーションのキャッシュを更新するには、呼び出す[COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)です。  
  
 この関数の引数には、OLE がターゲット デバイスの識別に使用される情報が含まれています。 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)構造体には、Windows に共通の印刷 ダイアログ ボックスを初期化するために使用する情報が含まれています。 ユーザーは、ダイアログ ボックスを閉じ、後に、Windows はこの構造体でユーザーの選択に関する情報を返します。 `m_pd`のメンバー、 [CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトが、 **PRINTDLG**構造体。  
  
 詳細については、次を参照してください。、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Windows SDK 内の構造。  
  
 詳細については、次を参照してください。、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Windows SDK 内の構造。  
  
##  <a name="coledocument"></a>  COleDocument::COleDocument  
 `COleDocument` オブジェクトを構築します。  
  
```  
COleDocument();
```  
  
##  <a name="enablecompoundfile"></a>  COleDocument::EnableCompoundFile  
 複合ファイル形式を使用してドキュメントを格納する場合は、この関数を呼び出します。  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 複合ファイルのサポートを有効または無効になっているかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 これは構造化ストレージとも呼ばれます。 通常のコンス トラクターからこの関数を呼び出す、 `COleDocument`-クラスを派生します。 複合ドキュメントの詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md)..  
  
 このメンバー関数を呼び出さない場合は、構造化されていない ("") フラットファイルの形式でドキュメントに格納されています。  
  
 複合ファイルのサポートを有効になっているまたはドキュメントに対して無効にすると、ドキュメントの有効期間中に、設定を変更できません必要があります。  
  
##  <a name="getinplaceactiveitem"></a>  COleDocument::GetInPlaceActiveItem  
 項目の OLE を取得するには、この関数の呼び出しが現在によって識別されるビューを含むフレーム ウィンドウ内の場所にアクティブ化`pWnd`です。  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コンテナーのドキュメントを表示するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 1 つ、インプレース アクティブ OLE アイテムへのポインター**NULL**かどうか項目がない OLE 現在「、インプレース アクティブ」状態にします。  
  
##  <a name="getnextclientitem"></a>  COleDocument::GetNextClientItem  
 この関数では、クライアントの各アイテム、ドキュメントにアクセスするには、繰り返しです。  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**値セットの前の呼び出しによって`GetNextClientItem`; 初期値がによって返される、`GetStartPosition`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 ドキュメントでは、次のクライアント アイテムへのポインターまたは**NULL**クライアント項目がある場合。  
  
### <a name="remarks"></a>コメント  
 値は、各呼び出しの後に`pos`可能性がありますまたはクライアント アイテムとは限りませんが、ドキュメント内の次の項目を設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="getnextitem"></a>  COleDocument::GetNextItem  
 この関数へのアクセス、ドキュメント内の項目の各繰り返しを呼び出します。  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**値セットの前の呼び出しによって`GetNextItem`; 初期値がによって返される、`GetStartPosition`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 指定した位置にあるドキュメント項目へのポインター。  
  
### <a name="remarks"></a>コメント  
 値は、各呼び出しの後に`pos`に設定されている、**位置**ドキュメント内の次の項目の値。 取得した要素がドキュメントではの新しい値の最後の要素の場合`pos`は**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="getnextserveritem"></a>  COleDocument::GetNextServerItem  
 この関数へのアクセス サーバーのアイテム、ドキュメント内の各繰り返しを呼び出します。  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**値セットの前の呼び出しによって`GetNextServerItem`; 初期値がによって返される、`GetStartPosition`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 このドキュメントでは、次のサーバー項目へのポインターまたは**NULL**サーバー項目がある場合。  
  
### <a name="remarks"></a>コメント  
 値は、各呼び出しの後に`pos`可能性がありますまたはサーバーのアイテムとは限りませんが、ドキュメント内の次の項目を設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="getprimaryselecteditem"></a>  COleDocument::GetPrimarySelectedItem  
 指定したビューで現在選択されている OLE 項目を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pView`  
 ドキュメントを表示するアクティブなビュー オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 1 つ、選択した OLE アイテムへのポインター**NULL** OLE 項目が選択されていないか、いずれかが選択されている場合、複数の場合。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、含まれている OLE の一覧に単一選択項目の項目を検索し、ポインターを返します。 選択すると、項目が存在しないか、かどうかは、選択した 1 つ以上の項目が、関数を返します**NULL**です。 オーバーライドする必要があります、`CView::IsSelected`操作するには、この関数のビュー クラスのメンバー関数。 内包されている OLE 項目を格納する、独自のメソッドがある場合は、この関数をオーバーライドします。  
  
##  <a name="getstartposition"></a>  COleDocument::GetStartPosition  
 この関数では、ドキュメント内の最初の項目の位置を取得します。  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**ドキュメントの項目を反復処理を開始するために使用する値**NULL**ドキュメントに項目がないです。  
  
### <a name="remarks"></a>コメント  
 返される値を渡す`GetNextItem`、 `GetNextClientItem`、または`GetNextServerItem`です。  
  
##  <a name="hasblankitems"></a>  COleDocument::HasBlankItems  
 この関数では、ドキュメントにブランク アイテムが含まれるかどうかを決定します。  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントには、ブランク アイテムが含まれている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 空のアイテムは、1 つ含む四角形は空です。  
  
##  <a name="oneditchangeicon"></a>  COleDocument::OnEditChangeIcon  
 OLE の アイコンの変更 ダイアログ ボックスを表示し、ユーザーの選択 ダイアログ ボックスで、アイコンを現在選択されている OLE 項目を表すアイコンを変更します。  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>コメント  
 `OnEditChangeIcon` 作成し、起動、`COleChangeIconDialog`アイコンの変更 ダイアログ ボックス。  
  
##  <a name="oneditconvert"></a>  COleDocument::OnEditConvert  
 OLE 変換 ダイアログ ボックスが表示されますや変換に従ってユーザーの選択 ダイアログ ボックスで現在選択されている OLE 項目をアクティブにしてください。  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>コメント  
 `OnEditConvert` 作成し、起動、`COleConvertDialog`変換 ダイアログ ボックス。  
  
 変換の例には、ワードパッドのドキュメントに、Microsoft Word 文書が変換します。  
  
##  <a name="oneditlinks"></a>  COleDocument::OnEditLinks  
 OLE/リンクの編集 ダイアログ ボックスが表示されます。  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>コメント  
 `OnEditLinks` 作成し、起動、`COleLinksDialog`ユーザーがリンクされているオブジェクトを変更できるリンク ダイアログ ボックス。  
  
##  <a name="onfilesendmail"></a>  COleDocument::OnFileSendMail  
 常駐しているメール ホスト経由でメッセージ (あれば) して送信ドキュメントの添付ファイルとしてします。  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>コメント  
 `OnFileSendMail` 呼び出し`OnSaveDocument`(保存) は、電子メールで送信し、一時ファイルに無題と変更されたドキュメントをシリアル化します。 ドキュメントが変更されていない場合、一時ファイルは必要ありません。オリジナルが送信されます。 `OnFileSendMail` MAPI32 を読み込みます。DLL が既に読み込まれていない場合。  
  
 実装とは異なり`OnFileSendMail`の**CDocument**、この関数は、複合ファイルを正しく処理されます。  
  
 詳細については、次を参照してください、 [MAPI トピック](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)記事..  
  
##  <a name="onshowviews"></a>  COleDocument::OnShowViews  
 フレームワークは、状態の変更、ドキュメントの表示後にこの関数を呼び出します。  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 `bVisible`  
 表示または非表示にドキュメントがなくなっているかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定のバージョンでは、何も行われません。 アプリケーションがドキュメントの表示が変更されたときに、特別な処理を実行する必要がある場合は、それをオーバーライドします。  
  
##  <a name="onupdateeditchangeicon"></a>  COleDocument::OnUpdateEditChangeIcon  
 編集 メニューのアイコンの変更 コマンドを更新するためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`更新コマンドを作成するメニューを表す構造です。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を通じて構造体`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 `OnUpdateEditChangeIcon` 有効なアイコンがドキュメントに存在するかどうかによって、コマンドのユーザー インターフェイスを更新します。 動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="onupdateeditlinksmenu"></a>  COleDocument::OnUpdateEditLinksMenu  
 編集 メニューの リンク コマンドを更新するためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`更新コマンドを作成するメニューを表す構造です。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を通じて構造体`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 以降で、ドキュメント内の最初の OLE 項目`OnUpdateEditLinksMenu`の各項目にアクセスする、アイテムが、リンクにあり、リンクである場合、リンクのコマンドを有効にするかどうかをテストします。 動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="onupdateobjectverbmenu"></a>  COleDocument::OnUpdateObjectVerbMenu  
 更新するためにフレームワークによって呼び出されます、 *ObjectName*編集 メニューからアクセスされる動詞 サブメニューでコマンド、 *ObjectName*コマンド、場所*ObjectName*の名前を指定しますOLE オブジェクトは、ドキュメントに埋め込まれます。  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`更新コマンドを作成するメニューを表す構造です。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を通じて構造体`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 `OnUpdateObjectVerbMenu` 更新プログラム、 *ObjectName*ドキュメントに有効なオブジェクトが存在するかどうかによって、コマンドのユーザー インターフェイス。 オブジェクトが存在する場合、 *ObjectName* [編集] メニューのコマンドを有効にします。 このメニュー コマンドを選択すると、動詞のサブメニューが表示されます。 動詞サブメニューには、編集、プロパティ、およびよびななど、オブジェクトで使用できるすべての動詞コマンドが含まれています。 動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="onupdatepastelinkmenu"></a>  COleDocument::OnUpdatePasteLinkMenu  
 リンクされた OLE 項目をクリップボードから貼り付けできるかどうかを判断するためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`更新コマンドを作成するメニューを表す構造です。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を通じて構造体`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 貼り付け コマンドが有効になっているか、アイテムがドキュメントに貼り付けられるかどうかによって無効になっています。  
  
##  <a name="onupdatepastemenu"></a>  COleDocument::OnUpdatePasteMenu  
 OLE 埋め込みアイテムをクリップボードから貼り付けできるかどうかを判断するためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`更新コマンドを作成するメニューを表す構造です。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を通じて構造体`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 [貼り付け] コマンドとボタン有効/無効のアイテムがドキュメントに貼り付けられるかどうかによって異なります。  
  
##  <a name="removeitem"></a>  COleDocument::RemoveItem  
 ドキュメントから項目を削除するには、この関数を呼び出します。  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 削除するドキュメント項目へのポインター。  
  
### <a name="remarks"></a>コメント  
 通常必要はありませんこの関数を明示的に呼び出すデストラクターで呼び出された`COleClientItem`と`COleServerItem`です。  
  
##  <a name="updatemodifiedflag"></a>  COleDocument::UpdateModifiedFlag  
 内包されている OLE 項目のいずれかが変更された場合に変更されたドキュメントをマークするには、この関数を呼び出します。  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>コメント  
 これにより、ドキュメントのネイティブのデータが変更されていない場合でもを閉じる前にドキュメントを保存するように求めるために、フレームワークです。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル コンテナー](../../visual-cpp-samples.md)   
 [MFC サンプル MFCBIND](../../visual-cpp-samples.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




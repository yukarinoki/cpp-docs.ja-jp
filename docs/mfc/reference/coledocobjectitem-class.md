---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
ms.openlocfilehash: a696226185dd99b9e277e74d92cbe15c95cc900a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375049"
---
# <a name="coledocobjectitem-class"></a>クラス

Active ドキュメント コンテインメントを実装します。

## <a name="syntax"></a>構文

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[オブジェクトアイテムを選択します。](#coledocobjectitem)|項目を`COleDocObject`構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトアイテム::Do 既定の印刷](#dodefaultprinting)|既定のプリンター設定を使用して、コンテナー アプリケーションのドキュメントを印刷します。|
|[オブジェクト::コマンド](#execcommand)|ユーザーが指定したコマンドを実行します。|
|[オブジェクトアイテム::アクティブビュー](#getactiveview)|ドキュメントのアクティブ なビューを取得します。|
|[オブジェクト::ページ数](#getpagecount)|コンテナー アプリケーションのドキュメント内のページ数を取得します。|
|[印刷の準備を開始します。](#onprepareprinting)|コンテナー アプリケーションのドキュメントを印刷用に準備します。|
|[オブジェクト::オンプリント](#onprint)|コンテナー アプリケーションのドキュメントを印刷します。|
|[オブジェクト::クエリコマンド](#querycommand)|ユーザー インターフェイスのイベントによって生成された 1 つ以上のコマンドの状態を調べるためにクエリを実行します。|
|[オブジェクト::リリース](#release)|OLE リンク アイテムへの接続を解放し、開いている場合は閉じます。 クライアント アイテムを破棄しません。|

## <a name="remarks"></a>解説

MFC では、Active ドキュメントは、通常の埋め込みで編集できる通常の埋め込みと同様に処理されます。

- 派生`COleDocument`クラスは、現在埋め込まれている項目のリストを保持します。ただし、これらの項目は-derived 項目である`COleDocObjectItem`可能性があります。

- アクティブドキュメントがアクティブな場合、インプレースアクティブの場合、ビューのクライアント領域全体が占有されます。

- Active ドキュメント コンテナは、[**ヘルプ**] メニューをフル コントロールで管理します。

- **[ヘルプ**] メニューには、Active ドキュメント コンテナーとサーバーの両方のメニュー項目が含まれています。

Active ドキュメント コンテナは **[ヘルプ**] メニューを所有するため、サーバーの**ヘルプ**メニュー メッセージをサーバーに転送する役割を担います。 この統合は によって`COleDocObjectItem`処理されます。

メニューの結合とアクティブ ドキュメントのアクティブ化の詳細については、「[アクティブ ドキュメントコンテインメント](../../mfc/active-document-containment.md)の概要 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coledocobjectitemcoledocobjectitem"></a><a name="coledocobjectitem"></a>オブジェクトアイテムを選択します。

オブジェクトを初期化するには、このメンバー`COleDocObjectItem`関数を呼び出します。

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
アクティブなドキュメント`COleDocument`コンテナーとして機能するオブジェクトへのポインター。 IMPLEMENT_SERIALIZEを有効にするには、このパラメーターを NULL にする必要があります。 通常、OLE アイテムは NULL 以外のドキュメント ポインタで構成されます。

## <a name="coledocobjectitemdodefaultprinting"></a><a name="dodefaultprinting"></a>オブジェクトアイテム::Do 既定の印刷

既定の設定を使用して、フレームワークによってドキュメントに呼び出されます。

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*呼び出し元*<br/>
印刷コマンドを送信している[CView](../../mfc/reference/cview-class.md)オブジェクトへのポインター。

*Pinfo*<br/>
印刷するジョブを記述する[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)オブジェクトへのポインター。

## <a name="coledocobjectitemexeccommand"></a><a name="execcommand"></a>オブジェクト::コマンド

ユーザーが指定したコマンドを実行するには、このメンバー関数を呼び出します。

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
実行するコマンドの識別子。 によって識別されるグループに*含まれる*必要があります。

*をクリックします。*<br/>
コマンド実行オプションを指定します。 デフォルトでは、ユーザーにプロンプトを表示せずにコマンドを実行するように設定されます。 値のリストについては[、OLECMDEXECOPT](/windows/win32/api/docobj/ne-docobj-olecmdexecopt)を参照してください。

*グループ化*<br/>
コマンド グループを表す一意の識別子です。 既定では、標準グループを指定する NULL。 *nCmdID*で渡されるコマンドは、グループに属している必要があります。

### <a name="return-value"></a>戻り値

成功した場合はS_OKを返します。それ以外の場合は、次のいずれかのエラー コードを返します。

|[値]|説明|
|-----------|-----------------|
|E_UNEXPECTED|Unexpected error occurred. (予期しないエラーが発生しました。)|
|E_FAIL|エラーが発生しました。|
|E_NOTIMPL|MFC 自体がコマンドの変換とディスパッチを試みることを示します。|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup*は NULL 以外ですが、認識されたコマンド グループを指定しません。|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID*は、グループ pGroup の有効なコマンドとして認識されません。|
|OLECMDERR_DISABLED|*nCmdID*で識別されたコマンドは無効になっており、実行できません。|
|OLECMDERR_NOHELP|呼び出し元は*nCmdID*で識別されたコマンドに関するヘルプを求めましたが、ヘルプがありません。|
|OLECMDERR_CANCELLED|ユーザーは実行をキャンセルしました。|

### <a name="remarks"></a>解説

*pguidCmdGroup*と*nCmdID*パラメーターを一緒に呼び出すコマンドを一意に識別します。 *nCmdExecOpt*パラメーターは、実行する正確なアクションを指定します。

## <a name="coledocobjectitemgetactiveview"></a><a name="getactiveview"></a>オブジェクトアイテム::アクティブビュー

現在アクティブなビューの`IOleDocumentView`インターフェイスへのポインターを取得します。

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>戻り値

現在アクティブなビューの[インターフェイス](/windows/win32/api/docobj/nn-docobj-ioledocumentview)へのポインター。 現在のビューがない場合は、NULL を返します。

### <a name="remarks"></a>解説

返された`IOleDocumentView`ポインターの参照カウントは、この関数から返される前にインクリメントされません。

## <a name="coledocobjectitemgetpagecount"></a><a name="getpagecount"></a>オブジェクト::ページ数

ドキュメント内のページ数を取得します。

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
ドキュメントの最初のページの番号へのポインター。 呼び出し元がこの番号を必要としないことを示す NULL を指定できます。

*pc ページ*<br/>
ドキュメント内のページの合計数へのポインター。 呼び出し元がこの番号を必要としないことを示す NULL を指定できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="coledocobjectitemonprepareprinting"></a><a name="onprepareprinting"></a>印刷の準備を開始します。

このメンバー関数は、ドキュメントを印刷用に準備するために、フレームワークによって呼び出されます。

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>パラメーター

*呼び出し元*<br/>
印刷コマンドを送信している[CView](../../mfc/reference/cview-class.md)オブジェクトへのポインター。

*Pinfo*<br/>
印刷するジョブを記述する[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)オブジェクトへのポインター。

*すべてを印刷する*<br/>
文書全体を印刷するかどうかを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="coledocobjectitemonprint"></a><a name="onprint"></a>オブジェクト::オンプリント

このメンバー関数は、ドキュメントを印刷するためにフレームワークによって呼び出されます。

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>パラメーター

*呼び出し元*<br/>
印刷コマンドを送信している CView オブジェクトへのポインター。

*Pinfo*<br/>
印刷するジョブを記述する[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)オブジェクトへのポインター。

*すべてを印刷する*<br/>
文書全体を印刷するかどうかを指定します。

## <a name="coledocobjectitemquerycommand"></a><a name="querycommand"></a>オブジェクト::クエリコマンド

ユーザー インターフェイスのイベントによって生成された 1 つ以上のコマンドの状態を調べるためにクエリを実行します。

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
照会されるコマンドの識別子。

*ステータス*<br/>
クエリの結果として返されるフラグへのポインター。 使用可能な値の一覧については、 [OLECMDF](/windows/win32/api/docobj/ne-docobj-olecmdf)を参照してください。

*をクリックします。*<br/>
単一のコマンドの名前と状態情報を返す[OLECMDTEXT](/windows/win32/api/docobj/ns-docobj-olecmdtext)構造体へのポインター。 呼び出し元がこの情報を必要としないことを示すには、NULL を指定できます。

*グループ化*<br/>
コマンド グループを表す一意の識別子です。標準グループを指定するには NULL を指定できます。

### <a name="return-value"></a>戻り値

戻り値の完全な一覧については、Windows SDK の[「IOleCommandTarget::クエリステータス](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus)」を参照してください。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、[メソッド](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus)の機能をエミュレートします。

## <a name="coledocobjectitemrelease"></a><a name="release"></a>オブジェクト::リリース

OLE リンク アイテムへの接続を解放し、開いている場合は閉じます。 クライアント アイテムを破棄しません。

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
OLE アイテムが読み込まれた状態に戻ったときに、どのような状況で OLE アイテムが保存されるのかを指定するフラグ。 使用できる値の一覧については[、「COleClientItem::Close」を参照してください](../../mfc/reference/coleclientitem-class.md#close)。

### <a name="remarks"></a>解説

クライアント アイテムを破棄しません。

## <a name="see-also"></a>関連項目

[MFC サンプル MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)

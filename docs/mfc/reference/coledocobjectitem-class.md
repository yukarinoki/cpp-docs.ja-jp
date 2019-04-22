---
title: COleDocObjectItem クラス
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
ms.openlocfilehash: 382960b4dc4dcfa61c836a87044dd14585756174
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769648"
---
# <a name="coledocobjectitem-class"></a>COleDocObjectItem クラス

Active ドキュメント コンテインメントを実装します。

## <a name="syntax"></a>構文

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|構築、`COleDocObject`項目。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[:Dodefaultprinting](#dodefaultprinting)|既定のプリンター設定を使用して、コンテナー アプリケーションのドキュメントを印刷します。|
|[COleDocObjectItem::ExecCommand](#execcommand)|ユーザーによって指定されたコマンドを実行します。|
|[COleDocObjectItem::GetActiveView](#getactiveview)|ドキュメントのアクティブなビューを取得します。|
|[COleDocObjectItem::GetPageCount](#getpagecount)|コンテナー アプリケーションのドキュメントのページ数を取得します。|
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|印刷用のコンテナー アプリケーションのドキュメントを準備します。|
|[COleDocObjectItem::OnPrint](#onprint)|コンテナー アプリケーションのドキュメントを印刷します。|
|[COleDocObjectItem::QueryCommand](#querycommand)|ユーザー インターフェイスのイベントによって生成された 1 つ以上のコマンドの状態を調べるためにクエリを実行します。|
|[COleDocObjectItem::Release](#release)|OLE リンク アイテムへの接続を解放し、開いていた場合に終了します。 クライアントの項目を破棄しません。|

## <a name="remarks"></a>Remarks

Mfc では、アクティブ ドキュメントは、通常、一括編集可能な埋め込み、相違点を次に同様に処理します。

- `COleDocument`-派生クラスは、埋め込まれた現在の項目の一覧を引き続き維持。 ただし、これらの項目があります`COleDocObjectItem`-項目を派生します。

- アクティブ ドキュメントがアクティブな場合は、インプレース アクティブになったときに、ビューの全体のクライアント領域を占有します。

- Active ドキュメント コンテナーがのフル コントロール、**ヘルプ**メニュー。

- **ヘルプ**メニューには、Active ドキュメント コンテナーとサーバーの両方のメニュー項目が含まれています。

Active ドキュメント コンテナーが所有しているため、**ヘルプ**メニューで、コンテナーがサーバーに転送します**ヘルプ**サーバーへのメッセージのメニュー。 この統合はによって処理される`COleDocObjectItem`します。

メニューのマージとアクティブなドキュメントのアクティブ化する方法の詳細については、の概要を参照してください[Active ドキュメント コンテインメント](../../mfc/active-document-containment.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="coledocobjectitem"></a>  COleDocObjectItem::COleDocObjectItem

初期化するためにこのメンバー関数を呼び出す、`COleDocObjectItem`オブジェクト。

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>パラメーター

*pContainerDoc*<br/>
ポインター、 `COleDocument` active ドキュメント コンテナーとして機能するオブジェクト。 このパラメーターは、IMPLEMENT_SERIALIZE を有効にする NULL である必要があります。 通常、OLE アイテムは NULL でないドキュメント ポインターを使用して構築されます。

##  <a name="dodefaultprinting"></a>  COleDocObjectItem::DoDefaultPrinting

既定の設定を使用してドキュメントに、フレームワークによって呼び出されます。

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pCaller*<br/>
ポインターを[CView](../../mfc/reference/cview-class.md) print コマンドを送信しているオブジェクト。

*pInfo*<br/>
ポインターを[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)印刷ジョブを記述するオブジェクト。

##  <a name="execcommand"></a>  COleDocObjectItem::ExecCommand

ユーザーによって指定されたコマンドを実行するには、このメンバー関数を呼び出します。

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>パラメーター

*nCmdID*<br/>
実行するコマンドの識別子です。 識別されるグループである必要があります*pguidCmdGroup*します。

*nCmdExecOpt*<br/>
コマンドの実行オプションを指定します。 既定では、ユーザーに確認しないで、コマンドの実行に設定します。 参照してください[する](/windows/desktop/api/docobj/ne-docobj-olecmdexecopt)の値の一覧。

*pguidCmdGroup*<br/>
コマンド グループの一意の識別子。 既定で null の場合、標準のグループを指定します。 コマンドは、渡された*nCmdID*グループに属している必要があります。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返します。それ以外の場合、次のエラー コードのいずれかを返します。

|[値]|説明|
|-----------|-----------------|
|E_UNEXPECTED|予期しないエラーが発生しました。|
|E_FAIL|エラーが発生しました。|
|E_NOTIMPL|MFC を示す変換し、コマンドをディスパッチする自体しようとする必要があります。|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* NULL 以外ですが、認識されたコマンドのグループを指定できません。|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID*は有効なグループ pGroup コマンドとして認識されません。|
|OLECMDERR_DISABLED|によって識別されるコマンド*nCmdID*は無効になり、実行することはできません。|
|OLECMDERR_NOHELP|呼び出し元によって識別されるコマンドのヘルプについてよく寄せられる*nCmdID*が使用可能なヘルプはありません。|
|OLECMDERR_CANCELLED|ユーザーには、実行が取り消されました。|

### <a name="remarks"></a>Remarks

*PguidCmdGroup*と*nCmdID*パラメーターを一緒に呼び出すコマンドを一意に識別します。 *NCmdExecOpt*パラメーターを実行する正確なアクションを指定します。

##  <a name="getactiveview"></a>  COleDocObjectItem::GetActiveView

ポインターを取得するには、このメンバー関数を呼び出す、`IOleDocumentView`現在アクティブなビューのインターフェイス。

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>戻り値

ポインター、 [IOleDocumentView](/windows/desktop/api/docobj/nn-docobj-ioledocumentview)現在アクティブなビューのインターフェイス。 現在のビューがない場合は、NULL を返します。

### <a name="remarks"></a>Remarks

返された参照カウント`IOleDocumentView`ポインターは、この関数によって返される前に加算されません。

##  <a name="getpagecount"></a>  COleDocObjectItem::GetPageCount

ドキュメントのページの数を取得するには、このメンバー関数を呼び出します。

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>パラメーター

*pnFirstPage*<br/>
ドキュメントの最初のページの数へのポインター。 この番号は必要ありません、呼び出し元を示す、NULL を指定できます。

*pcPages*<br/>
ドキュメントのページの総数へのポインター。 この番号は必要ありません、呼び出し元を示す、NULL を指定できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="onprepareprinting"></a>  COleDocObjectItem::OnPreparePrinting

このメンバー関数は、ドキュメントを印刷に備えるためにフレームワークによって呼び出されます。

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>パラメーター

*pCaller*<br/>
ポインターを[CView](../../mfc/reference/cview-class.md) print コマンドを送信しているオブジェクト。

*pInfo*<br/>
ポインターを[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)印刷ジョブを記述するオブジェクト。

*bPrintAll*<br/>
ドキュメント全体を印刷するかどうかを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="onprint"></a>  COleDocObjectItem::OnPrint

このメンバー関数は、ドキュメントを印刷するためにフレームワークによって呼び出されます。

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>パラメーター

*pCaller*<br/>
印刷コマンドを送信する CView オブジェクトへのポインター。

*pInfo*<br/>
ポインターを[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)印刷ジョブを記述するオブジェクト。

*bPrintAll*<br/>
ドキュメント全体を印刷するかどうかを指定します。

##  <a name="querycommand"></a>  COleDocObjectItem::QueryCommand

ユーザー インターフェイスのイベントによって生成された 1 つ以上のコマンドの状態を調べるためにクエリを実行します。

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>パラメーター

*nCmdID*<br/>
照会するコマンドの識別子です。

*pdwStatus*<br/>
クエリの結果として返されるフラグへのポインター。 使用可能な値の一覧は、次を参照してください。 [OLECMDF](/windows/desktop/api/docobj/ne-docobj-olecmdf)します。

*pCmdText*<br/>
ポインター、 [OLECMDTEXT](/windows/desktop/api/docobj/ns-docobj-_tagolecmdtext)を 1 つのコマンドの名前と状態情報を返す対象の構造体。 呼び出し元がこの情報を必要としないことを示す NULL を指定できます。

*pguidCmdGroup*<br/>
コマンド グループの一意の識別子標準のグループを指定する NULL にすることができます。

### <a name="return-value"></a>戻り値

戻り値の完全な一覧については、次を参照してください。 [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus) Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

このメンバー関数の機能をエミュレートする、 [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus)メソッドを Windows SDK で説明します。

##  <a name="release"></a>  COleDocObjectItem::Release

OLE リンク アイテムへの接続を解放し、開いていた場合に終了します。 クライアントの項目を破棄しません。

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>パラメーター

*dwCloseOption*<br/>
読み込み済み状態に戻ったときにどのような状況で OLE 項目が保存されたを指定するフラグ。 使用可能な値の一覧は、次を参照してください。 [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close)します。

### <a name="remarks"></a>Remarks

クライアントの項目を破棄しません。

## <a name="see-also"></a>関連項目

[MFC サンプル MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)

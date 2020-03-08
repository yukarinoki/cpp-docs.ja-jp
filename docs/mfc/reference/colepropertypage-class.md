---
title: COlePropertyPage クラス
ms.date: 11/04/2016
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::OVERWRITEApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
helpviewer_keywords:
- COlePropertyPage [MFC], COlePropertyPage
- COlePropertyPage [MFC], GetControlStatus
- COlePropertyPage [MFC], GetObjectArray
- COlePropertyPage [MFC], GetPageSite
- COlePropertyPage [MFC], IgnoreApply
- COlePropertyPage [MFC], IsModified
- COlePropertyPage [MFC], OnEditProperty
- COlePropertyPage [MFC], OnHelp
- COlePropertyPage [MFC], OnInitDialog
- COlePropertyPage [MFC], OnObjectsChanged
- COlePropertyPage [MFC], OnSetPageSite
- COlePropertyPage [MFC], SetControlStatus
- COlePropertyPage [MFC], SetDialogResource
- COlePropertyPage [MFC], SetHelpInfo
- COlePropertyPage [MFC], SetModifiedFlag
- COlePropertyPage [MFC], SetPageName
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
ms.openlocfilehash: 8253b2c2fa6b93ec51c7ede983ef710eed039970
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865887"
---
# <a name="colepropertypage-class"></a>COlePropertyPage クラス

ダイアログ ボックスのようなグラフィカルなインターフェイスでカスタム コントロールのプロパティを表示します。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[COlePropertyPage:: COlePropertyPage](#colepropertypage)|`COlePropertyPage` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[COlePropertyPage:: GetControlStatus](#getcontrolstatus)|ユーザーがコントロールの値を変更したかどうかを示します。|
|[COlePropertyPage:: GetObjectArray](#getobjectarray)|プロパティページによって編集されているオブジェクトの配列を返します。|
|[COlePropertyPage:: Get Ite](#getpagesite)|プロパティページの `IPropertyPageSite` インターフェイスへのポインターを返します。|
|[COlePropertyPage:: IgnoreApply](#ignoreapply)|[適用] ボタンを有効にしないコントロールを決定します。|
|[COlePropertyPage:: IsModified](#ismodified)|ユーザーがプロパティページを変更したかどうかを示します。|
|[COlePropertyPage:: OnEditProperty](#oneditproperty)|ユーザーがプロパティを編集するときに、フレームワークによって呼び出されます。|
|[COlePropertyPage:: OnHelp](#onhelp)|ユーザーがヘルプを呼び出したときにフレームワークによって呼び出されます。|
|[COlePropertyPage:: OnInitDialog](#oninitdialog)|プロパティページが初期化されるときにフレームワークによって呼び出されます。|
|[COlePropertyPage:: On が変更されました](#onobjectschanged)|新しいプロパティを持つ別の OLE コントロールが選択されたときに、フレームワークによって呼び出されます。|
|[COlePropertyPage:: OnSetPageSite](#onsetpagesite)|プロパティフレームがページのサイトを提供するときに、フレームワークによって呼び出されます。|
|[COlePropertyPage:: SetControlStatus](#setcontrolstatus)|ユーザーがコントロールの値を変更したかどうかを示すフラグを設定します。|
|[COlePropertyPage:: Setのリソース](#setdialogresource)|プロパティページのダイアログリソースを設定します。|
|[COlePropertyPage:: SetHelpInfo](#sethelpinfo)|プロパティページの簡単なヘルプテキスト、ヘルプファイルの名前、およびヘルプコンテキストを設定します。|
|[COlePropertyPage:: SetModifiedFlag](#setmodifiedflag)|ユーザーがプロパティページを変更したかどうかを示すフラグを設定します。|
|[COlePropertyPage:: SetPageName](#setpagename)|プロパティページの名前 (キャプション) を設定します。|

## <a name="remarks"></a>解説

たとえば、プロパティページには、ユーザーがコントロールのキャプションプロパティを表示および変更できるようにするエディットコントロールを含めることができます。

各カスタムまたはストックコントロールのプロパティには、コントロールのユーザーが現在のプロパティ値を表示し、必要に応じてその値を変更できるダイアログコントロールを含めることができます。

`COlePropertyPage`の使用方法の詳細については、「 [ActiveX コントロール: プロパティページ](../../mfc/mfc-activex-controls-property-pages.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

##  <a name="colepropertypage"></a>COlePropertyPage:: COlePropertyPage

`COlePropertyPage` オブジェクトを構築します。

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>パラメーター

*idDlg*<br/>
ダイアログテンプレートのリソース ID。

*idCaption*<br/>
プロパティページのキャプションのリソース ID。

### <a name="remarks"></a>解説

`COlePropertyPage`のサブクラスを実装する場合、サブクラスのコンストラクターは、`COlePropertyPage` コンストラクターを使用して、プロパティページの基になるダイアログテンプレートリソースと、キャプションを含む文字列リソースを識別する必要があります。

##  <a name="getcontrolstatus"></a>COlePropertyPage:: GetControlStatus

ユーザーが、指定されたリソース ID を使用してプロパティページコントロールの値を変更したかどうかを判断します。

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
プロパティページコントロールのリソース ID。

### <a name="return-value"></a>戻り値

コントロールの値が変更された場合は TRUE。それ以外の場合は FALSE。

##  <a name="getobjectarray"></a>COlePropertyPage:: GetObjectArray

プロパティページによって編集されているオブジェクトの配列を返します。

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>パラメーター

*pnObjects*<br/>
ページによって編集されているオブジェクトの数を受け取る符号なし長整数へのポインター。

### <a name="return-value"></a>戻り値

プロパティページ上の各コントロールのプロパティにアクセスするために使用される `IDispatch` ポインターの配列へのポインター。 呼び出し元は、これらのインターフェイスポインターを解放しないでください。

### <a name="remarks"></a>解説

各プロパティページオブジェクトは、ページによって編集されているオブジェクトの `IDispatch` インターフェイスへのポインターの配列を保持します。 この関数は、その*Pnobjects*引数をその配列内の要素数に設定し、配列の最初の要素へのポインターを返します。

##  <a name="getpagesite"></a>COlePropertyPage:: Get Ite

プロパティページの `IPropertyPageSite` インターフェイスへのポインターを取得します。

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>戻り値

プロパティページの `IPropertyPageSite` インターフェイスへのポインター。

### <a name="remarks"></a>解説

コントロールとコンテナーを連携させることにより、ユーザーがコントロールのプロパティを参照および編集できるようにします。 コントロールには、プロパティページが用意されています。各ページは、ユーザーが関連する一連のプロパティを編集するための OLE オブジェクトです。 コンテナーには、プロパティページを表示するプロパティフレームが用意されています。 ページごとに、プロパティフレームには `IPropertyPageSite` インターフェイスをサポートするページサイトが用意されています。

##  <a name="ignoreapply"></a>COlePropertyPage:: IgnoreApply

[適用] ボタンを有効にしないコントロールを決定します。

```
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
無視するコントロールの ID。

### <a name="remarks"></a>解説

プロパティページの [適用] ボタンは、プロパティページコントロールの値が変更された場合にのみ有効になります。 値が変更されたときに [適用] ボタンが有効にならないようにするコントロールを指定するには、この関数を使用します。

##  <a name="ismodified"></a>COlePropertyPage:: IsModified

ユーザーがプロパティページの値を変更したかどうかを判断します。

```
BOOL IsModified();
```

### <a name="return-value"></a>戻り値

プロパティページが変更されている場合は TRUE。

##  <a name="oneditproperty"></a>COlePropertyPage:: OnEditProperty

フレームワークは、特定のプロパティを編集するときに、この関数を呼び出します。

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
編集中のプロパティのディスパッチ ID。

### <a name="return-value"></a>戻り値

既定の実装では、FALSE が返されます。 この関数をオーバーライドすると、TRUE が返されます。

### <a name="remarks"></a>解説

これをオーバーライドして、ページ上の適切なコントロールにフォーカスを設定することができます。 既定の実装では、何も実行されず、FALSE が返されます。

##  <a name="onhelp"></a>COlePropertyPage:: OnHelp

フレームワークは、ユーザーがオンラインヘルプを要求したときに、この関数を呼び出します。

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>パラメーター

*lpszHelpDir*<br/>
プロパティページのヘルプファイルが格納されているディレクトリ。

### <a name="return-value"></a>戻り値

既定の実装では、FALSE が返されます。

### <a name="remarks"></a>解説

ユーザーがヘルプにアクセスしたときに、プロパティページで特別なアクションを実行する必要がある場合はオーバーライドします。 既定の実装では何も行われず、FALSE が返されます。これは、WinHelp を呼び出すようにフレームワークに指示します。

##  <a name="oninitdialog"></a>COlePropertyPage:: OnInitDialog

フレームワークは、プロパティページのダイアログが初期化されるときに、この関数を呼び出します。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

既定の実装では、FALSE が返されます。

### <a name="remarks"></a>解説

ダイアログの初期化時に特別な操作が必要な場合はオーバーライドします。 既定の実装では `CDialog::OnInitDialog` が呼び出され、FALSE が返されます。

##  <a name="onobjectschanged"></a>COlePropertyPage:: On が変更されました

新しいプロパティを持つ別の OLE コントロールが選択されたときに、フレームワークによって呼び出されます。

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>解説

開発環境で OLE コントロールのプロパティを表示するときに、モードレスダイアログボックスを使用してプロパティページを表示します。 別のコントロールが選択されている場合は、プロパティの新しいセットに対して異なる一連のプロパティページを表示する必要があります。 フレームワークは、この関数を呼び出して、変更のプロパティページに通知します。

このアクションの通知を受信し、特別なアクションを実行するには、この関数をオーバーライドします。

##  <a name="onsetpagesite"></a>COlePropertyPage:: OnSetPageSite

プロパティフレームにプロパティページのページサイトが用意されている場合、フレームワークはこの関数を呼び出します。

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>解説

既定の実装は、ページのキャプションを読み込み、ダイアログリソースからページのサイズを決定しようとします。 プロパティページで追加のアクションが必要な場合は、この関数をオーバーライドします。オーバーライドでは、基本クラスの実装を呼び出す必要があります。

##  <a name="setcontrolstatus"></a>COlePropertyPage:: SetControlStatus

プロパティページコントロールの状態を変更します。

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
プロパティページコントロールの ID を格納します。

*bDirty*<br/>
プロパティページのフィールドが変更されたかどうかを示します。 フィールドが変更されている場合は TRUE に、変更されていない場合は FALSE に設定します。

### <a name="return-value"></a>戻り値

指定したコントロールが設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

プロパティページが閉じているとき、または [適用] ボタンを選択したときにプロパティページコントロールの状態がダーティの場合は、適切な値でコントロールのプロパティが更新されます。

##  <a name="setdialogresource"></a>COlePropertyPage:: Setのリソース

プロパティページのダイアログリソースを設定します。

```
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>パラメーター

*hDialog*<br/>
プロパティページのダイアログリソースへのハンドル。

##  <a name="sethelpinfo"></a>COlePropertyPage:: SetHelpInfo

プロパティページのツールヒント情報、ヘルプファイル名、およびヘルプコンテキストを指定します。

```
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>パラメーター

*lpszDocString*<br/>
ステータスバーまたはその他の場所に表示するための簡単なヘルプ情報を格納している文字列。

*lpszHelpFile*<br/>
プロパティページのヘルプファイルの名前。

*dwHelpContext*<br/>
プロパティページのヘルプコンテキスト。

##  <a name="setmodifiedflag"></a>COlePropertyPage:: SetModifiedFlag

ユーザーがプロパティページを変更したかどうかを示します。

```
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>パラメーター

*bModified*<br/>
プロパティページの変更後のフラグの新しい値を指定します。

##  <a name="setpagename"></a>COlePropertyPage:: SetPageName

プロパティページの名前を設定します。プロパティフレームは通常、ページのタブに表示されます。

```
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>パラメーター

*lpszPageName*<br/>
プロパティページの名前を含む文字列へのポインター。

## <a name="see-also"></a>参照

[MFC のサンプル CIRC3](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)

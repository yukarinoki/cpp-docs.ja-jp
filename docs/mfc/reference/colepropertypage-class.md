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
ms.openlocfilehash: dbdc889e244b33365756bcbae5b37cf657a6d900
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374874"
---
# <a name="colepropertypage-class"></a>COlePropertyPage クラス

ダイアログ ボックスのようなグラフィカルなインターフェイスでカスタム コントロールのプロパティを表示します。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティページ::プロパティページ](#colepropertypage)|`COlePropertyPage` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[プロパティページ::コントロールステータスを取得します。](#getcontrolstatus)|ユーザーがコントロールの値を変更したかどうかを示します。|
|[プロパティページ::オブジェクト配列を取得します。](#getobjectarray)|プロパティ ページで編集されているオブジェクトの配列を返します。|
|[プロパティページページ::ページサイトを取得します。](#getpagesite)|プロパティ ページの`IPropertyPageSite`インターフェイスへのポインターを返します。|
|[プロパティページ::無視適用](#ignoreapply)|[適用] ボタンを有効にしていないコントロールを決定します。|
|[プロパティページ::変更されました](#ismodified)|ユーザーがプロパティ ページを変更したかどうかを示します。|
|[プロパティページ::オンエディットプロパティ](#oneditproperty)|ユーザーがプロパティを編集するときに、フレームワークによって呼び出されます。|
|[プロパティページ::ヘルプ](#onhelp)|ユーザーがヘルプを呼び出すときに、フレームワークによって呼び出されます。|
|[プロパティページ::オンイニトダイアログ](#oninitdialog)|プロパティ ページが初期化されるときに、フレームワークによって呼び出されます。|
|[プロパティページ::オンオブジェクト変更](#onobjectschanged)|新しいプロパティを持つ別の OLE コントロールが選択されたときに、フレームワークによって呼び出されます。|
|[ページページページ::オンセットページサイト](#onsetpagesite)|プロパティ フレームがページのサイトを提供するときに、フレームワークによって呼び出されます。|
|[プロパティページ::コントロールステータスを設定します。](#setcontrolstatus)|ユーザーがコントロールの値を変更したかどうかを示すフラグを設定します。|
|[プロパティページ::リソースを設定します。](#setdialogresource)|プロパティ ページのダイアログ リソースを設定します。|
|[プロパティページ::ヘルプインフォ](#sethelpinfo)|プロパティ ページの簡単なヘルプ テキスト、ヘルプ ファイルの名前、およびヘルプ コンテキストを設定します。|
|[プロパティページ::セット修正フラグ](#setmodifiedflag)|ユーザーがプロパティ ページを変更したかどうかを示すフラグを設定します。|
|[ページ名を設定します。](#setpagename)|プロパティ ページの名前 (キャプション) を設定します。|

## <a name="remarks"></a>解説

たとえば、プロパティ ページには、ユーザーがコントロールの caption プロパティを表示および変更できる編集コントロールが含まれる場合があります。

各カスタム コントロール プロパティまたはストック コントロール プロパティには、コントロールのユーザーが現在のプロパティ値を表示し、必要に応じてその値を変更できるようにするダイアログ コントロールを設定できます。

の詳細`COlePropertyPage`については、「 [ActiveX コントロール : プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="colepropertypagecolepropertypage"></a><a name="colepropertypage"></a>プロパティページ::プロパティページ

`COlePropertyPage` オブジェクトを構築します。

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>パラメーター

*idDlg*<br/>
ダイアログ テンプレートのリソース ID。

*idキャプション*<br/>
プロパティ ページのキャプションのリソース ID。

### <a name="remarks"></a>解説

`COlePropertyPage`のサブクラスを実装する場合、サブクラスのコンストラクターは`COlePropertyPage`、プロパティ ページの基になるダイアログ テンプレート リソースとそのキャプションを含む文字列リソースを識別するために、コンストラクターを使用する必要があります。

## <a name="colepropertypagegetcontrolstatus"></a><a name="getcontrolstatus"></a>プロパティページ::コントロールステータスを取得します。

指定したリソース ID を使用して、プロパティ ページ コントロールの値を変更したかどうかを確認します。

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
プロパティ ページ コントロールのリソース ID。

### <a name="return-value"></a>戻り値

コントロール値が変更されている場合は TRUE。それ以外の場合は FALSE。

## <a name="colepropertypagegetobjectarray"></a><a name="getobjectarray"></a>プロパティページ::オブジェクト配列を取得します。

プロパティ ページで編集されているオブジェクトの配列を返します。

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
ページによって編集されているオブジェクトの数を受け取る符号なし長整数へのポインター。

### <a name="return-value"></a>戻り値

プロパティ ページの各`IDispatch`コントロールのプロパティにアクセスするために使用されるポインターの配列へのポインター。 呼び出し元は、これらのインターフェイス ポインターを解放できません。

### <a name="remarks"></a>解説

各プロパティ ページ オブジェクトは、ページによって編集される`IDispatch`オブジェクトのインターフェイスへのポインターの配列を保持します。 この関数は、その配列内の要素の数に *、その pnObjects*引数を設定し、配列の最初の要素へのポインターを返します。

## <a name="colepropertypagegetpagesite"></a><a name="getpagesite"></a>プロパティページページ::ページサイトを取得します。

プロパティ ページの`IPropertyPageSite`インターフェイスへのポインターを取得します。

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>戻り値

プロパティ ページの`IPropertyPageSite`インターフェイスへのポインター。

### <a name="remarks"></a>解説

コントロールとコンテナーが連携して、ユーザーがコントロールのプロパティを参照および編集できるようにします。 このコントロールにはプロパティ ページが用意されており、各プロパティ ページは OLE オブジェクトであり、ユーザーは関連するプロパティセットを編集できます。 コンテナーには、プロパティ ページを表示するプロパティ フレームが用意されています。 各ページに対して、プロパティ フレームは、インターフェイスをサポートする`IPropertyPageSite`ページ サイトを提供します。

## <a name="colepropertypageignoreapply"></a><a name="ignoreapply"></a>プロパティページ::無視適用

[適用] ボタンを有効にしていないコントロールを決定します。

```
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
無視するコントロールの ID。

### <a name="remarks"></a>解説

プロパティ ページの [適用] ボタンは、プロパティ ページ コントロールの値が変更された場合にのみ有効になります。 この関数を使用して、値が変更されたときに [適用] ボタンを有効にしないコントロールを指定します。

## <a name="colepropertypageismodified"></a><a name="ismodified"></a>プロパティページ::変更されました

ユーザーがプロパティ ページの値を変更したかどうかを判断します。

```
BOOL IsModified();
```

### <a name="return-value"></a>戻り値

プロパティ ページが変更されている場合は TRUE。

## <a name="colepropertypageoneditproperty"></a><a name="oneditproperty"></a>プロパティページ::オンエディットプロパティ

フレームワークは、特定のプロパティを編集するときにこの関数を呼び出します。

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
編集中のプロパティのディスパッチ ID。

### <a name="return-value"></a>戻り値

既定の実装では FALSE が返されます。 この関数のオーバーライドは TRUE を返す必要があります。

### <a name="remarks"></a>解説

このコントロールをオーバーライドして、フォーカスをページ上の適切なコントロールに設定できます。 既定の実装では何も行われなくて、FALSE が返されます。

## <a name="colepropertypageonhelp"></a><a name="onhelp"></a>プロパティページ::ヘルプ

ユーザーがオンライン ヘルプを要求すると、フレームワークはこの関数を呼び出します。

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
プロパティ ページのヘルプ ファイルを含むディレクトリ。

### <a name="return-value"></a>戻り値

既定の実装では FALSE が返されます。

### <a name="remarks"></a>解説

ユーザーがヘルプにアクセスするときにプロパティ ページで特別な操作を実行する必要がある場合は、このプロパティをオーバーライドします。 既定の実装では何も実行されず、False が返され、WinHelp を呼び出すフレームワークに指示されます。

## <a name="colepropertypageoninitdialog"></a><a name="oninitdialog"></a>プロパティページ::オンイニトダイアログ

フレームワークは、プロパティ ページのダイアログが初期化されるときに、この関数を呼び出します。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

既定の実装では FALSE が返されます。

### <a name="remarks"></a>解説

ダイアログの初期化時に特別なアクションが必要な場合は、このオプションをオーバーライドします。 既定の実装は`CDialog::OnInitDialog`、FALSE を呼び出して返します。

## <a name="colepropertypageonobjectschanged"></a><a name="onobjectschanged"></a>プロパティページ::オンオブジェクト変更

新しいプロパティを持つ別の OLE コントロールが選択されたときに、フレームワークによって呼び出されます。

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>解説

開発環境で OLE コントロールのプロパティを表示する場合、モードレス ダイアログ ボックスを使用してプロパティ ページが表示されます。 別のコントロールを選択した場合は、新しいプロパティ セットに対して、異なるプロパティ ページのセットを表示する必要があります。 フレームワークは、この関数を呼び出して、プロパティ ページに変更を通知します。

このアクションの通知を受け取り、特別なアクションを実行するには、この関数をオーバーライドします。

## <a name="colepropertypageonsetpagesite"></a><a name="onsetpagesite"></a>ページページページ::オンセットページサイト

プロパティ フレームがプロパティ ページのページ サイトを提供するときに、フレームワークはこの関数を呼び出します。

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>解説

既定の実装では、ページのキャプションを読み込み、ダイアログ リソースからページのサイズを決定しようとします。 プロパティ ページに追加のアクションが必要な場合は、この関数をオーバーライドします。オーバーライドは、基本クラスの実装を呼び出す必要があります。

## <a name="colepropertypagesetcontrolstatus"></a><a name="setcontrolstatus"></a>プロパティページ::コントロールステータスを設定します。

プロパティ ページ コントロールの状態を変更します。

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
プロパティ ページ コントロールの ID を格納します。

*bダーティ*<br/>
プロパティ ページのフィールドが変更されたかどうかを指定します。 フィールドが変更されている場合は TRUE に設定し、変更されていない場合は FALSE に設定します。

### <a name="return-value"></a>戻り値

指定したコントロールが設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

プロパティ ページが閉じているか、[適用] ボタンが選択されているときにプロパティ ページ コントロールの状態がダーティである場合、コントロールのプロパティは適切な値で更新されます。

## <a name="colepropertypagesetdialogresource"></a><a name="setdialogresource"></a>プロパティページ::リソースを設定します。

プロパティ ページのダイアログ リソースを設定します。

```
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>パラメーター

*hダイアログ*<br/>
プロパティ ページのダイアログ リソースへのハンドル。

## <a name="colepropertypagesethelpinfo"></a><a name="sethelpinfo"></a>プロパティページ::ヘルプインフォ

プロパティ ページのツールヒント情報、ヘルプ ファイル名、およびヘルプ コンテキストを指定します。

```
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
ステータス バーまたはその他の場所に表示する簡単なヘルプ情報を含む文字列。

*ファイル*<br/>
プロパティ ページのヘルプ ファイルの名前。

*コンテキスト*<br/>
プロパティ ページのヘルプ コンテキスト。

## <a name="colepropertypagesetmodifiedflag"></a><a name="setmodifiedflag"></a>プロパティページ::セット修正フラグ

ユーザーがプロパティ ページを変更したかどうかを示します。

```
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>パラメーター

*bModified*<br/>
プロパティ ページの変更済みフラグの新しい値を指定します。

## <a name="colepropertypagesetpagename"></a><a name="setpagename"></a>ページ名を設定します。

プロパティ フレームが通常ページのタブに表示されるプロパティ ページの名前を設定します。

```
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>パラメーター

*ページ名*<br/>
プロパティ ページの名前を含む文字列へのポインター。

## <a name="see-also"></a>関連項目

[MFC サンプル CIRC3](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル テストヘルプ](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)

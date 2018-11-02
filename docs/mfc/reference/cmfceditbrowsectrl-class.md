---
title: CMFCEditBrowseCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
ms.openlocfilehash: a16d7508f273fc444be65c1e6cc176911fd28e03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643301"
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl クラス

`CMFCEditBrowseCtrl`クラスは、必要に応じて、[参照] ボタンを格納する編集可能なテキスト ボックスには、編集参照コントロールをサポートしています。 ユーザーが参照ボタンをクリックすると、このコントロールはカスタム動作を実行するか、ファイル参照またはフォルダー参照を含む標準ダイアログ ボックスを表示します。

## <a name="syntax"></a>構文

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|既定のコンストラクター|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[:Enablebrowsebutton](#enablebrowsebutton)|有効または (非表示にします) を無効に、[参照] ボタンをクリックします。|
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|[参照] ボタンを有効し、参照機能付きコントロールを*ファイル参照*モード。|
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|[参照] ボタンを有効し、参照機能付きコントロールを*フォルダーの参照*モード。|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|現在のブラウズ モードを返します。|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|参照操作の結果を参照機能付きコントロールが更新された後に、フレームワークによって呼び出されます。|
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|ユーザーが [参照] ボタンをクリックした後に、フレームワークによって呼び出されます。|
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|現在の参照機能付きコントロールを再描画します。|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|[参照] ボタンを描画するためにフレームワークによって呼び出されます。|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|編集コントロールに、無効なファイル名が入力されたときに、フレームワークによって呼び出されます。|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数。 構文と詳細については、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)します。|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|[参照] ボタンのカスタム イメージを設定します。|

## <a name="remarks"></a>Remarks

参照機能付きコントロールを使用すると、ファイルまたはフォルダーの名前を選択します。 必要に応じて、ダイアログ ボックスを表示するのにようにカスタム アクションを実行するのにコントロールを使用します。 表示したり、参照 ボタンが表示されないと ボタンをカスタムのラベルやイメージを適用することができます。

*ブラウズ モード*参照ボタンを表示するかどうかと、どのようなアクションは、ボタンがクリックされたときに発生します。 参照機能付きのコントロールを決定します。 詳細については、次を参照してください。、 [GetMode](#getmode)メソッド。

`CMFCEditBrowseCtrl`クラスは、次のモードをサポートします。

- **カスタム モード**

   [参照] ボタンをクリックすると、カスタム アクションが実行されます。 たとえば、アプリケーション固有のダイアログを表示できます。

- **ファイル モード**

   参照 ボタンをクリックすると、標準のファイルの選択 ダイアログ ボックスが表示されます。

- **フォルダー モード**

   参照 ボタンをクリックすると、標準のフォルダーの選択 ダイアログ ボックスが表示されます。

## <a name="how-to-specify-an-edit-browse-control"></a>方法: 参照機能付きコントロールを指定します。

アプリケーションの参照機能付きコントロールを組み込むには、次の手順に従います。

1. カスタムのブラウズ モードを実装する場合は、派生クラスから独自のクラス、`CMFCEditBrowseCtrl`クラスをオーバーライドして、 [CMFCEditBrowseCtrl::OnBrowse](#onbrowse)メソッド。 オーバーライドされたメソッドでは、カスタム参照アクションを実行し、結果で、参照機能付きコントロールを更新します。

1. いずれかを埋め込み、`CMFCEditBrowseCtrl`オブジェクトまたは親ウィンドウのオブジェクトには、派生編集参照コントロール オブジェクト。

1. 使用する場合、**クラス ウィザード** ダイアログ ボックスを作成するには、エディット コントロールを追加 ( `CEdit`) ダイアログ ボックスのフォームにします。 また、ヘッダー ファイル内のコントロールにアクセスする変数を追加します。 変数の型を変更すると、ヘッダー ファイルで`CEdit`に`CMFCEditBrowseCtrl`します。 参照機能付きコントロールが自動的に作成されます。 使用しない場合、**クラス ウィザード**、追加、`CMFCEditBrowseCtrl`変数を呼び出して、ヘッダー ファイルにその`Create`メソッド。

1. ダイアログ ボックスに、参照機能付きコントロールを追加する場合は、使用、 **ClassWizard**データ交換を設定するためのツール。

1. 呼び出す、 [EnableFolderBrowseButton](#enablefolderbrowsebutton)、 [EnableFileBrowseButton](#enablefilebrowsebutton)、または[EnableBrowseButton](#enablebrowsebutton)ブラウズ モードを設定し、[参照] ボタンを表示するメソッド。 呼び出す、 [GetMode](#getmode)現在ブラウズ モードを取得します。

1. [参照] ボタンをカスタム イメージを提供するには、呼び出し、 [SetBrowseButtonImage](#setbrowsebuttonimage)メソッドやオーバーライド、 [OnDrawBrowseButton](#ondrawbrowsebutton)メソッド。

1. 参照機能付きコントロールから、[参照] ボタンを削除するには、呼び出し、 [EnableBrowseButton](#enablebrowsebutton)メソッドを*bEnable*パラメーターが FALSE に設定します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>例

次の例では、2 つのメソッドを使用する方法、`CMFCEditBrowseCtrl`クラス:`EnableFolderBrowseButton`と`EnableFileBrowseButton`します。 この例は、[新しいコントロール サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxeditbrowsectrl.h

##  <a name="enablebrowsebutton"></a>  :Enablebrowsebutton

表示または現在の参照機能付きコントロールでは、参照ボタンは表示されません。

```
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[参照] ボタンを表示する場合は TRUE参照ボタンを表示しない場合は FALSE。 既定値は TRUE です。

*szLabel*<br/>
[参照] ボタンに表示されるラベルです。 既定値は" **.**".

### <a name="remarks"></a>Remarks

場合、 *bEnable*パラメーターが TRUE で、[参照] ボタンがクリックされたときに実行するカスタム アクションを実装します。 カスタム アクションを実装する派生クラスを`CMFCEditBrowseCtrl`クラスをオーバーライドし、その[OnBrowse](#onbrowse)メソッド。

場合、 *bEnable*パラメーターが TRUE で、コントロールのブラウズ モードは`BrowseMode_Default`、それ以外のブラウズ モードは`BrowseMode_None`します。 ブラウズ モードの詳細については、次を参照してください。、 [GetMode](#getmode)メソッド。

##  <a name="enablefilebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFileBrowseButton

現在の参照機能付きコントロールで参照ボタンを表示し、コントロールを*ファイル参照*モード。

```
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>パラメーター

*lpszDefExt*<br/>
[ファイルの選択] ダイアログ ボックスで使用する既定のファイル名拡張子を指定します。 既定値は、NULL です。

*lpszFilter*<br/>
[ファイルの選択] ダイアログ ボックスで使用する既定のフィルター文字列を指定します。 既定値は、NULL です。

*dwFlags*<br/>
ダイアログ ボックスのフラグ。 既定値は OFN_HIDEREADONLY と OFN_OVERWRITEPROMPT のビットごとの組み合わせ (OR) です。

### <a name="remarks"></a>Remarks

参照機能付きコントロールがファイル参照モードのときにユーザーが [参照] ボタンをクリックすると、コントロールに標準的なファイル選択のダイアログ ボックスが表示されます。

使用可能なフラグの一覧については、次を参照してください。 [OPENFILENAME 構造体](/windows/desktop/api/commdlg/ns-commdlg-tagofna)します。

##  <a name="enablefolderbrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFolderBrowseButton

現在の参照機能付きコントロールで参照ボタンを表示し、コントロールを*フォルダーの参照*モード。

```
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Remarks

参照機能付きコントロールは、フォルダーのブラウズ モードでは、ユーザーが 参照 ボタンをクリックして、コントロールには、標準のフォルダーの選択 ダイアログ ボックスが表示されます。

##  <a name="getmode"></a>  CMFCEditBrowseCtrl::GetMode

現在の参照機能付きコントロールのブラウズ モードを取得します。

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>戻り値

現在編集モードを指定する列挙値の 1 つは、コントロールを参照します。 ブラウズ モードでは、フレームワークが、参照ボタンを表示するかどうかと、ユーザーがそのボタンをクリックしたときに発生する動作を決定します。

次の表は、可能性のある戻り値の一覧です。

|[値]|説明|
|-----------|-----------------|
|`BrowseMode_Default`|**カスタム モード**します。 プログラマが定義したアクションが実行されます。|
|`BrowseMode_File`|**ファイル モード**します。 標準的なファイル ブラウザー ダイアログ ボックスが表示されます。|
|`BrowseMode_Folder`|**フォルダー モード**します。 標準的なフォルダーの参照 ダイアログ ボックスが表示されます。|
|`BrowseMode_None`|[参照] ボタンは表示されません。|

### <a name="remarks"></a>Remarks

既定で、`CMFCEditBrowseCtrl`オブジェクトが初期化`BrowseMode_None`モード。 ブラウズ モードでの変更、 [:enablebrowsebutton](#enablebrowsebutton)、 [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)、および[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)メソッド。

##  <a name="onafterupdate"></a>  CMFCEditBrowseCtrl::OnAfterUpdate

参照操作の結果を参照機能付きコントロールが更新された後に、フレームワークによって呼び出されます。

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Remarks

カスタム アクションを実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="onbrowse"></a>  CMFCEditBrowseCtrl::OnBrowse

ユーザーが、参照機能付きコントロールの [参照] ボタンをクリックした後に、フレームワークによって呼び出されます。

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Remarks

参照機能付きコントロールの [参照] ボタンをクリックすると、カスタム コードを実行するのにには、このメソッドを使用します。 クラスを派生、`CMFCEditBrowseCtrl`クラスし、オーバーライドの`OnBrowse`メソッド。 メソッドには、カスタム参照アクションを実装し、必要に応じて、参照機能付きコントロールのテキスト ボックスを更新します。 アプリケーションでは、使用、 [EnableBrowseButton](#enablebrowsebutton)メソッドに、参照機能付きコントロールを配置する*カスタム参照*モード。

##  <a name="onchangelayout"></a>  CMFCEditBrowseCtrl::OnChangeLayout

現在の参照機能付きコントロールを再描画します。

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Remarks

フレームワークは、ブラウズ モードの参照機能付きコントロール変更されるときに、このメソッドを呼び出します。 詳細については、次を参照してください。 [CMFCEditBrowseCtrl::GetMode](#getmode)します。

##  <a name="ondrawbrowsebutton"></a>  CMFCEditBrowseCtrl::OnDrawBrowseButton

参照機能付きコントロールの [参照] ボタンを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストへのポインター。

*rect*<br/>
[参照] ボタンの外接する四角形。

*bIsButtonPressed*<br/>
ボタンが押された; は、TRUE を返します。それ以外の場合、FALSE です。

*bIsButtonHot*<br/>
TRUE の場合は、ボタンが強調表示されます。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

[参照] ボタンの外観をカスタマイズする派生クラスでは、この関数をオーバーライドします。

##  <a name="setbrowsebuttonimage"></a>  CMFCEditBrowseCtrl::SetBrowseButtonImage

参照機能付きコントロールの [参照] ボタンをカスタム イメージを設定します。

```
void SetBrowseButtonImage(
    HICON hIcon,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(UINT uiBmpResId);
```

### <a name="parameters"></a>パラメーター

*hIcon*<br/>
アイコンのハンドル。

*hBitmap*<br/>
ビットマップのハンドル。

*uiBmpResId*<br/>
ビットマップのリソース ID。

*bAutoDestroy*<br/>
このメソッドが終了し、指定されたアイコンまたはビットマップを削除する場合は TRUEそれ以外の場合、FALSE です。 既定値は TRUE です。

### <a name="remarks"></a>Remarks

[参照] ボタンにカスタム イメージを適用するのにには、このメソッドを使用します。 参照機能付きコントロールがいる際に既定では、フレームワークが標準的なイメージを取得*ファイル参照*または*フォルダーの参照*モード。

##  <a name="onillegalfilename"></a>  CMFCEditBrowseCtrl::OnIllegalFileName

編集コントロールに、無効なファイル名が入力されたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>パラメーター

*strFileName*<br/>
無効なファイル名を指定します。

### <a name="return-value"></a>戻り値

このファイル名は、さらに、ファイル ダイアログは渡されない場合、FALSE を返す必要があります。 この場合、エディット コントロールにフォーカスが戻ります設定し、ユーザーが編集を続行する必要があります。 既定の実装では、について無効なファイル名を示すメッセージ ボックスを表示し、FALSE を返します。 このメソッドをオーバーライドできます、ファイル名を修正し、さらに処理するために TRUE を返します。

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)

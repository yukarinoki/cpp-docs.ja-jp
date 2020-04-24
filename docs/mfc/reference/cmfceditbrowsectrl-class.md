---
title: クラス
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
ms.openlocfilehash: d542af4a87b6f0a33c0344d1d3da76980f8c1a91
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752380"
---
# <a name="cmfceditbrowsectrl-class"></a>クラス

クラス`CMFCEditBrowseCtrl`は、必要に応じて参照ボタンを含む編集可能なテキスト ボックスである編集参照コントロールをサポートします。 ユーザーが参照ボタンをクリックすると、このコントロールはカスタム動作を実行するか、ファイル参照またはフォルダー参照を含む標準ダイアログ ボックスを表示します。

## <a name="syntax"></a>構文

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|既定のコンストラクターです。|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ボタンをクリックします。](#enablebrowsebutton)|参照ボタンを有効または無効にします (非表示にします)。|
|[ファイルの参照ボタンを有効にします。](#enablefilebrowsebutton)|参照ボタンを有効にし、ファイル*ブラウズモードで*ブラウズコントロールを編集します。|
|[ウィンドウの選択ボタン](#enablefolderbrowsebutton)|参照ボタンを有効にし、*フォルダーの参照*モードに編集の参照コントロールを配置します。|
|[次の項目を取得します。](#getmode)|現在のブラウズ モードを返します。|
|[次の更新を行います。](#onafterupdate)|参照操作の結果を使用して編集参照コントロールが更新された後に、フレームワークによって呼び出されます。|
|[ウィンドウズブラウズCtrl::オンブラウズ](#onbrowse)|ユーザーが参照ボタンをクリックした後に、フレームワークによって呼び出されます。|
|[ウィンドウズレイアウト](#onchangelayout)|現在の編集参照コントロールを再描画します。|
|[ボタン](#ondrawbrowsebutton)|参照ボタンを描画するために、フレームワークによって呼び出されます。|
|[ファイル名::無効なファイル名](#onillegalfilename)|編集コントロールに無効なファイル名が入力されたときに、フレームワークによって呼び出されます。|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 構文と詳細については[、「CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)」を参照してください。|
|[イメージを編集します。](#setbrowsebuttonimage)|参照ボタンのカスタム イメージを設定します。|

## <a name="remarks"></a>解説

ファイルまたはフォルダー名を選択するには、参照コントロールを編集します。 必要に応じて、コントロールを使用して、ダイアログ ボックスを表示するなどのカスタムアクションを実行します。 参照ボタンを表示または表示しない場合、ボタンにカスタム ラベルまたはイメージを適用できます。

参照コントロールの*ブラウズ モード*によって、参照ボタンを表示するかどうか、およびボタンがクリックされたときに実行されるアクションが決まります。 詳細については[、GetMode](#getmode)メソッドを参照してください。

この`CMFCEditBrowseCtrl`クラスは、次のモードをサポートします。

- **カスタム モード**

   ユーザーが参照ボタンをクリックすると、カスタムアクションが実行されます。 たとえば、アプリケーション固有のダイアログ ボックスを表示できます。

- **ファイル モード**

   ユーザーが参照ボタンをクリックすると、標準のファイル選択ダイアログボックスが表示されます。

- **フォルダ モード**

   ユーザーが参照ボタンをクリックすると、標準のフォルダ選択ダイアログボックスが表示されます。

## <a name="how-to-specify-an-edit-browse-control"></a>方法: 参照コントロールの編集を指定する

アプリケーションに編集参照コントロールを組み込むには、次の手順を実行します。

1. カスタム ブラウズ モードを実装する場合は、クラスから独自のクラス`CMFCEditBrowseCtrl`を派生し、[メソッド](#onbrowse)をオーバーライドします。 オーバーライドされたメソッドで、カスタムの参照アクションを実行し、結果に編集参照コントロールを更新します。

1. `CMFCEditBrowseCtrl`オブジェクトまたは派生編集参照コントロール オブジェクトを親ウィンドウ オブジェクトに埋め込みます。

1. **クラス ウィザード**を使用してダイアログ ボックスを作成する場合は、ダイアログ`CEdit`ボックス フォームにエディット コントロール ( ) を追加します。 また、ヘッダー ファイルのコントロールにアクセスする変数を追加します。 ヘッダー ファイルで、変数の型を から`CEdit`に`CMFCEditBrowseCtrl`変更します。 参照コントロールの編集は自動的に作成されます。 **クラス ウィザード**を使用しない場合は、ヘッダー`CMFCEditBrowseCtrl`ファイルに変数を追加し、そのメソッド`Create`を呼び出します。

1. ダイアログ ボックスに編集参照コントロールを追加する場合は **、ClassWizard**ツールを使用してデータ交換を設定します。

1. ブラウズ[モードを設定](#enablefolderbrowsebutton)[し、参照](#enablefilebrowsebutton)ボタンを表示するには、[メソッドを](#enablebrowsebutton)呼び出します。 [GetMode](#getmode)メソッドを呼び出して、現在のブラウズ モードを取得します。

1. 参照ボタンのカスタム イメージを提供するには[、メソッドを](#setbrowsebuttonimage)呼び出すか、メソッドをオーバーライド[します](#ondrawbrowsebutton)。

1. 参照の編集コントロールから参照ボタンを削除するには *、bEnable*パラメーターを FALSE に設定して[EnableBrowseButton](#enablebrowsebutton)メソッドを呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>例

次の例は、クラスで 2 つのメソッド`CMFCEditBrowseCtrl`を使用`EnableFolderBrowseButton`する`EnableFileBrowseButton`方法を示しています。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxeditbrowsectrl.h

## <a name="cmfceditbrowsectrlenablebrowsebutton"></a><a name="enablebrowsebutton"></a>ボタンをクリックします。

現在の編集参照コントロールの参照ボタンを表示または表示しません。

```cpp
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
参照ボタンを表示する場合は TRUE。[参照] ボタンを表示しない場合は FALSE。 既定値は TRUE です。

*szラベル*<br/>
参照ボタンに表示されるラベル。 既定値は **"..."** です。

### <a name="remarks"></a>解説

*bEnable*パラメーターが TRUE の場合は、参照ボタンがクリックされたときに実行するカスタム アクションを実装します。 カスタム アクションを実装するには、クラスからクラスを`CMFCEditBrowseCtrl`派生させ、その[OnBrowse](#onbrowse)メソッドをオーバーライドします。

*bEnable*パラメーターが TRUE の場合、コントロールのブラウズ`BrowseMode_Default`モードは;それ以外の場合、ブラウズ`BrowseMode_None`モードは です。 ブラウズ モードの詳細については[、GetMode](#getmode)メソッドを参照してください。

## <a name="cmfceditbrowsectrlenablefilebrowsebutton"></a><a name="enablefilebrowsebutton"></a>ファイルの参照ボタンを有効にします。

現在の編集参照コントロールの参照ボタンを表示し、*コントロールをファイル ブラウズ*モードにします。

```cpp
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
[ファイルの選択] ダイアログ ボックスで使用する既定のファイル名拡張子を指定します。 既定値は NULL です。

*Lpszfilter*<br/>
[ファイルの選択] ダイアログ ボックスで使用する既定のフィルター文字列を指定します。 既定値は NULL です。

*dwFlags*<br/>
ダイアログ ボックスのフラグ。 既定値は OFN_HIDEREADONLY と OFN_OVERWRITEPROMPT のビットごとの組み合わせ (OR) です。

### <a name="remarks"></a>解説

参照機能付きコントロールがファイル参照モードのときにユーザーが [参照] ボタンをクリックすると、コントロールに標準的なファイル選択のダイアログ ボックスが表示されます。

使用可能なフラグの完全なリストについては[、OPENFILENAME 構造体](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)を参照してください。

## <a name="cmfceditbrowsectrlenablefolderbrowsebutton"></a><a name="enablefolderbrowsebutton"></a>ウィンドウの選択ボタン

現在の編集参照コントロールの参照ボタンを表示し、*コントロールをフォルダ ブラウズ*モードにします。

```cpp
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>解説

ブラウズ コントロールの編集がフォルダ ブラウズ モードで、ユーザーが参照ボタンをクリックすると、標準のフォルダ選択ダイアログ ボックスが表示されます。

## <a name="cmfceditbrowsectrlgetmode"></a><a name="getmode"></a>次の項目を取得します。

現在の編集参照コントロールのブラウズ モードを取得します。

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>戻り値

編集参照コントロールの現在のモードを指定する列挙値の 1 つ。 ブラウズ モードは、フレームワークが参照ボタンを表示するかどうか、およびユーザーがそのボタンをクリックしたときに発生するアクションを決定します。

次の表は、可能性のある戻り値の一覧です。

|値|説明|
|-----------|-----------------|
|`BrowseMode_Default`|**カスタム モード**。 プログラマー定義のアクションが実行されます。|
|`BrowseMode_File`|**ファイル モード**。 標準のファイル ブラウザ ダイアログ ボックスが表示されます。|
|`BrowseMode_Folder`|**フォルダ モード**: 標準のフォルダ ブラウザ ダイアログ ボックスが表示されます。|
|`BrowseMode_None`|参照ボタンは表示されません。|

### <a name="remarks"></a>解説

デフォルトでは、`CMFCEditBrowseCtrl`オブジェクトはモードに`BrowseMode_None`初期化されます。 ブラウズ モードを変更[します](#enablebrowsebutton)。 [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton) [CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)

## <a name="cmfceditbrowsectrlonafterupdate"></a><a name="onafterupdate"></a>次の更新を行います。

参照操作の結果を使用して編集参照コントロールが更新された後に、フレームワークによって呼び出されます。

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>解説

カスタム アクションを実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfceditbrowsectrlonbrowse"></a><a name="onbrowse"></a>ウィンドウズブラウズCtrl::オンブラウズ

ユーザーが参照の編集コントロールの参照ボタンをクリックした後に、フレームワークによって呼び出されます。

```
virtual void OnBrowse();
```

### <a name="remarks"></a>解説

このメソッドは、ユーザーが参照コントロールの参照ボタンをクリックしたときにカスタム コードを実行するために使います。 クラスから独自のクラスを`CMFCEditBrowseCtrl`派生させ、その`OnBrowse`メソッドをオーバーライドします。 このメソッドでは、カスタムの参照動作を実装し、必要に応じて、参照コントロールの編集のテキスト ボックスを更新します。 アプリケーションで[、EnableBrowseButton](#enablebrowsebutton)メソッドを使用して、*カスタム*ブラウズ モードでの編集参照コントロールを配置します。

## <a name="cmfceditbrowsectrlonchangelayout"></a><a name="onchangelayout"></a>ウィンドウズレイアウト

現在の編集参照コントロールを再描画します。

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>解説

フレームワークは、編集参照コントロールのブラウズ モードが変更されたときに、このメソッドを呼び出します。 詳細については[、「CMFC 編集モードCtrl::GetMode](#getmode)」を参照してください。

## <a name="cmfceditbrowsectrlondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>ボタン

編集参照コントロールに参照ボタンを描画するために、フレームワークによって呼び出されます。

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

*Rect*<br/>
参照ボタンの外接する四角形。

*ビズボタン押下*<br/>
ボタンが押された場合は TRUE。それ以外の場合は FALSE。

*ビスボタンホット*<br/>
ボタンが強調表示されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

参照ボタンの外観をカスタマイズするには、派生クラスでこの関数をオーバーライドします。

## <a name="cmfceditbrowsectrlsetbrowsebuttonimage"></a><a name="setbrowsebuttonimage"></a>イメージを編集します。

参照コントロールの参照ボタンにカスタム イメージを設定します。

```cpp
void SetBrowseButtonImage(
    HICON hIcon,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(UINT uiBmpResId);
```

### <a name="parameters"></a>パラメーター

*Hicon*<br/>
アイコンのハンドル。

*hビットマップ*<br/>
ビットマップのハンドル。

*をクリックします。*<br/>
ビットマップのリソース ID。

*b自動破壊*<br/>
このメソッドが終了したときに指定されたアイコンまたはビットマップを削除する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

このメソッドは、参照ボタンにカスタム イメージを適用するために使います。 既定では、編集の参照コントロールが*ファイルの参照*モードまたは*フォルダーの参照*モードである場合、フレームワークは標準イメージを取得します。

## <a name="cmfceditbrowsectrlonillegalfilename"></a><a name="onillegalfilename"></a>ファイル名::無効なファイル名

編集コントロールに無効なファイル名が入力されたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
不正なファイル名を指定します。

### <a name="return-value"></a>戻り値

このファイル名をファイル ダイアログに渡す必要がある場合は、FALSE を返す必要があります。 この場合、フォーカスはエディット コントロールに戻され、ユーザーは編集を続行する必要があります。 既定の実装では、不正なファイル名をユーザーに知らせるメッセージ ボックスが表示され、FALSE が返されます。 このメソッドをオーバーライドしてファイル名を修正し、さらに処理するために TRUE を返すことができます。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)

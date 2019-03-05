---
title: CTaskDialog Class
ms.date: 11/19/2018
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
helpviewer_keywords:
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
ms.openlocfilehash: 04c8a60f546700be8eeb2ec8a948e0ea321d12f8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265016"
---
# <a name="ctaskdialog-class"></a>CTaskDialog Class

メッセージ ボックスのような機能を持つだけでなく、ユーザーに対する追加情報も表示できる、ポップアップ ダイアログ ボックスです。 `CTaskDialog` には、ユーザーから情報を収集するための機能も用意されています。

## <a name="syntax"></a>構文

```
class CTaskDialog : public CObject
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|||
|-|-|
|[CTaskDialog::CTaskDialog](#ctaskdialog)|`CTaskDialog` オブジェクトを構築します。|

### <a name="methods"></a>メソッド

|||
|-|-|
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|コマンド ボタン コントロールを追加、`CTaskDialog`します。|
|[CTaskDialog::AddRadioButton](#addradiobutton)|ラジオ ボタンを追加、`CTaskDialog`します。|
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|プログラムで、コマンド ボタンのコントロールや一般的なボタンをクリックします。|
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|プログラムでオプション ボタンをクリックします。|
|[CTaskDialog::DoModal](#domodal)|「`CTaskDialog`」を表示します。|
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|使用可能な一般的なボタンの数を取得します。|
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|一般的なボタンの種類に Windows のボタンに関連付けられている標準の変換、`CTaskDialog`クラス。|
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|関連付けられている一般的なボタンの種類のいずれかに変換、`CTaskDialog`クラスを標準 Windows ボタンをクリックします。|
|[CTaskDialog::GetOptions](#getoptions)|このオプションのフラグを返します`CTaskDialog`します。|
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|選択したコマンド ボタン コントロールを返します。|
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|選択したラジオ ボタンを返します。|
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|確認のチェック ボックスの状態を取得します。|
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|コマンド ボタン コントロールまたは一般的なボタンが有効かどうかを判断します。|
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|ラジオ ボタンが有効になっているかどうかを判断します。|
|[CTaskDialog::IsSupported](#issupported)|アプリケーションを実行しているコンピューターをサポートするかどうかを決定、`CTaskDialog`します。|
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|文字列テーブルからデータを使用して、コマンド ボタン コントロールを追加します。|
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|文字列テーブルからデータを使用して、オプション ボタンを追加します。|
|[CTaskDialog::NavigateTo](#navigateto)|別にフォーカスが移動`CTaskDialog`します。|
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|フレームワークは、ユーザーがコマンド ボタン コントロールをクリックすると、このメソッドを呼び出します。|
|[CTaskDialog::OnCreate](#oncreate)|作成した後、フレームワークはこのメソッドを呼び出して、`CTaskDialog`します。|
|[CTaskDialog::OnDestroy](#ondestroy)|これを破棄する前にすぐに、フレームワークはこのメソッドを呼び出して、`CTaskDialog`します。|
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|フレームワークは、ユーザーが展開ボタンをクリックすると、このメソッドを呼び出します。|
|[CTaskDialog::OnHelp](#onhelp)|フレームワークは、ユーザーがヘルプを要求すると、このメソッドを呼び出します。|
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|フレームワークは、ユーザーがハイパーリンクをクリックしたときに、このメソッドを呼び出します。|
|[CTaskDialog::OnInit](#oninit)|フレームワークは、このメソッドを呼び出すときに、`CTaskDialog`が初期化されます。|
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|ユーザーがコントロールに関してフォーカスを移動したときに、フレームワークはこのメソッドを呼び出して、`CTaskDialog`します。|
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|フレームワークは、ユーザーがラジオ ボタン コントロールを選択すると、このメソッドを呼び出します。|
|[CTaskDialog::OnTimer](#ontimer)|フレームワークは、タイマーの期限が切れると、このメソッドを呼び出します。|
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|フレームワークは、ユーザーが確認のチェック ボックスをクリックすると、このメソッドを呼び出します。|
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|すべてのコマンド コントロールを削除、`CTaskDialog`します。|
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|すべてのラジオ ボタンの削除、`CTaskDialog`します。|
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|コマンド ボタン コントロールを更新プログラム、`CTaskDialog`します。|
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|有効にして、UAC の昇格を必要とする一般的なボタンのサブセットを更新します。|
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|一般的なボタンを追加、`CTaskDialog`します。|
|[CTaskDialog::SetContent](#setcontent)|内容を更新、`CTaskDialog`します。|
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|既定のコマンド ボタン コントロールを指定します。|
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|既定のオプション ボタンを指定します。|
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|幅を調整、`CTaskDialog`します。|
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|更新の展開領域、`CTaskDialog`します。|
|[CTaskDialog::SetFooterIcon](#setfootericon)|フッターのアイコンを更新、`CTaskDialog`します。|
|[CTaskDialog::SetFooterText](#setfootertext)|フッターにテキストを更新、`CTaskDialog`します。|
|[CTaskDialog::SetMainIcon](#setmainicon)|メイン アイコンの更新、`CTaskDialog`します。|
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|更新のメイン インストラクション、`CTaskDialog`します。|
|[CTaskDialog::SetOptions](#setoptions)|オプションを構成します、`CTaskDialog`します。|
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|構成の選択バー、 `CTaskDialog`  ダイアログ ボックスに追加します。|
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|進行状況バーの位置を調整します。|
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|進行状況バーの範囲を調整します。|
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|進行状況バーの状態を設定し、それを表示、`CTaskDialog`します。|
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|有効またはラジオ ボタンを無効にします。|
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|確認のチェック ボックスのチェック状態を設定します。|
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|確認のチェック ボックスの右側にあるテキストを設定します。|
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|タイトルを設定、`CTaskDialog`します。|
|[CTaskDialog::ShowDialog](#showdialog)|作成し、表示、`CTaskDialog`します。|
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|フレームワークは、さまざまな Windows メッセージへの応答でこれを呼び出します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|`m_aButtons`|コマンド ボタン コントロールの配列、`CTaskDialog`します。|
|`m_aRadioButtons`|ラジオ ボタン コントロールの配列、`CTaskDialog`します。|
|`m_bVerified`|`TRUE` 確認のチェック ボックスがチェックされていることを示します。`FALSE`でないことを示します。|
|`m_footerIcon`|フッターに、アイコン、`CTaskDialog`します。|
|`m_hWnd`|ウィンドウへのハンドル、`CTaskDialog`します。|
|`m_mainIcon`|メイン アイコン、`CTaskDialog`します。|
|`m_nButtonDisabled`|指定すると、一般的なボタンのマスクが無効です。|
|`m_nButtonElevation`|指定すると、一般的なボタンのマスクは、UAC の昇格が必要です。|
|`m_nButtonId`|選択したコマンドのボタン コントロールの ID。|
|`m_nCommonButton`|一般的なボタンを示すマスクに表示される、`CTaskDialog`します。|
|`m_nDefaultCommandControl`|コマンド ボタンの ID のコントロールが選択されている場合、`CTaskDialog`が表示されます。|
|`m_nDefaultRadioButton`|ラジオ ボタンの ID のコントロールが選択されている場合、`CTaskDialog`が表示されます。|
|`m_nFlags`|オプションを示すマスク、`CTaskDialog`します。|
|`m_nProgressPos`|進行状況バーの現在の位置。  この値の有効値の範囲は `m_nProgressRangeMin` ～ `m_nProgressRangeMax` です。|
|`m_nProgressRangeMax`|進行状況バーの最大値。|
|`m_nProgressRangeMin`|進行状況バーの最小値。|
|`m_nProgressState`|進行状況バーの状態。 詳細については、次を参照してください。 [CTaskDialog::SetProgressBarState](#setprogressbarstate)します。|
|`m_nRadioId`|選択したラジオ ボタン コントロールの ID。|
|`m_nWidth`|幅、 `CTaskDialog` (ピクセル単位)。|
|`m_strCollapse`|文字列、`CTaskDialog`展開された情報が非表示の場合、展開 ボックスの右側に表示されます。|
|`m_strContent`|コンテンツの文字列、`CTaskDialog`します。|
|`m_strExpand`|文字列、`CTaskDialog`展開された情報が表示されるときに展開 ボックスの右側に表示されます。|
|`m_strFooter`|フッター、`CTaskDialog`します。|
|`m_strInformation`|展開された情報、`CTaskDialog`します。|
|`m_strMainInstruction`|メイン インストラクション、`CTaskDialog`します。|
|`m_strTitle`|タイトル、`CTaskDialog`します。|
|`m_strVerification`|文字列を`CTaskDialog`確認のチェック ボックスの右側に表示されます。|

## <a name="remarks"></a>Remarks

`CTaskDialog`クラスは、標準の Windows メッセージ ボックスに代わるものあり、ユーザーから情報を収集する新しいコントロールなどの追加機能。 このクラスは、Visual Studio 2010 以降では、MFC ライブラリでは。 `CTaskDialog`は Windows Vista から使用できます。 Windows の以前のバージョンを表示できません、`CTaskDialog`オブジェクト。 使用`CTaskDialog::IsSupported`を実行時に、現在のユーザーが、タスク ダイアログ ボックスを表示できるかどうかを判断します。 標準 Windows メッセージ ボックスは、引き続きサポートされます。

`CTaskDialog`は Unicode ライブラリを使用してアプリケーションをビルドするときにのみ使用できます。

`CTaskDialog` 2 つの異なるコンス トラクターがあります。 1 つのコンス トラクターでは、2 つのコマンド ボタンと最大 6 つの標準ボタン コントロールを指定することができます。 さらにコマンド ボタンを追加するには、作成した後、`CTaskDialog`します。 2 番目のコンス トラクターは、コマンド ボタンをサポートしていませんが、無制限の数の標準ボタン コントロールを追加することができます。 コンス トラクターの詳細については、次を参照してください。 [CTaskDialog::CTaskDialog](#ctaskdialog)します。

次の図は、サンプル`CTaskDialog`を一部のコントロールの場所を示します。

![CTaskDialog の例](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialog の例") <br/>
CTaskDialog のサンプル

## <a name="requirements"></a>必要条件

**最低限必要なオペレーティング システム:** Windows Vista

**ヘッダー:** afxtaskdialog.h

##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl

新しいコマンド ボタン コントロールを追加、`CTaskDialog`します。

```
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>パラメーター

*nCommandControlID*<br/>
[in]コマンド コントロールの識別番号。

*strCaption*<br/>
[in]文字列を`CTaskDialog`ユーザーに表示します。 この文字列を使用して、コマンドの目的を説明します。

*bEnabled*<br/>
[in]新しいボタンを有効または無効になっているかどうかを示すブール値パラメーター。

*bRequiresElevation*<br/>
[in]コマンドが昇格を必要とするかどうかを示すブール値パラメーター。

### <a name="remarks"></a>Remarks

`CTaskDialog Class`コマンド ボタン コントロールの無制限の数を表示することができます。 ただし場合、`CTaskDialog`表示コマンドのいずれかのボタン コントロールで、最大 6 つのボタンを表示できます。 場合、`CTaskDialog`コマンド ボタン コントロールを持たない、ボタンの無制限の数を表示できます。

ユーザーが、コマンド ボタン コントロールを選択すると、`CTaskDialog`を閉じます。 アプリケーションを使用して、ダイアログ ボックスが表示される場合[CTaskDialog::DoModal](#domodal)、`DoModal`を返します、 *nCommandControlID*の選択コマンドのボタン コントロール。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="addradiobutton"></a>  CTaskDialog::AddRadioButton

ラジオ ボタンを追加、`CTaskDialog`します。

```
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>パラメーター

*nRadioButtonID*<br/>
[in]オプション ボタンの id 番号。

*strCaption*<br/>
[in]文字列を`CTaskDialog`ラジオ ボタンの横に表示されます。

*bEnabled*<br/>
[in]ラジオ ボタンが有効になっているかどうかを示すブール値パラメーター。

### <a name="remarks"></a>Remarks

ためのラジオ ボタン、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)を使用すると、ユーザーから情報を収集します。 関数を使用して[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)ラジオ ボタンが選択されているかを判断します。

`CTaskDialog`いる必要はありません、 *nRadioButtonID*パラメーターは、オプション ボタンごとに一意です。 ただし、オプション ボタンごとに個別の識別子を使用しない場合、予期しない動作が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl

プログラムで、コマンド ボタンのコントロールや一般的なボタンをクリックします。

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>パラメーター

*nCommandControlID*<br/>
[in]をクリックするコントロールのコマンド ID。

### <a name="remarks"></a>Remarks

このメソッドは、windows メッセージ TDM_CLICK_BUTTON を生成します。

##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton

プログラムでオプション ボタンをクリックします。

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>パラメーター

*nRadioButtonID*<br/>
[in]クリックするラジオ ボタンの ID。

### <a name="remarks"></a>Remarks

このメソッドは、windows メッセージ TDM_CLICK_RADIO_BUTTON を生成します。

##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog

インスタンスを作成、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)します。

```
CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));

CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>パラメーター

*strContent*<br/>
[in]コンテンツを使用する文字列、`CTaskDialog`します。

*strMainInstruction*<br/>
[in]メイン インストラクション、`CTaskDialog`します。

*strTitle*<br/>
[in]タイトル、`CTaskDialog`します。

*nCommonButtons*<br/>
[in]追加する一般的なボタンのマスク、`CTaskDialog`します。

*nTaskDialogOptions*<br/>
[in]使用するオプションのセット、`CTaskDialog`します。

*strFooter*<br/>
[in]フッターとして使用する文字列。

*nIDCommandControlsFirst*<br/>
[in]最初のコマンドの文字列 ID。

*nIDCommandControlsLast*<br/>
[in]最後のコマンドの文字列 ID。

### <a name="remarks"></a>Remarks

追加できる 2 つの方法がある、`CTaskDialog`アプリケーションにします。 最初の方法が、コンス トラクターのいずれかを使用して作成するには、`CTaskDialog`を使用して表示および[CTaskDialog::DoModal](#domodal)します。 2 つ目の方法は、静的関数を使用する[CTaskDialog::ShowDialog](#showdialog)、表示できる、`CTaskDialog`明示的に作成せず、`CTaskDialog`オブジェクト。

2 番目のコンス トラクターは、アプリケーションのリソース ファイルからデータを使用して、コマンド ボタン コントロールを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドは、文字列テーブルの間で有効な各エントリのコマンド ボタン コントロールを追加します*nIDCommandControlsFirst*と*nCommandControlsLast*までの値。 これらのコマンド ボタン コントロールの文字列テーブル内の文字列がコントロールのキャプションと文字列 ID は、コントロールの ID です。

参照してください[CTaskDialog::SetOptions](#setoptions)有効なオプションの一覧についてはします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="domodal"></a>  CTaskDialog::DoModal

表示、`CTaskDialog`モーダルになります。

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>パラメーター

*hParent*<br/>
[in]親ウィンドウ、`CTaskDialog`します。

### <a name="return-value"></a>戻り値

ユーザーによる選択に対応する整数。

### <a name="remarks"></a>Remarks

このインスタンスが表示されます、 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md)します。 次に、アプリケーションは、ユーザーがダイアログ ボックスを閉じます待機します。

`CTaskDialog` 、ユーザーは、コマンド リンク コントロールでは、一般的なボタンが選択または終了すると、終了、`CTaskDialog`します。 戻り値は、ユーザーがダイアログ ボックスを閉じた方法を示す識別子です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount

一般的なボタンの数を取得します。

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>戻り値

使用できる一般的なボタンの数。

### <a name="remarks"></a>Remarks

一般的なボタンは既定のボタンに提供する[CTaskDialog::CTaskDialog](#ctaskdialog)します。 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)  ダイアログ ボックスの下部にボタンが表示されます。

CommCtrl.h で列挙されたボタンの一覧が提供されます。

##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag

一般的なボタンの種類に Windows のボタンに関連付けられている標準の変換、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)します。

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>パラメーター

*nButtonId*<br/>
[in]標準の Windows ボタンの値。

### <a name="return-value"></a>戻り値

対応する値`CTaskDialog`一般的なボタンをクリックします。 対応する一般的なボタンがない場合は、このメソッドは 0 を返します。

##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId

関連付けられている一般的なボタンの種類のいずれかに変換、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)標準 Windows ボタンをクリックします。

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>パラメーター

*指します*<br/>
[in]一般的なボタンの種類に関連付けられている、`CTaskDialog`クラス。

### <a name="return-value"></a>戻り値

対応する標準の Windows ボタンの値。 対応する Windows ボタンがない場合、メソッドは 0 を返します。

##  <a name="getoptions"></a>  CTaskDialog::GetOptions

このオプションのフラグを返します`CTaskDialog`します。

```
int GetOptions() const;
```

### <a name="return-value"></a>戻り値

フラグ、`CTaskDialog`します。

### <a name="remarks"></a>Remarks

使用できるオプションの詳細については、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)を参照してください[CTaskDialog::SetOptions](#setoptions)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getselectedcommandcontrolid"></a>  CTaskDialog::GetSelectedCommandControlID

選択したコマンド ボタン コントロールを返します。

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>戻り値

現在選択されているコマンドのボタン コントロールの ID。

### <a name="remarks"></a>Remarks

このメソッドを使用して、ユーザーが選択したコマンド ボタンの ID を取得する必要はありません。 いずれかでその ID が返される[CTaskDialog::DoModal](#domodal)または[CTaskDialog::ShowDialog](#showdialog)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="getselectedradiobuttonid"></a>  CTaskDialog::GetSelectedRadioButtonID

選択したラジオ ボタンを返します。

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>戻り値

選択したラジオ ボタンの ID。

### <a name="remarks"></a>Remarks

ユーザーが選択されたラジオ ボタンを取得する ダイアログ ボックスを閉じた後は、このメソッドを使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState

確認のチェック ボックスの状態を取得します。

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>戻り値

チェック ボックスがオンの場合、FALSE でない場合は TRUE。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled

コマンド ボタン コントロールまたはボタンが有効かどうかを判断します。

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>パラメーター

*nCommandControlID*<br/>
[in]テストするコマンド ボタン コントロールまたはボタンの ID。

### <a name="return-value"></a>戻り値

コントロールが有効な場合、FALSE でない場合は TRUE。

### <a name="remarks"></a>Remarks

このメソッドを使用するには両方のコマンド ボタン コントロールの可用性との一般的なボタンを判断する、`CTaskDialog`クラス *。

場合*nCommandControlID*共通のいずれかの有効な id ではありませんは、`CTaskDialog`ボタンまたはコマンド ボタン コントロールでは、このメソッドは例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled

ラジオ ボタンが有効になっているかどうかを判断します。

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>パラメーター

*nRadioButtonID*<br/>
[in]テストするラジオ ボタンの ID。

### <a name="return-value"></a>戻り値

ラジオ ボタンが有効な場合、FALSE でない場合は TRUE。

### <a name="remarks"></a>Remarks

場合*nRadioButtonID*有効な識別子ではないラジオのボタンで、このメソッドが例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="issupported"></a>  CTaskDialog::IsSupported

アプリケーションを実行しているコンピューターをサポートするかどうかを決定、`CTaskDialog`します。

```
static BOOL IsSupported();
```

### <a name="return-value"></a>戻り値

コンピューターがサポートされている場合は TRUE、 `CTaskDialog`;FALSE それ以外の場合。

### <a name="remarks"></a>Remarks

この関数を使用して、アプリケーションを実行しているコンピューターがサポートしている場合、実行時に決定する、`CTaskDialog`クラス。 コンピューターがサポートしていない場合、 `CTaskDialog`、別のユーザーに情報を伝達する方法を提供する必要があります。 使用を試みる場合、アプリケーションがクラッシュする`CTaskDialog`がサポートされていないコンピューターで、`CTaskDialog`クラス。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls

文字列テーブルからデータを使用して、コマンド ボタン コントロールを追加します。

```
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>パラメーター

*nIDCommandControlsFirst*<br/>
[in]最初のコマンドの文字列 ID。

*nIDCommandControlsLast*<br/>
[in]最後のコマンドの文字列 ID。

### <a name="remarks"></a>Remarks

このメソッドは、アプリケーションのリソース ファイルからデータを使用して、コマンド ボタン コントロールを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドを使用して追加のコマンド ボタン コントロールの新しいコントロールのキャプションと文字列 ID のコントロールの ID に文字列を使用します。 選択されている文字列の範囲がによって提供される*nIDCommandControlsFirst*と*nCommandControlsLast*までの値。 範囲の空のエントリがある場合、メソッドはそのエントリのコマンド ボタン コントロールを追加できません。

既定では、新しいコマンド ボタン コントロールが有効になっているし、昇格を必要としません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons

文字列テーブルからデータを使用して、オプション ボタン コントロールを追加します。

```
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>パラメーター

*nIDRadioButtonsFirst*<br/>
[in]最初のラジオ ボタンの文字列 ID。

*nIDRadioButtonsLast*<br/>
[in]最後のラジオ ボタンの文字列 ID。

### <a name="remarks"></a>Remarks

このメソッドは、アプリケーションのリソース ファイルからデータを使用して、オプション ボタンを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドを使用して追加された新しいラジオ ボタン、ラジオ ボタンのキャプションと文字列 ID のラジオ ボタンの ID の文字列を使用します。 選択されている文字列の範囲がによって提供される*nIDRadioButtonsFirst*と*nRadioButtonsLast*までの値。 範囲の空のエントリがある場合、メソッドはそのエントリのラジオ ボタンが追加されません。

既定では、新しいラジオ ボタンが有効にします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="navigateto"></a>  CTaskDialog::NavigateTo

別にフォーカスが移動`CTaskDialog`します。

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>パラメーター

*oTaskDialog*<br/>
[in]`CTaskDialog`フォーカスを受け取る。

### <a name="remarks"></a>Remarks

このメソッドは、現在を非表示に`CTaskDialog`が表示されたら、 *oTaskDialog*します。 *OTaskDialog*現在と同じ場所に表示される`CTaskDialog`します。

##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick

フレームワークは、ユーザーがコマンド ボタン コントロールをクリックすると、このメソッドを呼び出します。

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>パラメーター

*nCommandControlID*<br/>
[in]ユーザーが選択したコマンド ボタン コントロールの ID。

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="oncreate"></a>  CTaskDialog::OnCreate

作成した後、フレームワークはこのメソッドを呼び出して、`CTaskDialog`します。

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy

これを破棄する前にすぐに、フレームワークはこのメソッドを呼び出して、`CTaskDialog`します。

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="onexpandbuttonclick"></a>  CTaskDialog::OnExpandButtonClick

フレームワークは、ユーザーが展開ボタンをクリックすると、このメソッドを呼び出します。

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>パラメーター

*bExpanded*<br/>
[in]0 以外の値を示します、余分な情報が表示されます。0 では、追加の情報が非表示を示します。

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="onhelp"></a>  CTaskDialog::OnHelp

フレームワークは、ユーザーがヘルプを要求すると、このメソッドを呼び出します。

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="onhyperlinkclick"></a>  CTaskDialog::OnHyperlinkClick

フレームワークは、ユーザーがハイパーリンクをクリックしたときに、このメソッドを呼び出します。

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>パラメーター

*strHref*<br/>
[in]ハイパーリンクを表す文字列。

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

このメソッドを呼び出す[ShellExecute](/windows/desktop/api/shellapi/nf-shellapi-shellexecutea)前に、S_OK を返します。

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="oninit"></a>  CTaskDialog::OnInit

フレームワークは、このメソッドを呼び出すときに、`CTaskDialog`が初期化されます。

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage

フレームワークへの応答でこのメソッドを呼び出して、 [CTaskDialog::NavigateTo](#navigateto)メソッド。

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick

フレームワークは、ユーザーがラジオ ボタン コントロールを選択すると、このメソッドを呼び出します。

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>パラメーター

*nRadioButtonID*<br/>
[in]ユーザーがクリックしたラジオ ボタン コントロールの ID。

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="ontimer"></a>  CTaskDialog::OnTimer

フレームワークは、タイマーの期限が切れると、このメソッドを呼び出します。

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>パラメーター

*lTime*<br/>
[in]以降のミリ秒単位の時間、`CTaskDialog`が作成されたか、タイマーをリセットします。

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick

フレームワークは、ユーザーが確認のチェック ボックスをクリックすると、このメソッドを呼び出します。

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>パラメーター

*bChecked*<br/>
[in]TRUE は、確認のチェック ボックスが選択されていることを示しますFALSE でないことを示します。

### <a name="return-value"></a>戻り値

既定の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。

##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls

すべてのコマンド ボタン コントロールを削除、`CTaskDialog`します。

```
void RemoveAllCommandControls();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons

すべてのラジオ ボタンの削除、`CTaskDialog`します。

```
void RemoveAllRadioButtons();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions

コマンド ボタン コントロールを更新プログラム、`CTaskDialog`します。

```
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>パラメーター

*nCommandControlID*<br/>
[in]更新するコマンド コントロールの ID。

*bEnabled*<br/>
[in]指定したコマンドのボタン コントロールを有効または無効になっているかどうかを示すブール値パラメーター。

*bRequiresElevation*<br/>
[in]指定されたコマンド ボタン コントロールに昇格が必要なかどうかを示すブール値パラメーター。

### <a name="remarks"></a>Remarks

このメソッドを使用して、コマンド ボタン コントロールが有効かを追加した後は、昇格を必要とするかどうかを変更する、`CTaskDialog`クラス。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions

有効にして、UAC の昇格を必要とする一般的なボタンのサブセットを更新します。

```
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>パラメーター

*nDisabledButtonMask*<br/>
[in]無効にする一般的なボタンのマスク。

*nElevationButtonMask*<br/>
[in]昇格が必要な一般的なボタンのマスク。

### <a name="remarks"></a>Remarks

インスタンスに使用できる一般的なボタンを設定することができます、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)コンス トラクターを使用して[CTaskDialog::CTaskDialog](#ctaskdialog)メソッドと[CTaskDialog::SetCommonButtons](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` 新しい一般的なボタンの追加はサポートしません。

このメソッドを使用して無効にするか、またはこれにはない一般的なボタンを昇格する場合`CTaskDialog`、このメソッドを使用して例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ。

このメソッドにより、使用可能ないずれかのボタン、`CTaskDialog`ではありませんが、 *nDisabledButtonMask*無効だった場合でも、します。 このメソッドで同様の方法で: 一般的なボタンが使用できますに含まれていない場合は、昇格が必要としないとして一般的なボタンを記録*扱わ*します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons

一般的なボタンを追加、`CTaskDialog`します。

```
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>パラメーター

*nButtonMask*<br/>
[in]追加するボタンのマスク、`CTaskDialog`します。

*nDisabledButtonMask*<br/>
[in]無効にするボタンのマスク。

*nElevationButtonMask*<br/>
[in]昇格が必要なボタンのマスク。

### <a name="remarks"></a>Remarks

このインスタンスの後、表示ウィンドウにこのメソッドを呼び出すことはできません、`CTaskDialog`クラスが作成されます。 この場合、このメソッドは例外をスローします。

ボタンが示される*nButtonMask*にあらかじめ追加して、一般的なボタンのオーバーライド、 `CTaskDialog`。 示されているボタンのみ*nButtonMask*利用できます。

いずれか*nDisabledButtonMask*または*扱わ*内にないボタンに表示*nButtonMask*、このメソッドが、を使用して例外をスロー[を確認してください](diagnostic-services.md#ensure)マクロ。

既定では、すべての一般的なボタンが有効になっているし、昇格を必要としません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcontent"></a>  CTaskDialog::SetContent

内容を更新、`CTaskDialog`します。

```
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>パラメーター

*strContent*<br/>
[in]ユーザーに表示する文字列。

### <a name="remarks"></a>Remarks

コンテンツ、`CTaskDialog`クラスは、ダイアログ ボックスのメイン セクションでは、ユーザーに表示されるテキスト。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl

既定のコマンド ボタン コントロールを指定します。

```
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>パラメーター

*nCommandControlID*<br/>
[in]既定値にコマンド ボタン コントロールの ID。

### <a name="remarks"></a>Remarks

既定のコマンド ボタン コントロールがコントロールであるとき、`CTaskDialog`をユーザーに最初に表示されます。

指定されたコマンド ボタン コントロールを見つけられない場合、このメソッドが例外をスロー *nCommandControlID*します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton

既定のオプション ボタンを指定します。

```
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>パラメーター

*nRadioButtonID*<br/>
[in]既定では、するラジオ ボタンの ID。

### <a name="remarks"></a>Remarks

既定のオプション ボタンは、ボタンが選択されているときに、`CTaskDialog`をユーザーに最初に表示されます。

指定したオプション ボタンを見つけられない場合、このメソッドが例外をスロー *nRadioButtonID*します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth

幅を調整、`CTaskDialog`します。

```
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
[in]ダイアログ ボックスで、ピクセル単位の幅。

### <a name="remarks"></a>Remarks

パラメーター *nWidth* 0 以上にする必要があります。 それ以外の場合、このメソッドは例外をスローします。

場合*nWidth* 0 で、このメソッドは、ダイアログ ボックスの既定のサイズ設定に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea

更新の展開領域、`CTaskDialog`します。

```
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>パラメーター

*strExpandedInformation*<br/>
[in]文字列を`CTaskDialog`展開ボタンをクリックすると、ダイアログ ボックスの本文が表示されます。

*strCollapsedLabel*<br/>
[in]文字列を`CTaskDialog`展開された領域が折りたたまれているときに拡張ボタンの横に表示されます。

*strExpandedLabel*<br/>
[in]文字列を`CTaskDialog`展開された領域が表示されたら、拡張ボタンの横に表示されます。

### <a name="remarks"></a>Remarks

拡張領域、`CTaskDialog`クラスでは、ユーザーに追加情報を提供することができます。 拡張領域がの主要部分では、`CTaskDialog`タイトルとコンテンツの文字列のすぐ下にあります。

ときに、`CTaskDialog`を最初に展開された情報を表示しないと表示は`strCollapsedLabel`展開ボタンの横にあります。 拡張ボタンをクリックすると、`CTaskDialog`表示*strExpandedInformation*にラベルを変更し、 *strExpandedLabel*。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon

フッター アイコンを更新、`CTaskDialog`します。

```
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>パラメーター

*hFooterIcon*<br/>
[in]新しいアイコン、`CTaskDialog`します。

*lpszFooterIcon*<br/>
[in]新しいアイコン、`CTaskDialog`します。

### <a name="remarks"></a>Remarks

下部でフッター アイコンが表示されます、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)します。 フッター テキストを関連付けることできます。 フッター テキストを変更する[CTaskDialog::SetFooterText](#setfootertext)します。

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)マクロ場合、`CTaskDialog`が表示されますか、入力パラメーターが NULL です。

A`CTaskDialog`のみを受け入れることができます、`HICON`または`LPCWSTR`フッター アイコンとして。 これは、コンス トラクターで TDF_USE_HICON_FOOTER オプションを設定して構成がまたは[CTaskDialog::SetOptions](#setoptions)します。 既定で、`CTaskDialog`を使用するように構成`LPCWSTR`フッター アイコンの入力型として。 このメソッドは、不適切な型を使用して、アイコンを設定しようとする場合に例外を生成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText

フッターにテキストを更新、`CTaskDialog`します。

```
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>パラメーター

*strFooterText*<br/>
[in]フッターの新しいテキスト。

### <a name="remarks"></a>Remarks

一番下にフッターのテキストの横にあるフッター アイコンが表示されます、`CTaskDialog`します。 フッターのアイコンを変更する[CTaskDialog::SetFooterIcon](#setfootericon)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon

メイン アイコンの更新、`CTaskDialog`します。

```
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>パラメーター

*hMainIcon*<br/>
[in]新しいアイコン。

*lpszMainIcon*<br/>
[in]新しいアイコン。

### <a name="remarks"></a>Remarks

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)マクロ場合、`CTaskDialog`が表示されますか、入力パラメーターが NULL です。

A`CTaskDialog`のみを受け入れることができます、`HICON`または`LPCWSTR`メイン アイコン。 これを構成するには、コンス トラクターで TDF_USE_HICON_MAIN オプションの設定やで、 [CTaskDialog::SetOptions](#setoptions)メソッド。 既定で、`CTaskDialog`を使用するように構成`LPCWSTR`メイン アイコンの入力型として。 このメソッドは、不適切な型を使用して、アイコンを設定しようとする場合に例外を生成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction

更新のメイン インストラクション、`CTaskDialog`します。

```
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>パラメーター

*strInstructions*<br/>
[in]新しいメイン命令。

### <a name="remarks"></a>Remarks

メイン インストラクション、`CTaskDialog`クラスは、大規模な太字のフォントでユーザーに表示されるテキスト。 ダイアログ ボックスで、タイトル バーの下にあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setoptions"></a>  CTaskDialog::SetOptions

オプションを構成します、`CTaskDialog`します。

```
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>パラメーター

*nOptionFlag*<br/>
[in]使用するフラグのセット、`CTaskDialog`します。

### <a name="remarks"></a>Remarks

このメソッドは、の現在のすべてのオプションをクリアします、`CTaskDialog`します。 現在のオプションを保持するためにする必要がありますして取得しまず[CTaskDialog::GetOptions](#getoptions)し、それらを設定するオプションを使用して結合します。

次の表では、有効なオプションをすべて一覧表示します。

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|内のハイパーリンクをできるように、`CTaskDialog`します。|
|TDF_USE_HICON_MAIN|構成、`CTaskDialog`を使用する、`HICON`用メイン アイコン。 使用する方法が、`LPCWSTR`します。|
|TDF_USE_HICON_FOOTER|構成、`CTaskDialog`を使用する、`HICON`フッター アイコン。 使用する方法が、`LPCWSTR`します。|
|TDF_ALLOW_DIALOG_CANCELLATION|により、ユーザーを閉じる、`CTaskDialog`またはダイアログ ボックスの右上隅のアイコンを使用して、キーボードを使用していて、**キャンセル**ボタンが有効になっていません。 このフラグが設定されていない場合、**キャンセル**ボタンが有効でない、ユーザーが alt キーを押しながら f4 キーを Esc キーを使用して、ダイアログ ボックスを閉じることができませんまたはタイトル バーの閉じるボタン。|
|TDF_USE_COMMAND_LINKS|構成、`CTaskDialog`コマンド ボタン コントロールを使用します。|
|TDF_USE_COMMAND_LINKS_NO_ICON|構成、`CTaskDialog`コントロールの横にアイコンを表示せずにコマンド ボタン コントロールを使用します。 TDF_USE_COMMAND_LINKS TDF_USE_COMMAND_LINKS_NO_ICON をオーバーライドします。|
|TDF_EXPAND_FOOTER_AREA|拡張領域が現在展開されていることを示します。|
|TDF_EXPANDED_BY_DEFAULT|拡張領域が既定で展開されるかどうかを判断します。|
|TDF_VERIFICATION_FLAG_CHECKED|確認のチェック ボックスが現在選択されていることを示します。|
|TDF_SHOW_PROGRESS_BAR|構成、`CTaskDialog`進行状況バーを表示します。|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|マーキーの進行状況バーに進行状況バーを構成します。 このオプションを有効にすると、TDF_SHOW_PROGRESS_BAR が想定される動作を設定する必要があります。|
|TDF_CALLBACK_TIMER|示します、`CTaskDialog`コールバック間隔は、約 200 ミリ秒に設定されます。|
|TDF_POSITION_RELATIVE_TO_WINDOW|構成、`CTaskDialog`親ウィンドウを基準に中央揃えにします。 このフラグが有効でない場合、`CTaskDialog`モニターの基準とした中央揃えで配置します。|
|TDF_RTL_LAYOUT|構成、`CTaskDialog`右から左のレイアウトにします。|
|TDF_NO_DEFAULT_RADIO_BUTTON|ラジオ ボタンが選択されていないことを示すときに、`CTaskDialog`が表示されます。|
|TDF_CAN_BE_MINIMIZED|ユーザーが最小化できるように、`CTaskDialog`します。 このオプションをサポートするために、`CTaskDialog`モーダルにすることはできません。 MFC は、モードレスをサポートしていないために、MFC がこのオプションをサポートしない`CTaskDialog`します。|

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee

構成の選択バー、 `CTaskDialog`  ダイアログ ボックスに追加します。

```
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>パラメーター

*bEnabled*<br/>
[in]マーキー バーを有効にする場合は TRUEマーキーのバーを無効にしてから削除する場合は FALSE、`CTaskDialog`します。

*nMarqueeSpeed*<br/>
[in]マーキー バー速度を示す整数。

### <a name="remarks"></a>Remarks

メイン テキストの下に、マーキー バーが表示されます、`CTaskDialog`クラス。

使用*nMarqueeSpeed*マーキー バー速度を設定するより大きな値が低速を示します。 値 0 を*nMarqueeSpeed*マーキー バーが Windows の既定の速度で移動します。

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nMarqueeSpeed*が 0 未満です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition

進行状況バーの位置を調整します。

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>パラメーター

*nProgressPos*<br/>
[in]進行状況バーの位置。

### <a name="remarks"></a>Remarks

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nProgressPos*進行状況バーの範囲ではありません。 進行状況バーの範囲を変更する[CTaskDialog::SetProgressBarRange](#setprogressbarrange)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange

進行状況バーの範囲を調整します。

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>パラメーター

*nRangeMin*<br/>
[in]進行状況バーの下限値です。

*nRangeMax*<br/>
[in]進行状況バーの上限値です。

### <a name="remarks"></a>Remarks

進行状況バーの位置が関連して*nRangeMin*と*nRangeMax*します。 たとえば場合、 *nRangeMin* 50 と*nRangeMax* 100 は、進行状況バーの間で 75 の位置は偶数です。 使用[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)進行状況バーの位置を設定します。

進行状況バーを表示するには、オプションを TDF_SHOW_PROGRESS_BAR を有効にする必要があり、TDF_SHOW_MARQUEE_PROGRESS_BAR 有効にしないでください。 このメソッドは自動的に TDF_SHOW_PROGRESS_BAR を設定し、TDF_SHOW_MARQUEE_PROGRESS_BAR をクリアします。 使用[CTaskDialog::SetOptions](#setoptions)のこのインスタンスのオプションを手動で変更する、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)します。

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nRangeMin*はより小さくない*nRangeMax*します。 このメソッドは、場合も、例外をスロー、`CTaskDialog`が既に表示され、マーキーの進行状況バーがあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState

進行状況バーの状態を設定し、それを表示、`CTaskDialog`します。

```
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>パラメーター

*nState*<br/>
[in]進行状況バーの状態。 使用可能な値は、「解説」を参照してください。

### <a name="remarks"></a>Remarks

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)マクロ場合、`CTaskDialog`が既に表示され、マーキーの進行状況バーがあります。

次の表に、可能な値*状態*します。 これらすべてのケースでは指定された位置に達するまで、進行状況バーは標準の色に入力します。 その時点の状態に基づいた色が変更されます。

|||
|-|-|
|PBST_NORMAL|後は、進行状況バーが塗りつぶさ、`CTaskDialog`バーの色を変更することはできません。 既定では、通常の色が緑にします。|
|PBST_ERROR|後は、進行状況バーが塗りつぶさ、`CTaskDialog`エラー カラー バーの色を変更します。 既定では、これは赤です。|
|PBST_PAUSED|後は、進行状況バーが塗りつぶさ、`CTaskDialog`バーの色を一時停止した色に変更します。 既定では、この色は黄色です。|

進行状況バーが停止し、設定できる[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setradiobuttonoptions"></a>  CTaskDialog::SetRadioButtonOptions

有効またはラジオ ボタンを無効にします。

```
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>パラメーター

*nRadioButtonID*<br/>
[in]ラジオ ボタン コントロールの ID。

*bEnabled*<br/>
[in]オプション ボタンを有効にする場合は TRUEラジオ ボタンを無効にする場合は FALSE。

### <a name="remarks"></a>Remarks

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nRadioButtonID*ラジオ ボタンの有効な ID ではありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox

確認のチェック ボックスのチェック状態を設定します。

```
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>パラメーター

*bChecked*<br/>
[in]True を確認のチェック ボックス選択したときに、`CTaskDialog`が表示されます。チェック ボックスを確認する場合は FALSE を選択解除されているときに、`CTaskDialog`が表示されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText

確認のチェック ボックスの右側に表示されるテキストを設定します。

```
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>パラメーター

*strVerificationText*<br/>
[in]このメソッドは、確認のチェック ボックスの横に表示されるテキスト。

### <a name="remarks"></a>Remarks

このメソッドで例外をスロー、[を確認してください](diagnostic-services.md#ensure)場合は、このマクロのインスタンス、`CTaskDialog`クラスが既に表示されています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle

タイトルを設定、`CTaskDialog`します。

```
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>パラメーター

*strWindowTitle*<br/>
[in]新しいタイトル、`CTaskDialog`します。

### <a name="remarks"></a>Remarks

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="showdialog"></a>  CTaskDialog::ShowDialog

作成し、表示、`CTaskDialog`します。

```
static INT_PTR ShowDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>パラメーター

*strContent*<br/>
[in]コンテンツを使用する文字列、`CTaskDialog`します。

*strMainInstruction*<br/>
[in]メイン インストラクション、`CTaskDialog`します。

*strTitle*<br/>
[in]タイトル、`CTaskDialog`します。

*nIDCommandControlsFirst*<br/>
[in]最初のコマンドの文字列 ID。

*nIDCommandControlsLast*<br/>
[in]最後のコマンドの文字列 ID。

*nCommonButtons*<br/>
[in]追加するボタンのマスク、`CTaskDialog`します。

*nTaskDialogOptions*<br/>
[in]使用するオプションのセット、`CTaskDialog`します。

*strFooter*<br/>
[in]フッターとして使用する文字列。

### <a name="return-value"></a>戻り値

ユーザーによる選択に対応する整数。

### <a name="remarks"></a>Remarks

この静的メソッドでは、インスタンスを作成することができます、`CTaskDialog`クラスを明示的に作成せず、`CTaskDialog`コード内のオブジェクト。 あるためありません`CTaskDialog`オブジェクトの他の任意のメソッドを呼び出すことはできません、`CTaskDialog`を表示するこのメソッドを使用する場合、`CTaskDialog`をユーザーにします。

このメソッドは、アプリケーションのリソース ファイルからデータを使用して、コマンド ボタン コントロールを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドは、文字列テーブルの間で有効な各エントリのコマンド ボタン コントロールを追加します*nIDCommandControlsFirst*と*nCommandControlsLast*までの値。 これらのコマンド ボタン コントロールの文字列テーブル内の文字列がコントロールのキャプションと文字列 ID は、コントロールの ID です。

参照してください[CTaskDialog::SetOptions](#setoptions)有効なオプションの一覧についてはします。

`CTaskDialog` 、ユーザーは、コマンド リンク コントロールでは、一般的なボタンが選択または終了すると、終了、`CTaskDialog`します。 戻り値は、ユーザーがダイアログ ボックスを閉じた方法を示す識別子です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="taskdialogcallback"></a>  CTaskDialog::TaskDialogCallback

フレームワークは、さまざまな Windows メッセージへの応答でこのメソッドを呼び出します。

```
friend:
HRESULT TaskDialogCallback(
    HWND hWnd,
    UINT uNotification,
    WPARAM wParam,
    LPARAM lParam,
    LONG_PTR dwRefData);
```

### <a name="parameters"></a>パラメーター

*hwnd*<br/>
[in]ハンドル、`m_hWnd`用の構造、`CTaskDialog`します。

*uNotification*<br/>
[in]生成されたメッセージを示す通知コード。

*wParam*<br/>
[in]メッセージの詳細についてはします。

*lParam*<br/>
[in]メッセージの詳細についてはします。

*dwRefData*<br/>
[in]ポインター、`CTaskDialog`コールバック メッセージを適用するオブジェクト。

### <a name="return-value"></a>戻り値

特定の通知コードに依存します。 詳細については、次の「解説」を参照してください。

### <a name="remarks"></a>Remarks

既定の実装`TaskDialogCallback`特定のメッセージを処理し、呼び出し、適切な方法で、 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md)します。 など、TDN_BUTTON_CLICKED メッセージへの応答で`TaskDialogCallback`呼び出し[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)します。

値は、 *wParam*と*lParam*生成された特定のメッセージに依存します。 どちらか一方または両方の値を空にすることができます。 次の表は、サポートされている既定の通知と、値の*wParam*と*lParam*を表します。 派生クラスでは、このメソッドをオーバーライドする場合は、次の表に各メッセージのコールバック コードを実装する必要があります。

|通知メッセージ|*wParam*値|*lParam*値|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|使用しません。|使用しません。|
|TDN_NAVIGATED|使用しません。|使用しません。|
|TDN_BUTTON_CLICKED|コマンド ボタン コントロールの id。|使用しません。|
|TDN_HYPERLINK_CLICKED|使用しません。|A [LPCWSTR](/windows/desktop/WinProg/windows-data-types)のリンクを含む構造体。|
|TDN_TIMER|以降のミリ秒単位の時間、`CTaskDialog`が作成されたか、タイマーをリセットします。|使用しません。|
|TDN_DESTROYED|使用しません。|使用しません。|
|TDN_RADIO_BUTTON_CLICKED|ラジオ ボタンの id。|使用しません。|
|TDN_DIALOG_CONSTRUCTED|使用しません。|使用しません。|
|TDN_VERIFICATION_CLICKED|チェック ボックスがオンの場合は 1、0 でない場合。|使用しません。|
|TDN_HELP|使用しません。|使用しません。|
|TDN_EXPANDO_BUTTON_CLICKED|拡張領域が折りたたまれている場合は 0拡張テキストが表示されている場合 0 以外の値。|使用しません。|

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[チュートリアル: アプリケーションへの CTaskDialog の追加](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)

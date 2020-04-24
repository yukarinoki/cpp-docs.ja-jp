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
ms.openlocfilehash: 79f52d275d360cf8447b8977b8196ea5f95eacd8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752289"
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
|[ダイアログボックス::Cタスクダイアログ](#ctaskdialog)|`CTaskDialog` オブジェクトを構築します。|

### <a name="methods"></a>メソッド

|||
|-|-|
|[コントロールを追加します。](#addcommandcontrol)|コマンド ボタン コントロールを`CTaskDialog`に追加します。|
|[ダイアログ::ラジオボタンの追加](#addradiobutton)|ラジオ ボタンを に`CTaskDialog`追加します。|
|[ダイアログ::クリックコマンドコントロール](#clickcommandcontrol)|コマンド ボタン コントロールまたはコモン ボタンをプログラムでクリックします。|
|[ダイアログ::クリックラジオボタン](#clickradiobutton)|プログラムでオプション ボタンをクリックします。|
|[ダイアログ::Doモーダル](#domodal)|「`CTaskDialog`」を表示します。|
|[ボタン数を取得します。](#getcommonbuttoncount)|使用可能な共通ボタンの数を取得します。|
|[ダイアログ::一般的なボタンフラグを取得します。](#getcommonbuttonflag)|標準の Windows ボタンを、クラスに関連付けられている共通`CTaskDialog`のボタンの種類に変換します。|
|[をクリックします。](#getcommonbuttonid)|`CTaskDialog`クラスに関連付けられている一般的なボタンの種類のいずれかを標準の Windows ボタンに変換します。|
|[ダイアログボックス::Getオプション](#getoptions)|この`CTaskDialog`オプション フラグを返します。|
|[を選択しました。](#getselectedcommandcontrolid)|選択したコマンド ボタン コントロールを返します。|
|[をクリックします。](#getselectedradiobuttonid)|選択したラジオボタンを返します。|
|[をクリックします。](#getverificationcheckboxstate)|検証チェック ボックスの状態を取得します。|
|[ダイアログ::Isコマンドコントロールが有効です](#iscommandcontrolenabled)|コマンド ボタン コントロールまたは共通ボタンが有効かどうかを判断します。|
|[ボタンをクリックします。](#isradiobuttonenabled)|ラジオ ボタンが有効かどうかを判断します。|
|[をサポートしています。](#issupported)|アプリケーションを実行しているコンピューターが をサポートしているかどうかを判断`CTaskDialog`します。|
|[ダイアログ::コマンドコントロールを読み込む](#loadcommandcontrols)|文字列テーブルのデータを使用して、コマンド ボタン コントロールを追加します。|
|[ダイアログ::ロードラジオボタン](#loadradiobuttons)|文字列テーブルのデータを使用して、ラジオ ボタンを追加します。|
|[タスクダイアログ::ナビゲート](#navigateto)|フォーカスを別`CTaskDialog`の .|
|[ダイアログ::コマンドコントロールクリック](#oncommandcontrolclick)|ユーザーがコマンド ボタン コントロールをクリックすると、フレームワークはこのメソッドを呼び出します。|
|[タスクダイアログ::オンCreate](#oncreate)|フレームワークは、作成後にこのメソッドを`CTaskDialog`呼び出します。|
|[Cタスクダイアログ::オンデストロイ](#ondestroy)|フレームワークは、このメソッドを呼び出す直前`CTaskDialog`に、 を破棄します。|
|[ボタンをクリックします。](#onexpandbuttonclick)|フレームワークは、ユーザーが展開ボタンをクリックすると、このメソッドを呼び出します。|
|[ダイアログ::オンヘルプ](#onhelp)|フレームワークは、ユーザーがヘルプを要求したときにこのメソッドを呼び出します。|
|[ダイアログ::ハイパーリンク上クリック](#onhyperlinkclick)|ユーザーがハイパーリンクをクリックすると、フレームワークはこのメソッドを呼び出します。|
|[タスクダイアログ::オンイニト](#oninit)|フレームワークは、初期化時にこの`CTaskDialog`メソッドを呼び出します。|
|[ダイアログ::オンナビゲートページ](#onnavigatepage)|フレームワークは、ユーザーがのコントロールに対してフォーカスを移動するときに、このメソッド`CTaskDialog`を呼び出します。|
|[ダイアログ::オンラジオボタンクリック](#onradiobuttonclick)|ユーザーがラジオ ボタン コントロールを選択すると、フレームワークはこのメソッドを呼び出します。|
|[ダイアログ::オンタイマー](#ontimer)|フレームワークは、タイマーの有効期限が切れるとこのメソッドを呼び出します。|
|[Cタスクダイアログ::オン検証チェックボックスクリック](#onverificationcheckboxclick)|フレームワークは、ユーザーが検証チェック ボックスをクリックしたときにこのメソッドを呼び出します。|
|[ダイアログ::すべてのコマンドコントロールを削除します。](#removeallcommandcontrols)|からすべてのコマンド コントロールを削除します`CTaskDialog`。|
|[ボタンをクリックします。](#removeallradiobuttons)|からすべてのラジオ ボタンを削除します`CTaskDialog`。|
|[ダイアログボックス::コマンドコントロールオプションを設定します。](#setcommandcontroloptions)|のコマンド ボタン コントロールを`CTaskDialog`更新します。|
|[ダイアログ::セットコモンボタンオプション](#setcommonbuttonoptions)|有効にする共通ボタンのサブセットを更新し、UAC の昇格を必要とします。|
|[ダイアログ::セットコモンボタン](#setcommonbuttons)|共通のボタンを`CTaskDialog`に追加します。|
|[ダイアログ::コンテンツを設定します。](#setcontent)|の内容を更新します`CTaskDialog`。|
|[コントロールを設定します。](#setdefaultcommandcontrol)|既定のコマンド ボタン コントロールを指定します。|
|[ダイアログ::デフォルトラジオボタンを設定します。](#setdefaultradiobutton)|既定のオプション ボタンを指定します。|
|[ダイアログボックス::ダイアログ幅の設定](#setdialogwidth)|の幅を調整します`CTaskDialog`。|
|[ダイアログ::拡張エリア](#setexpansionarea)|の拡張領域を更新します`CTaskDialog`。|
|[ダイアログボックス::フッターアイコン](#setfootericon)|のフッター アイコンを更新`CTaskDialog`します。|
|[ダイアログ::フッターテキスト](#setfootertext)|のフッターのテキストを更新します`CTaskDialog`。|
|[をクリックします。](#setmainicon)|のメイン アイコンを更新`CTaskDialog`します。|
|[ダイアログ::セットメイン命令](#setmaininstruction)|の主な命令を更新`CTaskDialog`します。|
|[ダイアログ::オプションを設定します。](#setoptions)|のオプションを構成します`CTaskDialog`。|
|[ダイアログ::セットプログレスバーマーキー](#setprogressbarmarquee)|のマーキー バーを構成`CTaskDialog`し、ダイアログ ボックスに追加します。|
|[ダイアログボックス::設定されたバーの位置](#setprogressbarposition)|プログレス バーの位置を調整します。|
|[ダイアログ::設定プログレスバー範囲](#setprogressbarrange)|プログレス バーの範囲を調整します。|
|[ダイアログ::設定プログレスバーステート](#setprogressbarstate)|プログレス バーの状態を設定し、`CTaskDialog`に表示します。|
|[ダイアログ::設定ラジオボタンオプション](#setradiobuttonoptions)|ラジオ ボタンを有効または無効にします。|
|[をクリックします。](#setverificationcheckbox)|検証チェック ボックスのチェック状態を設定します。|
|[をクリックします。](#setverificationcheckboxtext)|検証チェック ボックスの右側にテキストを設定します。|
|[ウィンドウのタイトルを設定します。](#setwindowtitle)|のタイトルを設定します`CTaskDialog`。|
|[ダイアログを表示します。](#showdialog)|を作成して表示`CTaskDialog`します。|
|[をクリックします。](#taskdialogcallback)|フレームワークは、さまざまな Windows メッセージに応答してこれを呼び出します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|`m_aButtons`|のコマンド ボタン コントロールの配列`CTaskDialog`。|
|`m_aRadioButtons`|のラジオ ボタン コントロールの配列`CTaskDialog`。|
|`m_bVerified`|`TRUE`検証チェック ボックスがオンになっていることを示します。`FALSE`は、そうではない場合を示します。|
|`m_footerIcon`|のフッターのアイコン。 `CTaskDialog`|
|`m_hWnd`|のウィンドウへのハンドル`CTaskDialog`。|
|`m_mainIcon`|のメイン アイコン。 `CTaskDialog`|
|`m_nButtonDisabled`|無効にする共通ボタンを示すマスク。|
|`m_nButtonElevation`|UAC の昇格が必要な共通のボタンを示すマスク。|
|`m_nButtonId`|選択したコマンド ボタン コントロールの ID。|
|`m_nCommonButton`|に表示される共通のボタンを示すマスク。 `CTaskDialog`|
|`m_nDefaultCommandControl`|表示されるときに選択されるコマンド ボタン コントロールの`CTaskDialog`ID。|
|`m_nDefaultRadioButton`|表示時に選択されるラジオ ボタン コントロールの`CTaskDialog`ID。|
|`m_nFlags`|のオプションを示すマスク。 `CTaskDialog`|
|`m_nProgressPos`|プログレス バーの現在位置。  この値の有効値の範囲は `m_nProgressRangeMin` ～ `m_nProgressRangeMax` です。|
|`m_nProgressRangeMax`|プログレス バーの最大値。|
|`m_nProgressRangeMin`|プログレス バーの最小値。|
|`m_nProgressState`|プログレス バーの状態。 詳細については[、「C タスク ダイアログ::設定の進行状況バーステート](#setprogressbarstate)」を参照してください。|
|`m_nRadioId`|選択したラジオ ボタン コントロールの ID。|
|`m_nWidth`|`CTaskDialog` の幅 (ピクセル単位)。|
|`m_strCollapse`|展開された情報`CTaskDialog`が非表示の場合に、展開ボックスの右側に表示される文字列。|
|`m_strContent`|のコンテンツ文字列`CTaskDialog`。|
|`m_strExpand`|展開された情報`CTaskDialog`が表示されるときに、展開ボックスの右側に表示される文字列。|
|`m_strFooter`|のフッター。 `CTaskDialog`|
|`m_strInformation`|の展開された情報です`CTaskDialog`。|
|`m_strMainInstruction`|の主な指示です`CTaskDialog`。|
|`m_strTitle`|`CTaskDialog` のタイトル。|
|`m_strVerification`|検証チェック ボックス`CTaskDialog`の右側に表示される文字列。|

## <a name="remarks"></a>解説

この`CTaskDialog`クラスは、標準の Windows メッセージ ボックスを置き換え、ユーザーから情報を収集する新しいコントロールなどの追加機能を備えています。 このクラスは、Visual Studio 2010 以降の MFC ライブラリにあります。 は`CTaskDialog`、Windows Vista 以降で使用できます。 以前のバージョンの Windows`CTaskDialog`では、オブジェクトを表示できません。 現在`CTaskDialog::IsSupported`のユーザーがタスク ダイアログ ボックスを表示できるかどうかを実行時に確認するために使用します。 標準の Windows メッセージ ボックスは引き続きサポートされています。

は`CTaskDialog`、Unicode ライブラリを使用してアプリケーションをビルドする場合にのみ使用できます。

には`CTaskDialog`2 つの異なるコンストラクターがあります。 1 つのコンストラクターを使用すると、2 つのコマンド ボタンと最大 6 つの標準ボタン コントロールを指定できます。 を作成した後で、さらにコマンド ボタン`CTaskDialog`を追加できます。 2 番目のコンストラクターでは、コマンド ボタンはサポートされていませんが、標準のボタン コントロールを無制限に追加できます。 コンストラクターの詳細については[、「CTaskDialog::CTaskDialog](#ctaskdialog)」を参照してください。

次の図は、いくつかの`CTaskDialog`コントロールの場所を示すサンプルを示しています。

![CTaskDialog の例](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialog の例") <br/>
Cタスクダイアログのサンプル

## <a name="requirements"></a>必要条件

**最低限必要なオペレーティング システム:** ウィンドウズビスタ

**ヘッダー:** afxtaskdialog.h

## <a name="ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a>コントロールを追加します。

新しいコマンド ボタン コントロールを`CTaskDialog`に追加します。

```cpp
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>パラメーター

*を制御します。*<br/>
[in]コマンド制御識別番号。

*strキャプション*<br/>
[in]ユーザーに`CTaskDialog`表示される文字列。 この文字列を使用して、コマンドの目的を説明します。

*b有効*<br/>
[in]新しいボタンが有効か無効かを示すブール値パラメーター。

*必要な標高*<br/>
[in]コマンドに標高が必要かどうかを示すブール値パラメーター。

### <a name="remarks"></a>解説

コマンド`CTaskDialog Class`ボタン コントロールの数に制限はありません。 ただし、コマンド`CTaskDialog`ボタン コントロールが表示される場合は、最大 6 つのボタンを表示できます。 コマンド`CTaskDialog`ボタン コントロールがない場合は、無制限の数のボタンを表示できます。

ユーザーがコマンド ボタン コントロールを選択すると、`CTaskDialog`閉じます。 アプリケーションで[CTaskDialog::DoModal](#domodal)を使用してダイアログ ボックス`DoModal`を表示する場合は、選択したコマンド ボタン コントロールの*nCommandControlID*を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a>ダイアログ::ラジオボタンの追加

ラジオ ボタンを に`CTaskDialog`追加します。

```cpp
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>パラメーター

*ラジオボタンID*<br/>
[in]ラジオ ボタンの ID 番号。

*strキャプション*<br/>
[in]ラジオ ボタンの`CTaskDialog`横に表示される文字列。

*b有効*<br/>
[in]ラジオ ボタンが有効かどうかを示すブール値パラメーター。

### <a name="remarks"></a>解説

[CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)のラジオ ボタンを使用すると、ユーザーから情報を収集できます。 関数[CTaskDialog::GetSelectedRadioButtonID を](#getselectedradiobuttonid)使用して、どのラジオ ボタンが選択されているかを判断します。

`CTaskDialog` *nRadioButtonID*パラメータが各ラジオ ボタンに対して一意である必要はありません。 ただし、各ラジオ ボタンに個別の識別子を使用しないと、予期しない動作が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a>ダイアログ::クリックコマンドコントロール

コマンド ボタン コントロールまたはコモン ボタンをプログラムでクリックします。

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>パラメーター

*を制御します。*<br/>
[in]クリックするコントロールのコマンド ID。

### <a name="remarks"></a>解説

このメソッドは、ウィンドウ のメッセージ TDM_CLICK_BUTTONを生成します。

## <a name="ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a>ダイアログ::クリックラジオボタン

プログラムでオプション ボタンをクリックします。

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>パラメーター

*ラジオボタンID*<br/>
[in]クリックするラジオ ボタンの ID。

### <a name="remarks"></a>解説

このメソッドは、ウィンドウ メッセージ TDM_CLICK_RADIO_BUTTONを生成します。

## <a name="ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a>ダイアログボックス::Cタスクダイアログ

[クラス](../../mfc/reference/ctaskdialog-class.md)のインスタンスを作成します。

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

*コンテンツ*<br/>
[in]の内容に使用する文字列。 `CTaskDialog`

*命令*<br/>
[in]の主な指示です`CTaskDialog`。

*strタイトル*<br/>
[in]のタイトル`CTaskDialog`。

*コモンボタン*<br/>
[in]に追加する共通ボタンの`CTaskDialog`マスク。

*オプション*<br/>
[in]に使用するオプションのセット`CTaskDialog`。

*フッター*<br/>
[in]フッターとして使用する文字列。

*最初にコマンドを実行します。*<br/>
[in]最初のコマンドの文字列 ID。

*最後に実行する*<br/>
[in]最後のコマンドの文字列 ID。

### <a name="remarks"></a>解説

アプリケーションに を`CTaskDialog`追加するには、2 つの方法があります。 最初の方法は、コンストラクターの 1 つを使用して`CTaskDialog`を作成し[、CTaskDialog::DoModal](#domodal)を使用して表示する方法です。 2 つ目の方法は、静的関数[CTaskDialog::ShowDialog](#showdialog)を使用して、`CTaskDialog``CTaskDialog`オブジェクトを明示的に作成せずにを表示できるようにします。

2 番目のコンストラクターは、アプリケーションのリソース ファイルのデータを使用してコマンド ボタン コントロールを作成します。 リソース ファイルの文字列テーブルには、関連する文字列 ID を持つ文字列が複数あります。 このメソッドは、文字列テーブルの有効なエントリごとにコマンド ボタン*コントロールを**追加*します。 これらのコマンド ボタン コントロールの場合、文字列テーブル内の文字列はコントロールのキャプションで、文字列 ID はコントロールの ID です。

有効なオプションの一覧については[、CTaskDialog::SetOptions](#setoptions)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogdomodal"></a><a name="domodal"></a>ダイアログ::Doモーダル

を`CTaskDialog`表示し、モーダルにします。

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>パラメーター

*h親*<br/>
[in]の親ウィンドウです`CTaskDialog`。

### <a name="return-value"></a>戻り値

ユーザーが選択した選択に対応する整数。

### <a name="remarks"></a>解説

このインスタンスを[表示します](../../mfc/reference/ctaskdialog-class.md)。 アプリケーションは、ユーザーがダイアログ ボックスを閉じるまで待機します。

ユーザー`CTaskDialog`が共通のボタン、コマンド リンク コントロールを選択するか、または`CTaskDialog`を閉じると、が閉じます。 戻り値は、ユーザーがダイアログ ボックスを閉じた方法を示す識別子です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a>ボタン数を取得します。

共通ボタンの数を取得します。

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>戻り値

使用可能な共通ボタンの数。

### <a name="remarks"></a>解説

共通のボタンは[、CTaskDialog::CTaskDialog](#ctaskdialog)に提供する既定のボタンです。 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)は、ダイアログ ボックスの下部に沿ってボタンを表示します。

ボタンの列挙された一覧は、CommCtrl.h で提供されています。

## <a name="ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a>ダイアログ::一般的なボタンフラグを取得します。

標準の Windows ボタンを[、 CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)に関連付けられた共通のボタンの種類に変換します。

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>パラメーター

*ボタンId*<br/>
[in]標準の Windows ボタンの値。

### <a name="return-value"></a>戻り値

対応する`CTaskDialog`共通ボタンの値。 対応する共通ボタンがない場合、このメソッドは 0 を返します。

## <a name="ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a>をクリックします。

[CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)に関連付けられている一般的なボタンの種類の 1 つを標準の Windows ボタンに変換します。

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>パラメーター

*nフラグ*<br/>
[in]クラスに関連付けられている共通の`CTaskDialog`ボタンの種類。

### <a name="return-value"></a>戻り値

対応する標準 Windows ボタンの値。 対応する Windows ボタンがない場合、メソッドは 0 を返します。

## <a name="ctaskdialoggetoptions"></a><a name="getoptions"></a>ダイアログボックス::Getオプション

この`CTaskDialog`オプション フラグを返します。

```
int GetOptions() const;
```

### <a name="return-value"></a>戻り値

のフラグ。 `CTaskDialog`

### <a name="remarks"></a>解説

[CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)で使用できるオプションの詳細については[、「CTaskDialog::SetOptions](#setoptions)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a>を選択しました。

選択したコマンド ボタン コントロールを返します。

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>戻り値

現在選択されているコマンド ボタン コントロールの ID。

### <a name="remarks"></a>解説

ユーザーが選択したコマンド ボタンの ID を取得するために、このメソッドを使用する必要はありません。 その ID は[、CTaskDialog::DoModal](#domodal)または[CTaskDialog::ShowDialog](#showdialog)のいずれかによって返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a>をクリックします。

選択したラジオボタンを返します。

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>戻り値

選択したラジオ ボタンの ID。

### <a name="remarks"></a>解説

このメソッドは、ユーザーがダイアログ ボックスを閉じて、選択したラジオ ボタンを取得した後に使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a>をクリックします。

検証チェック ボックスの状態を取得します。

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>戻り値

チェック ボックスがオンの場合は TRUE、チェック ボックスがオンでない場合は FALSE。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a>ダイアログ::Isコマンドコントロールが有効です

コマンド ボタン コントロールまたはボタンが有効かどうかを判断します。

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>パラメーター

*を制御します。*<br/>
[in]テストするコマンド ボタン コントロールまたはボタンの ID。

### <a name="return-value"></a>戻り値

コントロールが有効な場合は TRUE、有効でない場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを使用して、コマンド ボタン コントロールと Class* の共通ボタンの両方`CTaskDialog`の使用可能性を確認できます。

*nCommandControlID*が共通`CTaskDialog`ボタンまたはコマンド ボタン コントロールの有効な識別子でない場合、このメソッドは例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a>ボタンをクリックします。

ラジオ ボタンが有効かどうかを判断します。

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>パラメーター

*ラジオボタンID*<br/>
[in]テストするラジオ ボタンの ID。

### <a name="return-value"></a>戻り値

オプション ボタンが有効になっている場合は TRUE、有効でない場合は FALSE。

### <a name="remarks"></a>解説

*nRadioButtonID*がラジオ ボタンの有効な識別子でない場合、このメソッドは例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogissupported"></a><a name="issupported"></a>をサポートしています。

アプリケーションを実行しているコンピューターが をサポートしているかどうかを判断`CTaskDialog`します。

```
static BOOL IsSupported();
```

### <a name="return-value"></a>戻り値

コンピュータがをサポートしている場合`CTaskDialog`は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数を使用して、アプリケーションを実行しているコンピューターがクラスをサポートしているかどうかを実行時`CTaskDialog`に確認します。 コンピュータが をサポートしていない場合`CTaskDialog`は、別の方法で情報をユーザーに伝える必要があります。 クラスをサポートしていないコンピューターで を`CTaskDialog`使用しようとすると、アプリケーションがクラッシュします。 `CTaskDialog`

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a>ダイアログ::コマンドコントロールを読み込む

文字列テーブルのデータを使用して、コマンド ボタン コントロールを追加します。

```cpp
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>パラメーター

*最初にコマンドを実行します。*<br/>
[in]最初のコマンドの文字列 ID。

*最後に実行する*<br/>
[in]最後のコマンドの文字列 ID。

### <a name="remarks"></a>解説

このメソッドは、アプリケーションのリソース ファイルのデータを使用してコマンド ボタン コントロールを作成します。 リソース ファイルの文字列テーブルには、関連する文字列 ID を持つ文字列が複数あります。 このメソッドを使用して追加された新しいコマンド ボタン コントロールは、コントロールのキャプションに文字列を使用し、コントロールの ID の文字列 ID を使用します。 選択された文字列の範囲は *、nID コマンド コントロールファースト*および*n コマンドコントロールスラスト*(両端を含む) によって提供されます。 範囲内に空のエントリがある場合、メソッドはそのエントリのコマンド ボタン コントロールを追加しません。

既定では、新しいコマンド ボタン コントロールは有効になっており、昇格は必要ありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a>ダイアログ::ロードラジオボタン

文字列テーブルのデータを使用して、ラジオ ボタン コントロールを追加します。

```cpp
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>パラメーター

*最初にラジオボタン*<br/>
[in]最初のラジオ ボタンの文字列 ID。

*最後の時間*<br/>
[in]最後のラジオ ボタンの文字列 ID。

### <a name="remarks"></a>解説

このメソッドは、アプリケーションのリソース ファイルのデータを使用して、ラジオ ボタンを作成します。 リソース ファイルの文字列テーブルには、関連する文字列 ID を持つ文字列が複数あります。 このメソッドを使用して追加された新しいラジオ ボタンは、ラジオ ボタンのキャプションの文字列と、ラジオ ボタンの ID の文字列 ID を使用します。 選択された文字列の範囲は *、nIDラジオボタンファースト*と*nラジオボタンラスト*によって提供されます。 範囲内に空のエントリがある場合、メソッドはそのエントリのラジオ ボタンを追加しません。

既定では、新しいラジオ ボタンが有効になっています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialognavigateto"></a><a name="navigateto"></a>タスクダイアログ::ナビゲート

フォーカスを別`CTaskDialog`の .

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>パラメーター

*oタスクダイアログ*<br/>
[in]`CTaskDialog`フォーカスを受け取る。

### <a name="remarks"></a>解説

このメソッドは`CTaskDialog`*、oTaskDialog*を表示するときに現在を非表示にします。 *oTaskDialog*は現在`CTaskDialog`の と同じ場所に表示されます。

## <a name="ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a>ダイアログ::コマンドコントロールクリック

ユーザーがコマンド ボタン コントロールをクリックすると、フレームワークはこのメソッドを呼び出します。

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>パラメーター

*を制御します。*<br/>
[in]ユーザーが選択したコマンド ボタン コントロールの ID。

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogoncreate"></a><a name="oncreate"></a>タスクダイアログ::オンCreate

フレームワークは、作成後にこのメソッドを`CTaskDialog`呼び出します。

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogondestroy"></a><a name="ondestroy"></a>Cタスクダイアログ::オンデストロイ

フレームワークは、このメソッドを呼び出す直前`CTaskDialog`に、 を破棄します。

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a>ボタンをクリックします。

フレームワークは、ユーザーが展開ボタンをクリックすると、このメソッドを呼び出します。

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>パラメーター

*b拡大*<br/>
[in]0 以外の値は、余分な情報が表示されていることを示します。0 は、追加情報が非表示であることを示します。

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogonhelp"></a><a name="onhelp"></a>ダイアログ::オンヘルプ

フレームワークは、ユーザーがヘルプを要求したときにこのメソッドを呼び出します。

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a>ダイアログ::ハイパーリンク上クリック

ユーザーがハイパーリンクをクリックすると、フレームワークはこのメソッドを呼び出します。

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>パラメーター

*ストルHref*<br/>
[in]ハイパーリンクを表す文字列。

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

このメソッドは、S_OKを返す前に[ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew)を呼び出します。

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogoninit"></a><a name="oninit"></a>タスクダイアログ::オンイニト

フレームワークは、初期化時にこの`CTaskDialog`メソッドを呼び出します。

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a>ダイアログ::オンナビゲートページ

フレームワークは[、CTaskDialog::NavigateTo](#navigateto)メソッドに応答してこのメソッドを呼び出します。

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a>ダイアログ::オンラジオボタンクリック

ユーザーがラジオ ボタン コントロールを選択すると、フレームワークはこのメソッドを呼び出します。

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>パラメーター

*ラジオボタンID*<br/>
[in]ユーザーがクリックしたラジオ ボタン コントロールの ID。

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogontimer"></a><a name="ontimer"></a>ダイアログ::オンタイマー

フレームワークは、タイマーの有効期限が切れるとこのメソッドを呼び出します。

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>パラメーター

*l時間*<br/>
[in]が作成されたか、タイマー`CTaskDialog`がリセットされてからの時間 (ミリ秒単位)。

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a>Cタスクダイアログ::オン検証チェックボックスクリック

フレームワークは、ユーザーが検証チェック ボックスをクリックしたときにこのメソッドを呼び出します。

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>パラメーター

*bチェック*<br/>
[in]TRUE は、検証チェック ボックスがオンになっていることを示します。FALSE は、それがないことを示します。

### <a name="return-value"></a>戻り値

既定の実装では、S_OKが返されます。

### <a name="remarks"></a>解説

カスタム動作を実装するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a>ダイアログ::すべてのコマンドコントロールを削除します。

からすべてのコマンド ボタン コントロールを削除`CTaskDialog`します。

```cpp
void RemoveAllCommandControls();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a>ボタンをクリックします。

からすべてのラジオ ボタンを削除します`CTaskDialog`。

```cpp
void RemoveAllRadioButtons();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a>ダイアログボックス::コマンドコントロールオプションを設定します。

のコマンド ボタン コントロールを`CTaskDialog`更新します。

```cpp
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>パラメーター

*を制御します。*<br/>
[in]更新するコマンド コントロールの ID。

*b有効*<br/>
[in]指定したコマンド ボタン コントロールが有効か無効かを示すブール値パラメーター。

*必要な標高*<br/>
[in]指定したコマンド ボタン コントロールに標高が必要かどうかを示すブール値パラメーター。

### <a name="remarks"></a>解説

このメソッドは、`CTaskDialog`コマンド ボタン コントロールを有効にするか、クラスに追加した後に昇格を必要とするかどうかを変更するために使います。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a>ダイアログ::セットコモンボタンオプション

有効にする共通ボタンのサブセットを更新し、UAC の昇格を要求します。

```cpp
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>パラメーター

*ボタンマスク*<br/>
[in]無効にする共通ボタンのマスク。

*n標高ボタンマスク*<br/>
[in]標高を必要とする共通のボタンのマスク。

### <a name="remarks"></a>解説

[CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)のインスタンスで使用できる共通のボタンを設定するには、コンストラクター [CTaskDialog::CTaskDialog](#ctaskdialog)とメソッド[CTaskDialog::SetCommonButtons](#setcommonbuttons)を使用します。 `CTaskDialog::SetCommonButtonOptions`新しい共通ボタンの追加はサポートしていません。

このメソッドを使用して、この`CTaskDialog`メソッドで使用できない共通ボタンを無効にしたり昇格したりすると、このメソッドは[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

このメソッドは、 が使用できる`CTaskDialog`が、以前に無効にされていた場合でも、 *nDisabledButtonMask*にはない任意のボタンを有効にします。 このメソッドは、同様の方法で標高を処理します: 共通ボタンが使用可能であるが *、nElevationButtonMask*に含まれていない場合は、共通ボタンを昇格を必要としないとして記録します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a>ダイアログ::セットコモンボタン

共通のボタンを`CTaskDialog`に追加します。

```cpp
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>パラメーター

*ボタンマスク*<br/>
[in]に追加するボタンのマスク。 `CTaskDialog`

*ボタンマスク*<br/>
[in]無効にするボタンのマスク。

*n標高ボタンマスク*<br/>
[in]標高を必要とするボタンのマスク。

### <a name="remarks"></a>解説

クラスのこのインスタンスの表示ウィンドウを作成した後は、この`CTaskDialog`メソッドを呼び出すことはできません。 このメソッドを実行すると、例外がスローされます。

*nButtonMask*で示されたボタンは、以前に追加された共通`CTaskDialog`のボタンをオーバーライドします。 *nButtonMask*に示されているボタンのみが使用できます。

*nDisabled ボタンマスク*または*nElevation ボタンマスク*に含まれているボタンが*nButtonMask*にない場合、このメソッドは[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

既定では、すべての共通ボタンが有効で、昇格は必要ありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcontent"></a><a name="setcontent"></a>ダイアログ::コンテンツを設定します。

の内容を更新します`CTaskDialog`。

```cpp
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>パラメーター

*コンテンツ*<br/>
[in]ユーザーに表示する文字列。

### <a name="remarks"></a>解説

クラスの`CTaskDialog`内容は、ダイアログ ボックスのメイン セクションでユーザーに表示されるテキストです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a>コントロールを設定します。

既定のコマンド ボタン コントロールを指定します。

```cpp
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>パラメーター

*を制御します。*<br/>
[in]既定のコマンド ボタン コントロールの ID。

### <a name="remarks"></a>解説

既定のコマンド ボタン コントロールは、 が`CTaskDialog`最初にユーザーに表示されるときに選択されるコントロールです。

このメソッドは *、nCommandControlID*で指定されたコマンド ボタン コントロールが見つからない場合に例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a>ダイアログ::デフォルトラジオボタンを設定します。

既定のオプション ボタンを指定します。

```cpp
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>パラメーター

*ラジオボタンID*<br/>
[in]デフォルトのラジオボタンの ID。

### <a name="remarks"></a>解説

デフォルトのラジオボタンは、ユーザーに初めて表示されるときに`CTaskDialog`選択されるボタンです。

このメソッドは *、nRadioButtonID*で指定されたオプション ボタンが見つからない場合に例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a>ダイアログボックス::ダイアログ幅の設定

の幅を調整します`CTaskDialog`。

```cpp
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
[in]ダイアログ ボックスの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

パラメータ*nWidth*は 0 以上である必要があります。 それ以外の場合、このメソッドは例外をスローします。

*nWidth*が 0 に設定されている場合、このメソッドはダイアログ ボックスを既定のサイズに設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a>ダイアログ::拡張エリア

の拡張領域を更新します`CTaskDialog`。

```cpp
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>パラメーター

*ストエキスパンド情報*<br/>
[in]ユーザーが展開ボタン`CTaskDialog`をクリックしたときにダイアログ ボックスの本文に表示される文字列。

*ラベルが折りたたまれています*<br/>
[in]展開領域が`CTaskDialog`折りたたまれているときに展開ボタンの横に表示される文字列。

*ストエキスパンドラベル*<br/>
[in]展開領域が`CTaskDialog`表示されるときに展開ボタンの横に表示される文字列。

### <a name="remarks"></a>解説

`CTaskDialog`クラスの拡張領域を使用すると、ユーザーに追加情報を提供できます。 拡張領域は、 のメイン部分`CTaskDialog`に位置し、タイトルとコンテンツ文字列のすぐ下にあります。

が最初`CTaskDialog`に表示されるとき、展開された情報は表示されず、拡張ボタン`strCollapsedLabel`の横に置きます。 ユーザーが展開ボタンをクリックすると、 `CTaskDialog` *strExpandedInformation が*表示され、ラベルが*strExpandedLabel*に変更されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootericon"></a><a name="setfootericon"></a>ダイアログボックス::フッターアイコン

のフッター アイコンを更新`CTaskDialog`します。

```cpp
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>パラメーター

*フッターアイコン*<br/>
[in]の新しいアイコン。 `CTaskDialog`

*アイコン*<br/>
[in]の新しいアイコン。 `CTaskDialog`

### <a name="remarks"></a>解説

フッター アイコンは[CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)の下部に表示されます。 フッター テキストを関連付けることができます。 フッター テキストは[、次の手順](#setfootertext)で変更できます。

このメソッドは、表示`CTaskDialog`される場合、または入力パラメーターが NULL の場合に[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

は`CTaskDialog`、フッター アイコン`HICON``LPCWSTR`としてのみ受け入れることができます。 これは、コンストラクターまたは[CTaskDialog::SetOptions](#setoptions)でオプション TDF_USE_HICON_FOOTERを設定することによって構成されます。 デフォルトでは、`CTaskDialog`フッターアイコンの入力タイプ`LPCWSTR`として使用するように設定されています。 このメソッドは、不適切な型を使用してアイコンを設定しようとすると、例外を生成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootertext"></a><a name="setfootertext"></a>ダイアログ::フッターテキスト

のフッターのテキストを更新します`CTaskDialog`。

```cpp
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
[in]フッターの新しいテキスト。

### <a name="remarks"></a>解説

フッター アイコンは、 の下部にあるフッター テキストの横`CTaskDialog`に表示されます。 フッター アイコンは[、次の手順](#setfootericon)で変更できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmainicon"></a><a name="setmainicon"></a>をクリックします。

のメイン アイコンを更新`CTaskDialog`します。

```cpp
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>パラメーター

*hメインアイコン*<br/>
[in]新しいアイコン。

*アイコン*<br/>
[in]新しいアイコン。

### <a name="remarks"></a>解説

このメソッドは、表示`CTaskDialog`される場合、または入力パラメーターが NULL の場合に[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

は`CTaskDialog`、メイン アイコン`HICON``LPCWSTR`としてのみ受け入れることができます。 これを構成するには、コンストラクターまたは[CTaskDialog::SetOptions](#setoptions)メソッドでTDF_USE_HICON_MAIN オプションを設定します。 既定では、`CTaskDialog`メイン アイコンの入力`LPCWSTR`タイプとして使用するように 構成されています。 このメソッドは、不適切な型を使用してアイコンを設定しようとすると、例外を生成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a>ダイアログ::セットメイン命令

の主な命令を更新`CTaskDialog`します。

```cpp
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>パラメーター

*str指示*<br/>
[in]新しい主な命令。

### <a name="remarks"></a>解説

`CTaskDialog`クラスの主な命令は、大きな太字フォントでユーザーに表示されるテキストです。 このダイアログ ボックスは、タイトル バーの下のダイアログ ボックスにあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetoptions"></a><a name="setoptions"></a>ダイアログ::オプションを設定します。

のオプションを構成します`CTaskDialog`。

```cpp
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>パラメーター

*オプションフラグ*<br/>
[in]に使用するフラグのセット`CTaskDialog`。

### <a name="remarks"></a>解説

このメソッドは、 の現在のオプションをすべて`CTaskDialog`クリアします。 現在のオプションを保持するには、まず[CTaskDialog::GetOptions](#getoptions)を使用してそれらのオプションを取得し、設定するオプションと組み合わせる必要があります。

次の表は、有効なオプションをすべて示しています。

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|でのハイパーリンクを有効`CTaskDialog`にします。|
|TDF_USE_HICON_MAIN|メイン アイコン`CTaskDialog`に を`HICON`使用するように を構成します。 代わりに、 を使用`LPCWSTR`します。|
|TDF_USE_HICON_FOOTER|フッター アイコン`CTaskDialog`に を`HICON`使用するように を構成します。 代わりに、 を使用`LPCWSTR`します。|
|TDF_ALLOW_DIALOG_CANCELLATION|キーボードを使用`CTaskDialog`するか、ダイアログ ボックスの右上隅にあるアイコンを使用して、**キャンセル**ボタンが有効になっていない場合でもを閉じるようにします。 このフラグが設定されていない場合に **[キャンセル]** ボタンが有効になっていない場合、ユーザーは、Alt + F4 キー、Esc キー、またはタイトル バーの閉じるボタンを使用してダイアログ ボックスを閉じることができません。|
|TDF_USE_COMMAND_LINKS|コマンド ボタン`CTaskDialog`コントロールを使用するように を構成します。|
|TDF_USE_COMMAND_LINKS_NO_ICON|コントロールの横`CTaskDialog`にアイコンを表示せずにコマンド ボタン コントロールを使用するように を構成します。 TDF_USE_COMMAND_LINKS_NO_ICONをTDF_USE_COMMAND_LINKSオーバーライドします。|
|TDF_EXPAND_FOOTER_AREA|拡張領域が現在拡張されていることを示します。|
|TDF_EXPANDED_BY_DEFAULT|拡張領域を既定で展開するかどうかを指定します。|
|TDF_VERIFICATION_FLAG_CHECKED|検証チェック ボックスが現在オンになっていることを示します。|
|TDF_SHOW_PROGRESS_BAR|進行状況バーを`CTaskDialog`表示するように を構成します。|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|進捗バーをマーキープログレスバーに設定します。 このオプションを有効にした場合は、TDF_SHOW_PROGRESS_BARが予期した動作をするように設定する必要があります。|
|TDF_CALLBACK_TIMER|`CTaskDialog`コールバック間隔が約 200 ミリ秒に設定されていることを示します。|
|TDF_POSITION_RELATIVE_TO_WINDOW|親ウィンドウ`CTaskDialog`を基準に中央に配置するように を設定します。 このフラグが有効でない場合`CTaskDialog`、モニターに対して中央に配置されます。|
|TDF_RTL_LAYOUT|右から左`CTaskDialog`への閲覧レイアウトの を構成します。|
|TDF_NO_DEFAULT_RADIO_BUTTON|表示された場合に、ラジオ ボタンが`CTaskDialog`選択されなくなったときに、このオプション ボタンが選択されていることを示します。|
|TDF_CAN_BE_MINIMIZED|ユーザーが`CTaskDialog`を最小化できるようにします。 このオプションをサポートするには、`CTaskDialog`モーダルにすることはできません。 MFC ではモードレス`CTaskDialog`をサポートしていないため、MFC はこのオプションをサポートしていません。|

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a>ダイアログ::セットプログレスバーマーキー

のマーキー バーを構成`CTaskDialog`し、ダイアログ ボックスに追加します。

```cpp
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>パラメーター

*b有効*<br/>
[in]マーキー バーを有効にするには TRUE。マーキーバーを無効にし、から削除するには`CTaskDialog`、FALSE を指定します。

*アンマーキースピード*<br/>
[in]マーキー バーの速度を示す整数。

### <a name="remarks"></a>解説

マーキーバーは、クラスのメインテキストの下`CTaskDialog`に表示されます。

マーキーバーの速度を設定するには *、nMarqueeSpeed*を使用します。値が大きい場合は、速度が遅くなります。 *nMarqueeSpeed*の値が 0 の場合、マーキー バーは Windows の既定の速度で移動します。

このメソッドは *、nMarqueeSpeed*が 0 より小さい場合に[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a>ダイアログボックス::設定されたバーの位置

プログレス バーの位置を調整します。

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>パラメーター

*経過中のポス*<br/>
[in]プログレス バーの位置。

### <a name="remarks"></a>解説

このメソッドは *、nProgressPos*がプログレス バーの範囲にない場合に[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。 プログレス バーの範囲を変更するには、[次の](#setprogressbarrange)手順を実行します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a>ダイアログ::設定プログレスバー範囲

プログレス バーの範囲を調整します。

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>パラメーター

*nレンジミン*<br/>
[in]プログレス バーの下限。

*nレンジマックス*<br/>
[in]プログレス バーの上限。

### <a name="remarks"></a>解説

プログレス バーの位置は *、nRangeMin*と*nRangeMax*に対する相対位置です。 たとえば *、nRangeMin*が 50 で*nRangeMax*が 100 の場合、75 の位置は進行状況バーの途中にあります。 プログレスバーの位置を設定するには[、CTaskDialog::SetProgressBarPosition](#setprogressbarposition)を使用します。

プログレス バーを表示するには、オプション TDF_SHOW_PROGRESS_BAR が有効になっている必要があり、TDF_SHOW_MARQUEE_PROGRESS_BARを有効にしていない必要があります。 このメソッドは、TDF_SHOW_PROGRESS_BARを自動的に設定し、TDF_SHOW_MARQUEE_PROGRESS_BARをクリアします。 [CTaskDialog::SetOptions](#setoptions)を使用して、[この](../../mfc/reference/ctaskdialog-class.md)インスタンスのオプションを手動で変更します。

このメソッドは *、nRangeMin*が*nRangeMax*より小さい場合に[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。 このメソッドは、 が既に表示`CTaskDialog`されており、マーキー進行状況バーがある場合にも例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a>ダイアログ::設定プログレスバーステート

プログレス バーの状態を設定し、`CTaskDialog`に表示します。

```cpp
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>パラメーター

*nステート*<br/>
[in]プログレス バーの状態。 可能な値については、「解説」を参照してください。

### <a name="remarks"></a>解説

このメソッドは、既に表示されており、マーキー進行状況`CTaskDialog`バーがある場合は[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

次の表は *、nState*の値を示しています。 いずれの場合も、プログレス バーは、指定された停止位置に達するまで、通常の色で塗りつぶされます。 その時点で、状態に基づいて色が変わります。

|||
|-|-|
|PBST_NORMAL|プログレス バーが塗りつぶ`CTaskDialog`された後は、バーの色は変更されません。 既定では、通常の色は緑です。|
|PBST_ERROR|プログレス バーが塗りつぶ`CTaskDialog`された後、バーの色がエラー色に変わります。 デフォルトでは、これは赤です。|
|PBST_PAUSED|プログレス バーが塗りつぶ`CTaskDialog`された後、バーの色が一時停止した色に変更されます。 デフォルトでは、これは黄色です。|

プログレス バーの停止位置を設定するには[、CTaskDialog:::SetProgressBarPosition](#setprogressbarposition)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a>ダイアログ::設定ラジオボタンオプション

ラジオ ボタンを有効または無効にします。

```cpp
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>パラメーター

*ラジオボタンID*<br/>
[in]ラジオ ボタン コントロールの ID。

*b有効*<br/>
[in]ラジオ ボタンを有効にする場合は TRUE。オプション ボタンを無効にする場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは *、nRadioButtonID*がラジオ ボタンの有効な ID でない場合に[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a>をクリックします。

検証チェック ボックスのチェック状態を設定します。

```cpp
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>パラメーター

*bチェック*<br/>
[in]TRUE を指定すると、 が表示されたときに`CTaskDialog`検証チェック ボックスがオンになります。FALSE を指定すると、検証チェック ボックスが`CTaskDialog`表示されるときにチェック ボックスがオフになります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a>をクリックします。

[検証] チェック ボックスの右側に表示されるテキストを設定します。

```cpp
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>パラメーター

*検証テキスト*<br/>
[in]このメソッドが検証チェック ボックスの横に表示されるテキスト。

### <a name="remarks"></a>解説

このメソッドは、クラスのこのインスタンスが既に表示されている場合に`CTaskDialog`[、ENSURE](diagnostic-services.md#ensure)マクロを使用して例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a>ウィンドウのタイトルを設定します。

のタイトルを設定します`CTaskDialog`。

```cpp
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>パラメーター

*ウィンドウタイトル*<br/>
[in]の新しいタイトル。 `CTaskDialog`

### <a name="remarks"></a>解説

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogshowdialog"></a><a name="showdialog"></a>ダイアログを表示します。

を作成して表示`CTaskDialog`します。

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

*コンテンツ*<br/>
[in]の内容に使用する文字列。 `CTaskDialog`

*命令*<br/>
[in]の主な指示です`CTaskDialog`。

*strタイトル*<br/>
[in]のタイトル`CTaskDialog`。

*最初にコマンドを実行します。*<br/>
[in]最初のコマンドの文字列 ID。

*最後に実行する*<br/>
[in]最後のコマンドの文字列 ID。

*コモンボタン*<br/>
[in]に追加するボタンのマスク。 `CTaskDialog`

*オプション*<br/>
[in]に使用するオプションのセット`CTaskDialog`。

*フッター*<br/>
[in]フッターとして使用する文字列。

### <a name="return-value"></a>戻り値

ユーザーが選択した選択に対応する整数。

### <a name="remarks"></a>解説

この静的メソッドを使用すると、コード内にオブジェクト`CTaskDialog`を明示的に作成せずに、`CTaskDialog`クラスのインスタンスを作成できます。 `CTaskDialog`オブジェクトがないため、このメソッドを使用して ユーザーに a`CTaskDialog`を表示する場合は、 の`CTaskDialog`他のメソッドを呼び出すことはできません。

このメソッドは、アプリケーションのリソース ファイルのデータを使用してコマンド ボタン コントロールを作成します。 リソース ファイルの文字列テーブルには、関連する文字列 ID を持つ文字列が複数あります。 このメソッドは、文字列テーブルの有効なエントリごとにコマンド ボタン*コントロールを**追加*します。 これらのコマンド ボタン コントロールの場合、文字列テーブル内の文字列はコントロールのキャプションで、文字列 ID はコントロールの ID です。

有効なオプションの一覧については[、CTaskDialog::SetOptions](#setoptions)を参照してください。

ユーザー`CTaskDialog`が共通のボタン、コマンド リンク コントロールを選択するか、または`CTaskDialog`を閉じると、が閉じます。 戻り値は、ユーザーがダイアログ ボックスを閉じた方法を示す識別子です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a>をクリックします。

フレームワークは、さまざまな Windows メッセージに応答してこのメソッドを呼び出します。

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

*Hwnd*<br/>
[in]の`m_hWnd`構造体へのハンドル`CTaskDialog`。

*通知*<br/>
[in]生成されたメッセージを指定する通知コード。

*wParam*<br/>
[in]メッセージの詳細。

*lParam*<br/>
[in]メッセージの詳細。

*データを取得します。*<br/>
[in]コールバック メッセージが`CTaskDialog`適用されるオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

特定の通知コードによって異なります。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

の既定の`TaskDialogCallback`実装では、特定のメッセージを処理し[、CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)の適切な On メソッドを呼び出します。 たとえば、TDN_BUTTON_CLICKED メッセージに応答して`TaskDialogCallback`[、CTaskDialog::コマンドコントロールクリックを](#oncommandcontrolclick)呼び出します。

*wParam*と*lParam*の値は、生成された特定のメッセージによって異なります。 これらの値のいずれかまたは両方を空にすることもできます。 次の表は、サポートされている既定の通知と *、wParam*と*lParam*の値が表す内容を示しています。 派生クラスでこのメソッドをオーバーライドする場合は、次の表に示す各メッセージのコールバック コードを実装する必要があります。

|通知メッセージ|*wパラム*値|*lパラム*値|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|使用されていません。|使用されていません。|
|TDN_NAVIGATED|使用されていません。|使用されていません。|
|TDN_BUTTON_CLICKED|コマンド ボタン コントロール ID。|使用されていません。|
|TDN_HYPERLINK_CLICKED|使用されていません。|リンクを含む[LPCWSTR](/windows/win32/WinProg/windows-data-types)構造体。|
|TDN_TIMER|が作成されたか、タイマー`CTaskDialog`がリセットされてからの時間 (ミリ秒単位)。|使用されていません。|
|TDN_DESTROYED|使用されていません。|使用されていません。|
|TDN_RADIO_BUTTON_CLICKED|ラジオ ボタン ID。|使用されていません。|
|TDN_DIALOG_CONSTRUCTED|使用されていません。|使用されていません。|
|TDN_VERIFICATION_CLICKED|チェック ボックスがオンの場合は 1、チェック ボックスがオンでない場合は 0。|使用されていません。|
|TDN_HELP|使用されていません。|使用されていません。|
|TDN_EXPANDO_BUTTON_CLICKED|展開領域が折りたたまれている場合は 0。展開テキストが表示される場合は、0 以外の値を指定します。|使用されていません。|

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[チュートリアル: アプリケーションへの CTaskDialog の追加](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)

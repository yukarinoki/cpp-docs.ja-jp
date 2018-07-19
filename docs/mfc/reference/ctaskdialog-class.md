---
title: CTaskDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2971293a61a662b789506bbc32923089097f962d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123215"
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
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|コマンド ボタン コントロールを追加、`CTaskDialog`です。|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|ラジオ ボタンを追加、`CTaskDialog`です。|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|プログラムで、コマンド ボタン コントロールや一般的なボタンをクリックします。|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|プログラムによって、ラジオ ボタンをクリックします。|  
|[CTaskDialog::DoModal](#domodal)|「`CTaskDialog`」を表示します。|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|使用できる一般的なボタンの数を取得します。|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|一般的なボタンの種類に Windows のボタンに関連付けられている標準の変換、`CTaskDialog`クラスです。|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|関連付けられている一般的なボタンの種類のいずれかに変換します、`CTaskDialog`クラスを標準 Windows ボタンをクリックします。|  
|[CTaskDialog::GetOptions](#getoptions)|このオプションのフラグを返します`CTaskDialog`です。|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|選択したコマンド ボタン コントロールを返します。|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|選択したオプション ボタンを返します。|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|確認のチェック ボックスの状態を取得します。|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|コマンド ボタン コントロールまたは一般的なボタンが有効かどうかを判断します。|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|ラジオ ボタンが有効になっているかどうかを判断します。|  
|[CTaskDialog::IsSupported](#issupported)|アプリケーションを実行しているコンピューターをサポートするかどうかを決定、`CTaskDialog`です。|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|ストリング テーブルからデータを使用してコマンド ボタン コントロールを追加します。|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|ストリング テーブルからデータを使用して、オプション ボタンを追加します。|  
|[CTaskDialog::NavigateTo](#navigateto)|別にフォーカスが移動`CTaskDialog`です。|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|フレームワークは、ユーザーがコマンド ボタン コントロールをクリックしたときに、このメソッドを呼び出します。|  
|[CTaskDialog::OnCreate](#oncreate)|フレームワークが作成された後、このメソッドを呼び出して、`CTaskDialog`です。|  
|[CTaskDialog::OnDestroy](#ondestroy)|破棄する前にすぐに、フレームワークはこのメソッドを呼び出して、`CTaskDialog`です。|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|フレームワークは、ユーザーが展開ボタンをクリックすると、このメソッドを呼び出します。|  
|[CTaskDialog::OnHelp](#onhelp)|フレームワークは、ユーザーがヘルプを要求すると、このメソッドを呼び出します。|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|フレームワークは、ユーザーがハイパーリンクをクリックしたときに、このメソッドを呼び出します。|  
|[CTaskDialog::OnInit](#oninit)|フレームワークがこのメソッドを呼び出すときに、`CTaskDialog`が初期化されます。|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|ユーザー コントロールに関してフォーカスを移動するときに、フレームワークはこのメソッドを呼び出して、`CTaskDialog`です。|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|フレームワークは、ユーザーがラジオ ボタン コントロールを選択したときに、このメソッドを呼び出します。|  
|[CTaskDialog::OnTimer](#ontimer)|フレームワークは、タイマーが切れたときに、このメソッドを呼び出します。|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|フレームワークは、ユーザーが確認のチェック ボックスをクリックしたときに、このメソッドを呼び出します。|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|すべてのコマンド コントロールが削除、`CTaskDialog`です。|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|すべてのオプション ボタンを削除、`CTaskDialog`です。|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|コマンド ボタン コントロールを更新プログラムを`CTaskDialog`です。|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|有効にして、UAC 昇格を要求するために一般的なボタンのサブセットを更新します。|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|一般的なボタンを追加、`CTaskDialog`です。|  
|[CTaskDialog::SetContent](#setcontent)|内容を更新、`CTaskDialog`です。|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|既定のコマンド ボタン コントロールを指定します。|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|既定のオプション ボタンを指定します。|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|幅を調整、`CTaskDialog`です。|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|拡張領域を更新、`CTaskDialog`です。|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|[フッター] アイコンを更新、`CTaskDialog`です。|  
|[CTaskDialog::SetFooterText](#setfootertext)|フッターにテキストを更新、`CTaskDialog`です。|  
|[CTaskDialog::SetMainIcon](#setmainicon)|メインのアイコンを更新、`CTaskDialog`です。|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|メインの命令を更新、`CTaskDialog`です。|  
|[CTaskDialog::SetOptions](#setoptions)|オプションを構成、`CTaskDialog`です。|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|構成のマーキー バー、`CTaskDialog`し、ダイアログ ボックスに追加します。|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|進行状況バーの位置を調整します。|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|進行状況バーの範囲を調整します。|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|進行状況バーの状態に設定し、それを表示、`CTaskDialog`です。|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|有効またはラジオ ボタンを無効にします。|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|確認のチェック ボックスのチェック状態を設定します。|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|確認のチェック ボックスの右側にあるテキストを設定します。|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|タイトルを設定、`CTaskDialog`です。|  
|[CTaskDialog::ShowDialog](#showdialog)|作成し、表示、`CTaskDialog`です。|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|フレームワークは、さまざまな Windows メッセージへの応答でこれを呼び出します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|`m_aButtons`|コマンド ボタンのコントロールの配列、`CTaskDialog`です。|  
|`m_aRadioButtons`|ラジオ ボタン コントロール用の配列、`CTaskDialog`です。|  
|`m_bVerified`|`TRUE` 確認のチェック ボックスがチェックを示します。`FALSE`なっていないことを示します。|  
|`m_footerIcon`|フッターに、アイコン、`CTaskDialog`です。|  
|`m_hWnd`|ウィンドウのハンドル、`CTaskDialog`です。|  
|`m_mainIcon`|メインのアイコン、`CTaskDialog`です。|  
|`m_nButtonDisabled`|指定する、一般的なボタンのマスクが無効になります。|  
|`m_nButtonElevation`|指定する、一般的なボタンのマスクは、UAC 昇格を要求します。|  
|`m_nButtonId`|選択したコマンドのボタン コントロールの ID。|  
|`m_nCommonButton`|一般的なボタンを示すマスクが表示されます、`CTaskDialog`です。|  
|`m_nDefaultCommandControl`|コマンド ボタンの ID を制御するがオンの場合、`CTaskDialog`が表示されます。|  
|`m_nDefaultRadioButton`|ラジオ ボタンの ID を制御するがオンの場合、`CTaskDialog`が表示されます。|  
|`m_nFlags`|マスクのオプションを示す、`CTaskDialog`です。|  
|`m_nProgressPos`|進行状況バーの現在位置。  この値の有効値の範囲は `m_nProgressRangeMin` ～ `m_nProgressRangeMax` です。|  
|`m_nProgressRangeMax`|進行状況バーの最大値。|  
|`m_nProgressRangeMin`|進行状況バーの最小値。|  
|`m_nProgressState`|進行状況バーの状態。 詳細については、次を参照してください。 [CTaskDialog::SetProgressBarState](#setprogressbarstate)です。|  
|`m_nRadioId`|選択したオプション ボタン コントロールの ID。|  
|`m_nWidth`|幅、 `CTaskDialog` (ピクセル単位)。|  
|`m_strCollapse`|文字列、`CTaskDialog`展開された情報が表示されていない場合、展開 ボックスの右側に表示されます。|  
|`m_strContent`|コンテンツの文字列、`CTaskDialog`です。|  
|`m_strExpand`|文字列、`CTaskDialog`展開された情報が表示されるときに、展開 ボックスの右側に表示されます。|  
|`m_strFooter`|フッター、`CTaskDialog`です。|  
|`m_strInformation`|展開情報、`CTaskDialog`です。|  
|`m_strMainInstruction`|メインの命令、`CTaskDialog`です。|  
|`m_strTitle`|タイトル、`CTaskDialog`です。|  
|`m_strVerification`|文字列を`CTaskDialog`確認のチェック ボックスの右側に表示されます。|  
  
## <a name="remarks"></a>Remarks  
 `CTaskDialog`クラスは、標準の Windows メッセージ ボックスに置き換えられますおり、ユーザーから情報を収集する新しいコントロールなどの追加機能。 このクラスは、MFC ライブラリで[!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]です。 `CTaskDialog`は Windows Vista 以降で使用できます。 Windows の以前のバージョンを表示できません、`CTaskDialog`オブジェクト。 使用して`CTaskDialog::IsSupported`を実行時に、現在のユーザーが、タスク ダイアログ ボックスを表示するかどうかを判断します。 標準 Windows メッセージ ボックスが引き続きサポート[!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]です。  
  
 `CTaskDialog`は Unicode ライブラリを使用して、アプリケーションをビルドするときにのみ使用できます。  
  
 `CTaskDialog`が異なる 2 つのコンス トラクターです。 1 つのコンス トラクターでは、2 つのコマンド ボタンと 6 つの標準ボタン コントロールの最大数を指定することができます。 さらにコマンド ボタンを追加するには、作成した後、`CTaskDialog`です。 2 番目のコンス トラクターは、コマンド ボタンをサポートしていませんが、無制限の数の標準ボタン コントロールを追加することができます。 コンス トラクターの詳細については、次を参照してください。 [CTaskDialog::CTaskDialog](#ctaskdialog)です。  
  
 次の図は、サンプル`CTaskDialog`を一部のコントロールの場所を示しています。  
  
 ![CTaskDialog の例](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
CTaskDialog の例  
  
## <a name="requirements"></a>必要条件  
 **必要なオペレーティング システムの最小:** Windows Vista  
  
 **ヘッダー:** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl  
 新しいコマンド ボタン コントロールを追加、`CTaskDialog`です。  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCommandControlID*  
 コマンド コントロールの識別番号。  
  
 [in]*strCaption*  
 文字列を`CTaskDialog`をユーザーに表示されます。 この文字列を使用して、コマンドの目的について説明します。  
  
 [in]*bEnabled*  
 新しいボタンが有効か無効になっているかどうかを示すブール値パラメーターです。  
  
 [in]*bRequiresElevation*  
 コマンドが昇格を必要とするかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>Remarks  
 `CTaskDialog Class`コマンド ボタン コントロールの無制限の数を表示できます。 ただし場合、`CTaskDialog`表示いずれかのコマンド ボタン コントロールで、最大 6 つのボタンを表示できます。 場合、`CTaskDialog`コマンド ボタン コントロールを持たず、ボタンの無制限の数を表示できます。  
  
 コマンド ボタン コントロールを選択すると、`CTaskDialog`を閉じます。 アプリケーションを使用して、ダイアログ ボックスが表示される場合[CTaskDialog::DoModal](#domodal)、`DoModal`を返します、 *nCommandControlID*選択したコマンド ボタンのコントロールです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="addradiobutton"></a>  CTaskDialog::AddRadioButton  
 ラジオ ボタンを追加、`CTaskDialog`です。  
  
```  
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nRadioButtonID*  
 オプション ボタンの識別番号。  
  
 [in]*strCaption*  
 文字列を`CTaskDialog`ラジオ ボタンの横に表示されます。  
  
 [in]*bEnabled*  
 ラジオ ボタンが有効になっているかどうかを示すブール値パラメーター。  
  
### <a name="remarks"></a>Remarks  
 ラジオ ボタンが配置、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)を使用すると、ユーザーから情報を収集します。 関数を使用して[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)いるラジオ ボタンが選択されているかを決定します。  
  
 `CTaskDialog`いる必要はありません、 *nRadioButtonID*パラメーターはオプション ボタンごとに一意です。 ただし、オプション ボタンごとに個別の識別子を使用しない場合に、予期しない動作が発生する可能性があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl  
 プログラムで、コマンド ボタン コントロールや一般的なボタンをクリックします。  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCommandControlID*  
 をクリックするコントロールのコマンド ID。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、windows メッセージ TDM_CLICK_BUTTON を生成します。  
  
##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton  
 プログラムによって、ラジオ ボタンをクリックします。  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nRadioButtonID*  
 ラジオ ボタンをクリックしての ID。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、windows メッセージ TDM_CLICK_RADIO_BUTTON を生成します。  
  
##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog  
 インスタンスを作成、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)です。  
  
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
 [in]*strContent*  
 コンテンツを使用する文字列を`CTaskDialog`です。  
  
 [in]*strMainInstruction*  
 メインの命令、`CTaskDialog`です。  
  
 [in]*されません*  
 タイトル、`CTaskDialog`です。  
  
 [in]*nCommonButtons*  
 追加する一般的なボタンのマスク、`CTaskDialog`です。  
  
 [in]*nTaskDialogOptions*  
 使用するオプションのセット、`CTaskDialog`です。  
  
 [in]*strFooter*  
 フッターに使用する文字列。  
  
 [in]*nIDCommandControlsFirst*  
 最初のコマンドの文字列 ID です。  
  
 [in]*nIDCommandControlsLast*  
 最後のコマンドの文字列 ID。  
  
### <a name="remarks"></a>Remarks  
 追加できる 2 つの方法、`CTaskDialog`をアプリケーションにします。 最初の方法が、コンス トラクターのいずれかを使用して作成するには、`CTaskDialog`しを使用して表示します。 [CTaskDialog::DoModal](#domodal)です。 2 番目の方法は、静的関数を使用する[CTaskDialog::ShowDialog](#showdialog)を使用すると、表示、`CTaskDialog`明示的に作成することがなく、`CTaskDialog`オブジェクト。  
  
 2 番目のコンス トラクターは、アプリケーションのリソース ファイルからデータを使用して、コマンド ボタン コントロールを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドは、文字列テーブルの間に有効な各エントリのコマンド ボタン コントロールを追加*nIDCommandControlsFirst*と*nCommandControlsLast*、包括的です。 これらのコマンド ボタン コントロールの文字列テーブル内の文字列は、コントロールのキャプションと文字列 ID は、コントロールの ID  
  
 参照してください[CTaskDialog::SetOptions](#setoptions)有効なオプションの一覧についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="domodal"></a>  CTaskDialog::DoModal  
 表示、`CTaskDialog`されモーダルになります。  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hParent*  
 親ウィンドウ、`CTaskDialog`です。  
  
### <a name="return-value"></a>戻り値  
 ユーザーによる選択に対応する整数。  
  
### <a name="remarks"></a>Remarks  
 このインスタンスが表示されます、 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md)です。 その後、アプリケーションは、ユーザーをダイアログ ボックスを閉じるまで待機します。  
  
 `CTaskDialog` 、ユーザーがコマンド リンク コントロールでは、共通のボタンを選択または終了すると、終了、`CTaskDialog`です。 戻り値は、ユーザーがダイアログ ボックスを閉じる方法を示す識別子です。  
  
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
 一般的なボタンが既定のボタンに提供する[CTaskDialog::CTaskDialog](#ctaskdialog)です。 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md) ダイアログ ボックスの下部にあるボタンが表示されます。  
  
 列挙されたボタンの一覧については、CommCtrl.h で提供されます。  
  
##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag  
 一般的なボタンの種類に Windows のボタンに関連付けられている標準の変換、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)です。  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nButtonId*  
 標準の Windows ボタンの値。  
  
### <a name="return-value"></a>戻り値  
 対応する値`CTaskDialog`一般的なボタンをクリックします。 対応する一般的なボタンがない場合、このメソッドは 0 を返します。  
  
##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId  
 関連付けられている一般的なボタンの種類のいずれかの変換、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)標準 Windows ボタンをクリックします。  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*指します*  
 一般的なボタンの種類に関連付けられている、`CTaskDialog`クラスです。  
  
### <a name="return-value"></a>戻り値  
 対応する標準の Windows ボタンの値。 対応する Windows ボタンがない場合は、このメソッドは 0 を返します。  
  
##  <a name="getoptions"></a>  CTaskDialog::GetOptions  
 このオプションのフラグを返します`CTaskDialog`です。  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フラグ、`CTaskDialog`です。  
  
### <a name="remarks"></a>Remarks  
 使用可能なオプションの詳細については、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)を参照してください[CTaskDialog::SetOptions](#setoptions)です。  
  
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
 このメソッドを使用して、ユーザーが選択したコマンド ボタンの ID を取得する必要はありません。 いずれかでその ID が返される[CTaskDialog::DoModal](#domodal)または[CTaskDialog::ShowDialog](#showdialog)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="getselectedradiobuttonid"></a>  CTaskDialog::GetSelectedRadioButtonID  
 選択したオプション ボタンを返します。  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したオプション ボタンの ID。  
  
### <a name="remarks"></a>Remarks  
 ユーザーが選択したオプション ボタンを取得する ダイアログ ボックスを閉じた後は、このメソッドを使用することができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState  
 確認のチェック ボックスの状態を取得します。  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 チェック ボックスがオンの場合、FALSE されていない場合は TRUE。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled  
 コマンド ボタン コントロールまたはボタンが有効かどうかを判断します。  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCommandControlID*  
 テストするコマンド ボタンのコントロールまたはボタンの ID。  
  
### <a name="return-value"></a>戻り値  
 コントロールが有効な場合、FALSE されていない場合は TRUE。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用するには両方のコマンド ボタン コントロールの可用性との共通のボタンを判断する、`CTaskDialog`クラス * です。  
  
 場合*nCommandControlID*共通のいずれかの有効な識別子ではありませんは、`CTaskDialog`ボタンまたはコマンド ボタン コントロールでは、このメソッドが例外をスローします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled  
 ラジオ ボタンが有効になっているかどうかを判断します。  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nRadioButtonID*  
 テストするラジオ ボタンの ID。  
  
### <a name="return-value"></a>戻り値  
 ラジオ ボタンが有効な場合、FALSE されていない場合は TRUE。  
  
### <a name="remarks"></a>Remarks  
 場合*nRadioButtonID*有効な識別子ではないのラジオ ボタンでは、このメソッドが例外をスローします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>  CTaskDialog::IsSupported  
 アプリケーションを実行しているコンピューターをサポートするかどうかを決定、`CTaskDialog`です。  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>戻り値  
 コンピューターをサポートしている場合は TRUE、`CTaskDialog`です。FALSE それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 この関数を使用して、アプリケーションを実行しているコンピューターをサポートしている場合、実行時に決定する、`CTaskDialog`クラスです。 コンピューターがサポートしていない場合、 `CTaskDialog`、別のユーザーに情報を伝達する方法を指定する必要があります。 使用しようとすると、アプリケーションがクラッシュする`CTaskDialog`サポートしていないコンピューターで、`CTaskDialog`クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls  
 ストリング テーブルからデータを使用してコマンド ボタン コントロールを追加します。  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nIDCommandControlsFirst*  
 最初のコマンドの文字列 ID です。  
  
 [in]*nIDCommandControlsLast*  
 最後のコマンドの文字列 ID。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、アプリケーションのリソース ファイルからデータを使用して、コマンド ボタン コントロールを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドを使用して追加された新しいコマンド ボタン コントロールは、コントロールの ID にコントロールのキャプションと文字列 ID の文字列を使用します。 選択されている文字列の範囲がによって提供される*nIDCommandControlsFirst*と*nCommandControlsLast*、包括的です。 範囲の空のエントリがある場合、メソッドはそのエントリのコマンド ボタン コントロールを追加できません。  
  
 既定では、新しいコマンド ボタン コントロールが有効になってされ、昇格は必要ありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons  
 ストリング テーブルからデータを使用してラジオ ボタン コントロールを追加します。  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nIDRadioButtonsFirst*  
 最初のラジオ ボタンの文字列 ID。  
  
 [in]*nIDRadioButtonsLast*  
 最後のラジオ ボタンの文字列 ID です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、アプリケーションのリソース ファイルからデータを使用して、オプション ボタンを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドを使用して追加された新しいラジオ ボタン、ラジオ ボタンのキャプションと文字列 ID のラジオ ボタンの ID の文字列を使用します。 選択されている文字列の範囲がによって提供される*nIDRadioButtonsFirst*と*nRadioButtonsLast*、包括的です。 範囲の空のエントリがある場合、メソッドはそのエントリのラジオ ボタンを追加できません。  
  
 既定では、新しいラジオ ボタンが有効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>  CTaskDialog::NavigateTo  
 別にフォーカスが移動`CTaskDialog`です。  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*oTaskDialog*  
 `CTaskDialog`フォーカスを受け取る。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは現在、隠ぺい`CTaskDialog`それを表示するとき、 *oTaskDialog*です。 *OTaskDialog*現在と同じ場所に表示される`CTaskDialog`です。  
  
##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick  
 フレームワークは、ユーザーがコマンド ボタン コントロールをクリックしたときに、このメソッドを呼び出します。  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCommandControlID*  
 ユーザーが選択したコマンド ボタン コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="oncreate"></a>  CTaskDialog::OnCreate  
 フレームワークが作成された後、このメソッドを呼び出して、`CTaskDialog`です。  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy  
 破棄する前にすぐに、フレームワークはこのメソッドを呼び出して、`CTaskDialog`です。  
  
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
 [in]*bExpanded*  
 余分な情報が表示されます。 0 以外の値を示します0 は、追加情報が非表示を示します。  
  
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
 [in]*strHref*  
 ハイパーリンクを表す文字列。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出す[ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) S_OK を返す前にします。  
  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="oninit"></a>  CTaskDialog::OnInit  
 フレームワークがこのメソッドを呼び出すときに、`CTaskDialog`が初期化されます。  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage  
 フレームワークでは、このメソッドを呼び出してへの応答、 [CTaskDialog::NavigateTo](#navigateto)メソッドです。  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick  
 フレームワークは、ユーザーがラジオ ボタン コントロールを選択したときに、このメソッドを呼び出します。  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nRadioButtonID*  
 ユーザーがクリックしたオプション ボタン コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="ontimer"></a>  CTaskDialog::OnTimer  
 フレームワークは、タイマーが切れたときに、このメソッドを呼び出します。  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lTime*  
 以降のミリ秒単位の時間、`CTaskDialog`が作成されたか、タイマーをリセットします。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick  
 フレームワークは、ユーザーが確認のチェック ボックスをクリックしたときに、このメソッドを呼び出します。  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bChecked*  
 TRUE は、確認のチェック ボックスが選択されていることを示しますFALSE は、にないことを示します。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム動作を実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls  
 すべてのコマンド ボタン コントロールを削除、`CTaskDialog`です。  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons  
 すべてのオプション ボタンを削除、`CTaskDialog`です。  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions  
 コマンド ボタン コントロールを更新プログラムを`CTaskDialog`です。  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCommandControlID*  
 更新するコマンド コントロールの ID。  
  
 [in]*bEnabled*  
 指定されたコマンド ボタン コントロールが有効か無効になっているかどうかを示すブール値パラメーターです。  
  
 [in]*bRequiresElevation*  
 指定されたコマンド ボタン コントロールに昇格が必要なかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>Remarks  
 コマンド ボタン コントロールを有効にまたはに追加された後に、昇格を必要とするかどうかを変更するには、このメソッドを使用して、`CTaskDialog`クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions  
 一般的なボタンを有効にして、UAC 昇格を要求のサブセットを更新します。  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nDisabledButtonMask*  
 無効にする一般的なボタンのマスク。  
  
 [in]*扱わ*  
 昇格が必要な一般的なボタンのマスク。  
  
### <a name="remarks"></a>Remarks  
 インスタンスに使用できる一般的なボタンを設定することができます、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)コンス トラクターを使用して、 [CTaskDialog::CTaskDialog](#ctaskdialog)とメソッド[CTaskDialog::SetCommonButtons](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` 新しいの一般的なボタンを追加することはできません。  
  
 このメソッドを無効または昇格がこれを利用できない一般的なボタンを使用する場合`CTaskDialog`、このメソッドを使用して例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロです。  
  
 このメソッドにより、使用可能ないずれかのボタン、`CTaskDialog`に含まれていないが、 *nDisabledButtonMask*無効であった場合でも、します。 このメソッドは、同様の方法で昇格をどのように処理: 一般的なボタンが使用できるに含まれていない場合は、昇格が必要としないとして一般的なボタンが記録*扱わ*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons  
 一般的なボタンを追加、`CTaskDialog`です。  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nButtonMask*  
 追加するボタンのマスク、`CTaskDialog`です。  
  
 [in]*nDisabledButtonMask*  
 無効にするボタンのマスク。  
  
 [in]*扱わ*  
 昇格が必要なボタンのマスク。  
  
### <a name="remarks"></a>Remarks  
 このインスタンスの表示ウィンドウの後にこのメソッドを呼び出すことはできません、`CTaskDialog`クラスを作成します。 この場合、このメソッドは例外をスローします。  
  
 によって示されるボタン*nButtonMask*に追加したすべての一般的なボタンを上書き、`CTaskDialog`です。 示されているボタンだけ*nButtonMask*を利用できます。  
  
 いずれか*nDisabledButtonMask*または*扱わ*に含まれていない、ボタンを含む*nButtonMask*、このメソッドは、を使用して例外をスロー[を確認してください](diagnostic-services.md#ensure)マクロです。  
  
 既定では、すべての一般的なボタンが有効で、昇格は必要ありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcontent"></a>  CTaskDialog::SetContent  
 内容を更新、`CTaskDialog`です。  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*strContent*  
 ユーザーに表示する文字列。  
  
### <a name="remarks"></a>Remarks  
 内容、`CTaskDialog`クラスは、ダイアログ ボックスのメインのセクションで、ユーザーに表示されるテキストです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl  
 既定のコマンド ボタン コントロールを指定します。  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCommandControlID*  
 既定値であるコマンド ボタン コントロールの ID。  
  
### <a name="remarks"></a>Remarks  
 既定のコマンド ボタン コントロールがコントロールを選択したときに、`CTaskDialog`をユーザーに最初に表示されます。  
  
 指定されたコマンド ボタン コントロールを見つけられない場合、このメソッドが例外をスロー *nCommandControlID*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton  
 既定のオプション ボタンを指定します。  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nRadioButtonID*  
 既定のオプション ボタンの ID です。  
  
### <a name="remarks"></a>Remarks  
 既定のオプション ボタンは、ボタンが選択されている場合に、`CTaskDialog`をユーザーに最初に表示されます。  
  
 指定されたオプション ボタンを見つけられない場合、このメソッドが例外をスロー *nRadioButtonID*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth  
 幅を調整、`CTaskDialog`です。  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nWidth*  
 ピクセル単位で、ダイアログ ボックスの幅。  
  
### <a name="remarks"></a>Remarks  
 パラメーター *nWidth* 0 以上にする必要があります。 それ以外の場合、このメソッドは、例外をスローします。  
  
 場合*nWidth*は、0 に設定します ダイアログ ボックスの既定のサイズにこのメソッドを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea  
 拡張領域を更新、`CTaskDialog`です。  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*strExpandedInformation*  
 文字列を`CTaskDialog`ユーザーに展開ボタンがクリックしたときに、ダイアログ ボックスの本文が表示されます。  
  
 [in]*strCollapsedLabel*  
 文字列を`CTaskDialog`展開された領域が折りたたまれているときに、拡張ボタンの横にあるが表示されます。  
  
 [in]*strExpandedLabel*  
 文字列を`CTaskDialog`展開された領域が表示されるときに拡張ボタンの横に表示されます。  
  
### <a name="remarks"></a>Remarks  
 拡張領域、`CTaskDialog`クラスでは、追加情報をユーザーに提供することができます。 拡張領域がの主要部分では、 `CTaskDialog`, タイトルと内容の文字列のすぐ下にあります。  
  
 ときに、`CTaskDialog`を最初に展開された情報を表示しないと表示は、`strCollapsedLabel`展開ボタンの横にあります。 展開ボタンをクリックする、`CTaskDialog`表示*strExpandedInformation*にラベルを変更および*strExpandedLabel*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon  
 [フッター] アイコンを更新、`CTaskDialog`です。  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hFooterIcon*  
 新しいアイコン、`CTaskDialog`です。  
  
 [in]*lpszFooterIcon*  
 新しいアイコン、`CTaskDialog`です。  
  
### <a name="remarks"></a>Remarks  
 下部にあるページ フッターのアイコンが表示されます、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)です。 関連付けることができますフッターのテキスト。 フッター テキストを変更することができます[CTaskDialog::SetFooterText](#setfootertext)です。  
  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ場合、`CTaskDialog`が表示されますか、入力パラメーターが NULL です。  
  
 A`CTaskDialog`のみを受け入れることができます、`HICON`または`LPCWSTR`フッター アイコンとして。 これはコンス トラクターで TDF_USE_HICON_FOOTER オプションを設定して構成または[CTaskDialog::SetOptions](#setoptions)です。 既定では、`CTaskDialog`を使用するように構成`LPCWSTR`フッター アイコンの入力の型として。 このメソッドは、不適切な型を使用してアイコンを設定しようとする場合に例外を生成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText  
 フッターにテキストを更新、`CTaskDialog`です。  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*strFooterText*  
 フッターの新しいテキスト。  
  
### <a name="remarks"></a>Remarks  
 下部でフッター テキストの横にあるフッター アイコンが表示されます、`CTaskDialog`です。 ページ フッターの付いたアイコンを変更することができます[CTaskDialog::SetFooterIcon](#setfootericon)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon  
 メインのアイコンを更新、`CTaskDialog`です。  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hMainIcon*  
 新しいアイコン。  
  
 [in]*lpszMainIcon*  
 新しいアイコン。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ場合、`CTaskDialog`が表示されますか、入力パラメーターが NULL です。  
  
 A`CTaskDialog`のみを受け入れることができます、`HICON`または`LPCWSTR`メイン アイコンとして。 これを構成するには、コンス トラクターで TDF_USE_HICON_MAIN オプションの設定やで、 [CTaskDialog::SetOptions](#setoptions)メソッドです。 既定では、`CTaskDialog`を使用するように構成`LPCWSTR`メイン アイコンの入力の型として。 このメソッドは、不適切な型を使用してアイコンを設定しようとする場合に例外を生成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction  
 メインの命令を更新、`CTaskDialog`です。  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*strInstructions*  
 新しいメイン命令です。  
  
### <a name="remarks"></a>Remarks  
 メインの命令、`CTaskDialog`クラスは、大規模な太字のフォントでユーザーに表示されるテキストです。 ダイアログ ボックスで、タイトル バーの下にあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setoptions"></a>  CTaskDialog::SetOptions  
 オプションを構成、`CTaskDialog`です。  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nOptionFlag*  
 使用するフラグのセット、`CTaskDialog`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはすべて現在のオプションをクリア、`CTaskDialog`です。 現在のオプションを保持するために取得する必要に最初に[CTaskDialog::GetOptions](#getoptions)し、それらを設定するオプションを使用して結合します。  
  
 次の表では、有効なオプションをすべて一覧表示します。  
  
 TDF_ENABLE_HYPERLINKS  
 内のハイパーリンクを有効に、`CTaskDialog`です。  
  
 TDF_USE_HICON_MAIN  
 構成、`CTaskDialog`を使用する、`HICON`メインのアイコン。 代替手段は、使用する、`LPCWSTR`です。  
  
 TDF_USE_HICON_FOOTER  
 構成、`CTaskDialog`を使用する、`HICON`フッターのアイコン。 代替手段は、使用する、`LPCWSTR`です。  
  
 TDF_ALLOW_DIALOG_CANCELLATION  
 閉じることができます、`CTaskDialog`キーボードを使用して、またはダイアログ ボックスの右上隅のアイコンを使用して場合でも、**キャンセル**ボタンが有効になっていません。 このフラグが設定されていない場合、**キャンセル**ボタンが有効になっていない、ユーザーは、alt キーを押しながら f4 キー、Esc キーを使用して、ダイアログ ボックスを閉じることはできません、またはタイトル バーの [閉じる] ボタン。  
  
 TDF_USE_COMMAND_LINKS  
 構成、`CTaskDialog`コマンド ボタン コントロールを使用します。  
  
 TDF_USE_COMMAND_LINKS_NO_ICON  
 構成、`CTaskDialog`コマンド ボタン コントロールを使用して、コントロールの横にアイコンを表示せずにします。 TDF_USE_COMMAND_LINKS TDF_USE_COMMAND_LINKS_NO_ICON をオーバーライドします。  
  
 TDF_EXPAND_FOOTER_AREA  
 拡張領域が現在展開されていることを示します。  
  
 TDF_EXPANDED_BY_DEFAULT  
 既定では、拡張領域が展開されているかどうかを判断します。  
  
 TDF_VERIFICATION_FLAG_CHECKED  
 確認のチェック ボックスが現在選択されていることを示します。  
  
 TDF_SHOW_PROGRESS_BAR  
 構成、`CTaskDialog`進行状況バーを表示します。  
  
 TDF_SHOW_MARQUEE_PROGRESS_BAR  
 マーキーの進行状況バーに進行状況バーを構成します。 このオプションを有効にする場合は、予想されるように動作する TDF_SHOW_PROGRESS_BAR を設定してください。  
  
 TDF_CALLBACK_TIMER  
 示します、`CTaskDialog`コールバック間隔は約 200 ミリ秒に設定します。  
  
 TDF_POSITION_RELATIVE_TO_WINDOW  
 構成、`CTaskDialog`親ウィンドウに対して相対的に中央揃えにします。 このフラグが有効でない場合、`CTaskDialog`モニター相対中央に配置します。  
  
 TDF_RTL_LAYOUT  
 構成、`CTaskDialog`レイアウトの右から左への読み取り。  
  
 TDF_NO_DEFAULT_RADIO_BUTTON  
 ラジオ ボタンが選択されていないことを示すときに、`CTaskDialog`が表示されます。  
  
 TDF_CAN_BE_MINIMIZED  
 最小限に抑えることができます、`CTaskDialog`です。 このオプションをサポートするために、`CTaskDialog`モーダルにすることはできません。 MFC がこのオプションをサポートしていない MFC は、モードレスをサポートしていないため`CTaskDialog`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee  
 構成のマーキー バー、`CTaskDialog`し、ダイアログ ボックスに追加します。  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnabled*  
 マーキー バー; を有効にする場合は TRUEマーキー バーを無効にしてから削除する場合は FALSE、`CTaskDialog`です。  
  
 [in]*nMarqueeSpeed*  
 マーキーのバーの速度を示す整数。  
  
### <a name="remarks"></a>Remarks  
 メイン テキストの下に marquee バーが表示されます、`CTaskDialog`クラスです。  
  
 使用して*nMarqueeSpeed* marquee バーの速度を設定するより大きな値を示す速度を遅くします。 値 0 を*nMarqueeSpeed* marquee バーが Windows の既定の速度で移動します。  
  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nMarqueeSpeed*が 0 未満です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition  
 進行状況バーの位置を調整します。  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nProgressPos*  
 進行状況バーの位置。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nProgressPos*進行状況バーの範囲ではありません。 進行状況バーの範囲を変更することができます[CTaskDialog::SetProgressBarRange](#setprogressbarrange)です。  
  
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
 [in]*nRangeMin*  
 進行状況バーの下限値です。  
  
 [in]*nRangeMax*  
 進行状況バーの上限です。  
  
### <a name="remarks"></a>Remarks  
 進行状況バーの位置は、に対して相対的な*nRangeMin*と*nRangeMax*です。 たとえば場合、 *nRangeMin* 50 および*nRangeMax* 100、75 の位置は、プログレス バー内の中間に位置します。 使用して[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)プログレス バーの位置を設定します。  
  
 進行状況バーを表示するには、TDF_SHOW_PROGRESS_BAR を有効にする必要がありますオプションと TDF_SHOW_MARQUEE_PROGRESS_BAR 有効にしないでください。 このメソッドは自動的に TDF_SHOW_PROGRESS_BAR を設定し、TDF_SHOW_MARQUEE_PROGRESS_BAR をクリアします。 使用して[CTaskDialog::SetOptions](#setoptions)を手動でのこのインスタンスのオプションを変更する、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)です。  
  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nRangeMin*はより小さくない*nRangeMax*です。 このメソッドは、場合も、例外をスロー、`CTaskDialog`既に表示されておりマーキーの進行状況バーです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState  
 進行状況バーの状態に設定し、それを表示、`CTaskDialog`です。  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*%n 状態*  
 進行状況バーの状態。 使用可能な値は、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ場合、`CTaskDialog`既に表示されておりマーキーの進行状況バーです。  
  
 次の表に、可能な値 *%n 状態*です。 これらすべてのケースで進行状況バーがいっぱいに通常の色を指定した位置に達するまでします。 その時点の状態に基づいて色が変更されます。  
  
 PBST_NORMAL  
 バーは塗りつぶさ進行状況の後に、`CTaskDialog`バーの色を変更することはできません。 既定では、通常の色は緑です。  
  
 PBST_ERROR  
 バーは塗りつぶさ進行状況の後に、`CTaskDialog`エラー カラー バーの色に変更します。 既定では、これは、赤です。  
  
 PBST_PAUSED  
 バーは塗りつぶさ進行状況の後に、`CTaskDialog`バーの色を一時停止中の色に変更します。 既定では、これは、黄色です。  
  
 進行状況バーが停止しを設定することができます[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)です。  
  
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
 [in]*nRadioButtonID*  
 ラジオ ボタン コントロールの ID。  
  
 [in]*bEnabled*  
 オプション ボタンを有効にする場合は TRUEオプション ボタンを無効にする場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)マクロ場合*nRadioButtonID*ラジオ ボタンの有効な ID ではありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox  
 確認のチェック ボックスのチェック状態を設定します。  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bChecked*  
 True を確認のチェック ボックス選択したときに、`CTaskDialog`が表示されます。チェック ボックスを検証する場合は FALSE の場合に選択を解除、`CTaskDialog`が表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText  
 確認のチェック ボックスの右側に表示されるテキストを設定します。  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*strVerificationText*  
 このメソッドは確認のチェック ボックスの横に表示されるテキスト。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで例外をスローする、[を確認してください](diagnostic-services.md#ensure)場合は、このマクロのインスタンス、`CTaskDialog`既にクラスが表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle  
 タイトルを設定、`CTaskDialog`です。  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*strWindowTitle*  
 新しいタイトル、`CTaskDialog`です。  
  
### <a name="remarks"></a>Remarks  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="showdialog"></a>  CTaskDialog::ShowDialog  
 作成し、表示、`CTaskDialog`です。  
  
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
 [in]*strContent*  
 コンテンツを使用する文字列を`CTaskDialog`です。  
  
 [in]*strMainInstruction*  
 メインの命令、`CTaskDialog`です。  
  
 [in]*されません*  
 タイトル、`CTaskDialog`です。  
  
 [in]*nIDCommandControlsFirst*  
 最初のコマンドの文字列 ID です。  
  
 [in]*nIDCommandControlsLast*  
 最後のコマンドの文字列 ID。  
  
 [in]*nCommonButtons*  
 追加するボタンのマスク、`CTaskDialog`です。  
  
 [in]*nTaskDialogOptions*  
 使用するオプションのセット、`CTaskDialog`です。  
  
 [in]*strFooter*  
 フッターに使用する文字列。  
  
### <a name="return-value"></a>戻り値  
 ユーザーによる選択に対応する整数。  
  
### <a name="remarks"></a>Remarks  
 この静的メソッドでは、インスタンスを作成することができます、`CTaskDialog`クラスを明示的に作成がない場合、`CTaskDialog`コード内のオブジェクト。 あるためありません`CTaskDialog`オブジェクトでの他の任意のメソッドを呼び出すことはできません、`CTaskDialog`を表示するこのメソッドを使用する場合、`CTaskDialog`をユーザーにします。  
  
 このメソッドは、アプリケーションのリソース ファイルからデータを使用して、コマンド ボタン コントロールを作成します。 リソース ファイル内の文字列テーブルには、関連付けられた文字列 Id いくつかの文字列があります。 このメソッドは、文字列テーブルの間に有効な各エントリのコマンド ボタン コントロールを追加*nIDCommandControlsFirst*と*nCommandControlsLast*、包括的です。 これらのコマンド ボタン コントロールの文字列テーブル内の文字列は、コントロールのキャプションと文字列 ID は、コントロールの ID  
  
 参照してください[CTaskDialog::SetOptions](#setoptions)有効なオプションの一覧についてはします。  
  
 `CTaskDialog` 、ユーザーがコマンド リンク コントロールでは、共通のボタンを選択または終了すると、終了、`CTaskDialog`です。 戻り値は、ユーザーがダイアログ ボックスを閉じる方法を示す識別子です。  
  
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
 [in]*hwnd*  
 ハンドル、`m_hWnd`の構造体、`CTaskDialog`です。  
  
 [in]*uNotification*  
 生成されたメッセージを示す通知コード。  
  
 [in]*wParam*  
 メッセージの詳細についてはします。  
  
 [in]*lParam*  
 メッセージの詳細についてはします。  
  
 [in]*dwRefData*  
 ポインター、`CTaskDialog`にコールバック メッセージを適用するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 特定の通知コードに依存します。 詳細については、次の「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 既定の実装`TaskDialogCallback`特定のメッセージを処理し、呼び出し、適切な方法で、 [CTaskDialog クラス](../../mfc/reference/ctaskdialog-class.md)です。 たとえば、TDN_BUTTON_CLICKED メッセージへの応答で`TaskDialogCallback`呼び出し[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)です。  
  
 値は、 *wParam*と*lParam*生成された特定のメッセージに依存します。 どちらか一方または両方のこれらの値を空にすることができます。 次の表は、サポートされている既定の通知と新機能の値*wParam*と*lParam*を表します。 派生クラスでは、このメソッドをオーバーライドする場合は、次の表に各メッセージのコールバック コードを実装する必要があります。  
  
|通知メッセージ|*wParam*値|*lParam*値|  
|--------------------------|--------------------|--------------------|  
|TDN_CREATED|使用しません。|使用しません。|  
|TDN_NAVIGATED|使用しません。|使用しません。|  
|TDN_BUTTON_CLICKED|コマンド ボタン コントロールの id。|使用しません。|  
|TDN_HYPERLINK_CLICKED|使用しません。|A [LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751)リンクを含む構造体。|  
|TDN_TIMER|以降のミリ秒単位の時間、`CTaskDialog`が作成されたか、タイマーをリセットします。|使用しません。|  
|TDN_DESTROYED|使用しません。|使用しません。|  
|TDN_RADIO_BUTTON_CLICKED|ラジオ ボタンの id。|使用しません。|  
|TDN_DIALOG_CONSTRUCTED|使用しません。|使用しません。|  
|TDN_VERIFICATION_CLICKED|チェック ボックスがオンの場合は 1、ない場合は 0 です。|使用しません。|  
|TDN_HELP|使用しません。|使用しません。|  
|TDN_EXPANDO_BUTTON_CLICKED|拡張領域が折りたたまれている場合は 0以外の場合は、拡張テキストが表示されます。|使用しません。|  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [チュートリアル: アプリケーションへの CTaskDialog の追加](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)




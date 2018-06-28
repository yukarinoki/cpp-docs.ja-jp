---
title: CMFCEditBrowseCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 495f6360601fc41493f68bd4fdd7ac769b9a634c
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037975"
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl クラス
`CMFCEditBrowseCtrl`クラスは、参照機能付きコントロール、これは、[参照] ボタンを含む (オプション) を編集可能なテキスト ボックスをサポートします。 ユーザーが参照ボタンをクリックすると、このコントロールはカスタム動作を実行するか、ファイル参照またはフォルダー参照を含む標準ダイアログ ボックスを表示します。  
  
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
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|有効または無効に (非表示にします)、[参照] ボタンをクリックします。|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|[参照] ボタンを有効にし、参照機能付きコントロール*ファイル参照*モード。|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|[参照] ボタンを有効にし、参照機能付きコントロール*フォルダー参照*モード。|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|現在のブラウズ モードを返します。|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|参照操作の結果を含む参照機能付きコントロールを更新した後に、フレームワークによって呼び出されます。|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|ユーザーが、参照ボタンをクリックした後に、フレームワークによって呼び出されます。|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|現在の参照機能付きコントロールを再描画します。|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|[参照] ボタンを描画するためにフレームワークによって呼び出されます。|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|無効なファイル名が編集コントロールに入力されたときに、フレームワークによって呼び出されます。|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数。 構文や詳細については、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)です。|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|[参照] ボタンのカスタム イメージを設定します。|  
  
## <a name="remarks"></a>Remarks  
 参照機能付きコントロールを使用すると、ファイルまたはフォルダーの名前を選択します。 必要に応じて、コントロールを使用して、ダイアログ ボックスを表示するようにカスタム アクションを実行します。 表示したり、[参照] ボタンは表示されませんし、ボタンにカスタム ラベルまたはイメージを適用することができます。  
  
 *ブラウズ モード*参照機能付きコントロールが決まります [参照] ボタンを表示するかどうかと、どのようなアクション ボタンがクリックされたときに発生します。 詳細については、次を参照してください。、 [GetMode](#getmode)メソッドです。  
  
 `CMFCEditBrowseCtrl`クラスは、次のモードをサポートします。  
  
 `custom mode`  
 カスタム アクションは、ユーザーが、参照ボタンをクリックしたときに実行されます。 たとえば、アプリケーション固有のダイアログ ボックスを表示することができます。  
  
 `file mode`  
 ユーザーが、参照ボタンをクリックしたときに、標準のファイルの選択 ダイアログ ボックスが表示されます。  
  
 `folder mode`  
 ユーザーが、参照ボタンをクリックしたときに、標準のフォルダーの選択 ダイアログ ボックスが表示されます。  
  
## <a name="how-to-specify-an-edit-browse-control"></a>方法: 参照機能付きコントロールを指定します。  
 アプリケーションの参照機能付きコントロールを組み込むには、次の手順を実行します。  
  
1.  カスタム参照モードを実装する場合は、派生クラスから、`CMFCEditBrowseCtrl`クラスをオーバーライドし、 [CMFCEditBrowseCtrl::OnBrowse](#onbrowse)メソッドです。 オーバーライドされたメソッドでカスタム参照アクションを実行し、結果で参照機能付きコントロールを更新します。  
  
2.  いずれかを埋め込む、`CMFCEditBrowseCtrl`オブジェクトまたは親ウィンドウ オブジェクトには、派生編集参照コントロール オブジェクトです。  
  
3.  使用する場合、**クラス ウィザード**エディット コントロールの追加 ダイアログ ボックスを作成する ( `CEdit`) ダイアログ ボックスのフォームにします。 また、ヘッダー ファイルでコントロールにアクセスする変数を追加します。 変数の型を変更すると、ヘッダー ファイルで`CEdit`に`CMFCEditBrowseCtrl`です。 参照機能付きコントロールが自動的に作成されます。 使用しない場合、**クラス ウィザード**、追加、`CMFCEditBrowseCtrl`変数ヘッダー ファイルと、呼び出しをその`Create`メソッドです。  
  
4.  ダイアログ ボックスに、参照機能付きコントロールを追加する場合を使用して、 **ClassWizard**データ交換を設定するツールです。  
  
5.  呼び出す、 [EnableFolderBrowseButton](#enablefolderbrowsebutton)、 [EnableFileBrowseButton](#enablefilebrowsebutton)、または[EnableBrowseButton](#enablebrowsebutton)ブラウズ モードを設定し、[参照] ボタンを表示します。 呼び出す、 [GetMode](#getmode)現在ブラウズ モードを取得します。  
  
6.  [参照] ボタンをカスタム イメージを提供する、 [SetBrowseButtonImage](#setbrowsebuttonimage)メソッドまたは上書き、 [OnDrawBrowseButton](#ondrawbrowsebutton)メソッドです。  
  
7.  参照機能付きコントロールから、[参照] ボタンを削除するには、呼び出し、 [EnableBrowseButton](#enablebrowsebutton)メソッドを*bEnable*パラメーターに設定`FALSE`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>例  
 次の例では、次の 2 つのメソッドを使用して、`CMFCEditBrowseCtrl`クラス:`EnableFolderBrowseButton`と`EnableFileBrowseButton`です。 この例の一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxeditbrowsectrl.h  
  
##  <a name="enablebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableBrowseButton  
 表示または現在の参照機能付きコントロールでは、参照ボタンは表示されません。  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnable*  
 `TRUE` [参照] ボタンを表示するには`FALSE` [参照] ボタンを表示しないようにします。 既定値は `TRUE` です。  
  
 *szLabel*  
 [参照] ボタンに表示されるラベルです。 既定値は" **.**".  
  
### <a name="remarks"></a>Remarks  
 場合、 *bEnable*パラメーターは`TRUE`、[参照] ボタンがクリックされたときに実行するカスタム アクションを実装します。 カスタム動作を実装するのには、派生クラスを`CMFCEditBrowseCtrl`クラスをオーバーライドし、その[OnBrowse](#onbrowse)メソッドです。  
  
 場合、`bEnable`パラメーターは`TRUE`、コントロールのブラウズ モードは`BrowseMode_Default`以外の場合、ブラウズ モードは`BrowseMode_None`します。 ブラウズ モードの詳細については、次を参照してください。、 [GetMode](#getmode)メソッドです。  
  
##  <a name="enablefilebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFileBrowseButton  
 現在の参照機能付きコントロールで参照ボタンを表示し、コントロールを*ファイル参照*モード。  
  
```  
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,  
    LPCTSTR lpszFilter=NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszDefExt*  
 [ファイルの選択] ダイアログ ボックスで使用する既定のファイル名拡張子を指定します。 既定値は `NULL` です。  
  
 *lpszFilter*  
 [ファイルの選択] ダイアログ ボックスで使用する既定のフィルター文字列を指定します。 既定値は `NULL` です。  
  
 *dwFlags*  
 ダイアログ ボックスのフラグ。 既定値は OFN_HIDEREADONLY と OFN_OVERWRITEPROMPT のビットごとの組み合わせ (OR) です。  
  
### <a name="remarks"></a>Remarks  
 参照機能付きコントロールがファイル参照モードのときにユーザーが [参照] ボタンをクリックすると、コントロールに標準的なファイル選択のダイアログ ボックスが表示されます。  
  
 使用可能なフラグの一覧については、次を参照してください。 [OPENFILENAME 構造体](https://msdn.microsoft.com/library/ms646839.aspx)です。  
  
##  <a name="enablefolderbrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 現在の参照機能付きコントロールで参照ボタンを表示し、コントロールを*フォルダー参照*モード。  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>Remarks  
 フォルダー参照モードでは、参照機能付きコントロール、ユーザーが、参照ボタンをクリックして、ときに、コントロールは標準のフォルダーの選択 ダイアログ ボックスを表示します。  
  
##  <a name="getmode"></a>  CMFCEditBrowseCtrl::GetMode  
 現在の参照機能付きコントロールのブラウズ モードを取得します。  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 編集の現在のモードを指定する列挙値の 1 つは、コントロールを参照します。 ブラウズ モードは、フレームワークは、参照ボタンを表示するかどうかと、ユーザーがそのボタンをクリックしたときに発生する動作を決定します。  
  
 次の表は、可能性のある戻り値の一覧です。  
  
|[値]|説明|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`。 プログラマが定義したアクションは実行されます。|  
|`BrowseMode_File`|`file mode`。 標準的なファイル ブラウザー ダイアログ ボックスが表示されます。|  
|`BrowseMode_Folder`|`folder mode`。 標準フォルダ ブラウザー ダイアログ ボックスが表示されます。|  
|`BrowseMode_None`|[参照] ボタンは表示されません。|  
  
### <a name="remarks"></a>Remarks  
 既定では、`CMFCEditBrowseCtrl`オブジェクトが初期化`BrowseMode_None`モード。 ブラウズ モードでの変更、 [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)、 [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)、および[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)メソッドです。  
  
##  <a name="onafterupdate"></a>  CMFCEditBrowseCtrl::OnAfterUpdate  
 参照操作の結果を含む参照機能付きコントロールを更新した後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>Remarks  
 カスタム アクションを実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="onbrowse"></a>  CMFCEditBrowseCtrl::OnBrowse  
 ユーザーが参照機能付きコントロールの参照ボタンをクリックした後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用すると、ユーザーが参照機能付きコントロールの参照ボタンをクリックしたときに、カスタム コードを実行します。 独自のクラスを派生させる、`CMFCEditBrowseCtrl`クラスし、オーバーライドの`OnBrowse`メソッドです。 このメソッドでカスタム参照アクションを実装し、必要に応じて参照機能付きコントロールのテキスト ボックスを更新します。 アプリケーションで使用して、 [EnableBrowseButton](#enablebrowsebutton)メソッドに参照機能付きコントロールを配置する*カスタム参照*モード。  
  
##  <a name="onchangelayout"></a>  CMFCEditBrowseCtrl::OnChangeLayout  
 現在の参照機能付きコントロールを再描画します。  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、ブラウズ モードの参照機能付きコントロール変更されるときに、このメソッドを呼び出します。 詳細については、次を参照してください。 [CMFCEditBrowseCtrl::GetMode](#getmode)です。  
  
##  <a name="ondrawbrowsebutton"></a>  CMFCEditBrowseCtrl::OnDrawBrowseButton  
 参照機能付きコントロールに、参照ボタンを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsButtonPressed,  
    BOOL bIsButtonHot);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 デバイス コンテキストへのポインター。  
  
 *rect*  
 [参照] ボタンの外接する四角形。  
  
 *bIsButtonPressed*  
 `TRUE` 場合は、ボタンが押されたです。それ以外の場合、`FALSE`です。  
  
 *bIsButtonHot*  
 `TRUE` 場合は、ボタンが強調表示されます。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 [参照] ボタンの外観をカスタマイズする派生クラスでは、この関数をオーバーライドします。  
  
##  <a name="setbrowsebuttonimage"></a>  CMFCEditBrowseCtrl::SetBrowseButtonImage  
 参照機能付きコントロールの参照ボタンをカスタム イメージを設定します。  
  
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
 *hIcon*  
 アイコンのハンドル。  
  
 *hBitmap*  
 ビットマップのハンドル。  
  
 *uiBmpResId*  
 ビットマップのリソース ID です。  
  
 *bAutoDestroy*  
 `TRUE` このメソッドを終了時に指定されたアイコンまたはビットマップを削除するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>Remarks  
 [参照] ボタンにカスタム イメージを適用するのにには、このメソッドを使用します。 既定では、フレームワークときに取得する標準的なイメージでは、参照機能付きコントロール*ファイル参照*または*フォルダー参照*モード。  
  
##  <a name="onillegalfilename"></a>  CMFCEditBrowseCtrl::OnIllegalFileName  
 無効なファイル名が編集コントロールに入力されたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 *strFileName*  
 無効なファイル名を指定します。  
  
### <a name="return-value"></a>戻り値  
 返す必要があります`FALSE`場合は、ファイル ダイアログをさらにこのファイル名を渡すことはできません。 ここでは、エディット コントロールにフォーカスが戻ります設定し、ユーザーが編集を続行する必要があります。 既定の実装が無効なファイル名のバージョン情報をユーザーに示すメッセージ ボックスを表示しを返します`FALSE`です。 このメソッドをオーバーライドして、ファイル名を修正および返す`TRUE`さらに処理します。  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

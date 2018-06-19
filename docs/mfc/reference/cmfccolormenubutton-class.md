---
title: CMFCColorMenuButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c19386aeac0d85565ae7834a881d710d9226ef9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370706"
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton クラス
`CMFCColorMenuButton`メニュー コマンドまたはツールバーのボタン、カラー ピッカー ダイアログ ボックスを起動するクラスをサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|`CMFCColorMenuButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|有効にし、通常の色のボタンの上に配置する「自動」ボタンを無効にします。 (標準のシステムの自動ボタンのラベルは**自動**)。|  
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|システム カラーではなくドキュメント固有の色の表示を有効にします。|  
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|有効にし、標準のカラー ボタンの下にある、"other"ボタンを無効にします。 ("のその他"ボタンのラベルは、標準的なシステム**他の色**)。|  
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|色ウィンドウのティアオフ機能を有効にします。|  
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|現在の自動の色を取得します。|  
|[CMFCColorMenuButton::GetColor](#getcolor)|現在のボタンの色を取得します。|  
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|指定されたコマンド ID に対応する色を取得します。|  
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|親ウィンドウが変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|色の選択 ダイアログ ボックスを開きます。|  
|[CMFCColorMenuButton::SetColor](#setcolor)|現在のカラー ボタンの色を設定します。|  
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|指定した色のメニュー ボタンの色を設定します。|  
|[CMFCColorMenuButton::SetColorName](#setcolorname)|指定した色の新しい名前を設定します。|  
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|によって表示される列の数を設定、`CMFCColorBar`オブジェクト。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|現在のボタンに別のツール バー ボタンをコピーします。|  
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|カラー ピッカー ダイアログ ボックスを作成します。|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|空のメニューがサポートされているかどうかを示します。|  
|[CMFCColorMenuButton::OnDraw](#ondraw)|ボタンの画像を表示するためにフレームワークによって呼び出されます。|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|前にフレームワークによって呼び出されます、`CMFCColorMenuButton`オブジェクトは、ツールバーのカスタマイズ ダイアログ ボックスの一覧に表示されます。|  
  
## <a name="remarks"></a>コメント  
 元のメニュー コマンドまたはツール バー ボタンを置換する、`CMFCColorMenuButton`オブジェクトを作成、`CMFCColorMenuButton`オブジェクト、設定、適切な[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)スタイル、および、呼び出し、 `ReplaceButton` のメソッド[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラスです。 ツールバーをカスタマイズする場合、 [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)メソッドです。  
  
 カラー ピッカー ダイアログ ボックスがの処理中に作成された、 [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)イベント ハンドラー。 イベント ハンドラーで親フレームに通知する`WM_COMMAND`メッセージ。 `CMFCColorMenuButton`オブジェクトは、元のメニュー コマンドまたはツール バー ボタンに割り当てられているコントロールの ID を送信します。  
  
## <a name="example"></a>例  
 次の例で作成およびのさまざまなメソッドを使用して、色のメニュー ボタンを構成する方法、`CMFCColorMenuButton`クラスです。 例では、`CPalette`オブジェクトが最初に作成され、オブジェクトの構築を使用して、`CMFCColorMenuButton`クラスです。 `CMFCColorMenuButton`オブジェクトが、自動ボタンとその他のボタンを有効にし、色と列の数を設定して構成されます。 このコードの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolormenubutton.h  
  
##  <a name="cmfccolormenubutton"></a>  CMFCColorMenuButton::CMFCColorMenuButton  
 `CMFCColorMenuButton` オブジェクトを構築します。  
  
```  
CMFCColorMenuButton();

 
CMFCColorMenuButton(
    UINT uiCmdID,  
    LPCTSTR lpszText,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 ボタン コマンド id。  
  
 [入力] `lpszText`  
 ボタンのテキスト。  
  
 [入力] `pPalette`  
 ボタンの色パレットへのポインター。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 最初のコンス トラクターは、既定のコンス トラクターです。 オブジェクトの現在の色と自動の色は黒 (RGB (0, 0, 0)) に初期化されます。  
  
 2 番目のコンス トラクターは、指定されたコマンド ID に対応する色のボタンを初期化します  
  
##  <a name="copyfrom"></a>  CMFCColorMenuButton::CopyFrom  
 1 つをコピー [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)-別の派生オブジェクト。  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 ソース コピーする をクリックします。  
  
### <a name="remarks"></a>コメント  
 派生したオブジェクトをコピーするには、このメソッドをオーバーライドして、`CMFCColorMenuButton`オブジェクト。  
  
##  <a name="createpopupmenu"></a>  CMFCColorMenuButton::CreatePopupMenu  
 カラー ピッカー ダイアログ ボックスを作成します。  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>戻り値  
 カラー ピッカー ダイアログ ボックスを表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは色のメニュー ボタンを押したときにフレームワークによって呼び出されます。  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorMenuButton::EnableAutomaticButton  
 有効にし、通常の色のボタンの上に配置する「自動」ボタンを無効にします。 (標準のシステムの自動ボタンのラベルは**自動**)。  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ボタンが自動的になったときに表示されるボタンのテキストを指定します。  
  
 [入力] `colorAutomatic`  
 新しい自動の色を指定します。  
  
 [入力] `bEnable`  
 ボタンが自動であるかどうかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 自動ボタンには、現在の既定の色が適用されます。  
  
##  <a name="enabledocumentcolors"></a>  CMFCColorMenuButton::EnableDocumentColors  
 システム カラーではなくドキュメント固有の色の表示を有効にします。  
  
```  
void EnableDocumentColors(
    LPCTSTR lpszLabel,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ボタンのテキストを指定します。  
  
 [入力] `bEnable`  
 `TRUE` ドキュメントに固有の色を表示するか、`FALSE`システム カラーを表示します。  
  
### <a name="remarks"></a>コメント  
 ユーザーがカラー メニュー ボタンをクリックしたときに、現在のドキュメントの色またはシステム パレットの色を表示するのにには、このメソッドを使用します。  
  
##  <a name="enableotherbutton"></a>  CMFCColorMenuButton::EnableOtherButton  
 有効にし、標準のカラー ボタンの下にある、"other"ボタンを無効にします。 ("のその他"ボタンのラベルは、標準的なシステム**他の色**)。  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ボタンのテキストを指定します。  
  
 [入力] `bAltColorDlg`  
 指定`TRUE`を表示する、`CMFCColorDialog`ダイアログ ボックスで、または`FALSE`標準のシステム カラー ダイアログ ボックスを表示します。  
  
 [入力] `bEnable`  
 指定`TRUE`、"other"ボタンを表示する場合は、`FALSE`です。 既定値は、`TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabletearoff"></a>  CMFCColorMenuButton::EnableTearOff  
 色ウィンドウのティアオフ機能を有効にします。  
  
```  
void EnableTearOff(
    UINT uiID,  
    int nVertDockColumns=-1,  
    int nHorzDockRows=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 ティアオフ ペインの ID を指定します。  
  
 [入力] `nVertDockColumns`  
 ティアオフ状態の間の垂直方向にドッキングされている色ウィンドウで列の数を指定します。  
  
 [入力] `nHorzDockRows`  
 ティアオフ状態の間に水平にドッキングされている色ウィンドウの行の数を指定します。  
  
### <a name="remarks"></a>コメント  
 ときにポップアップ表示される色ウィンドウの「ティアオフ」機能を有効にするには、このメソッドを呼び出す、`CMFCColorMenuButton`ボタンが押されました。  
  
##  <a name="getautomaticcolor"></a>  CMFCColorMenuButton::GetAutomaticColor  
 現在の自動の色を取得します。  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の自動の色を表す RGB カラー値。  
  
### <a name="remarks"></a>コメント  
 によって設定される自動の色を取得するには、このメソッドを呼び出す[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)です。  
  
##  <a name="getcolor"></a>  CMFCColorMenuButton::GetColor  
 現在のボタンの色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンの色。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcolorbycmdid"></a>  CMFCColorMenuButton::GetColorByCmdID  
 指定されたコマンド ID に対応する色を取得します。  
  
```  
static COLORREF GetColorByCmdID(UINT uiCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 コマンド id。  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID に対応する色  
  
### <a name="remarks"></a>コメント  
 アプリケーションに複数のカラー ボタンがある場合は、このメソッドを使用します。 ユーザーには、色のボタンがクリックすると、ボタンは送信コマンド ID、`WM_COMMAND`親へのメッセージ。 `GetColorByCmdID`メソッドでは、コマンド ID を使用して、対応する色を取得します。  
  
##  <a name="isemptymenuallowed"></a>  CMFCColorMenuButton::IsEmptyMenuAllowed  
 空のメニューがサポートされているかどうかを示します。  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 空の場合は 0 以外のメニューは使用できません。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 空のメニューは、既定でサポートされます。 派生クラスでは、この動作を変更するには、このメソッドをオーバーライドします。  
  
##  <a name="onchangeparentwnd"></a>  CMFCColorMenuButton::OnChangeParentWnd  
 親ウィンドウが変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 新しい親ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondraw"></a>  CMFCColorMenuButton::OnDraw  
 ボタンの画像を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz=TRUE,  
    BOOL bCustomizeMode=FALSE,  
    BOOL bHighlight=FALSE,  
    BOOL bDrawBorder=TRUE,  
    BOOL bGrayDisabledButtons=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 再描画される領域に外接する四角形。  
  
 [入力] `pImages`  
 ツール バー イメージの一覧を指します。  
  
 [入力] `bHorz`  
 `TRUE` ツールバーが、水平のドッキング状態を指定するにはそれ以外の場合、`FALSE`です。 既定値は、`TRUE` です。  
  
 [入力] `bCustomizeMode`  
 `TRUE` アプリケーションがカスタマイズ モードであることを指定するにはそれ以外の場合、`FALSE`です。 既定値は、`FALSE` です。  
  
 [入力] `bHighlight`  
 `TRUE` ボタンがハイライトされているを指定するにはそれ以外の場合、`FALSE`です。 既定値は、`FALSE` です。  
  
 [入力] `bDrawBorder`  
 `TRUE` ボタンの境界線が表示されることを指定するにはそれ以外の場合、`FALSE`です。 既定値は、`TRUE` です。  
  
 [入力] `bGrayDisabledButtons`  
 `TRUE` 無効なを指定するボタンはグレーで表示される (淡色) です。それ以外の場合、`FALSE`です。 既定値は、`TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCColorMenuButton::OnDrawOnCustomizeList  
 前にフレームワークによって呼び出されます、`CMFCColorMenuButton`オブジェクトは、ツールバーのカスタマイズ ダイアログ ボックスの一覧に表示されます。  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 ボタンを描画する領域に外接する四角形。  
  
 [入力] `bSelected`  
 `TRUE` ボタンが選択した状態であることを指定しますそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 ボタンの幅。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、フレームワークによって呼び出さときに、`CMFCColorMenuButton`ツールバーのカスタマイズ プロセス中に、リスト ボックスでオブジェクトを表示します。  
  
##  <a name="opencolordialog"></a>  CMFCColorMenuButton::OpenColorDialog  
 色の選択 ダイアログ ボックスを開きます。  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `colorDefault`  
 色のダイアログ ボックスで選択されている既定の色。  
  
 [出力] `colorRes`  
 色のダイアログ ボックスで、ユーザーが選択した色を返します。  
  
### <a name="return-value"></a>戻り値  
 ユーザーが新しい色を選択した場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニュー ボタンがクリックされたときに、色のダイアログ ボックスを開くには、このメソッドを呼び出します。 ユーザーが選択した色が格納されている戻り値が 0 以外の場合、`colorRes`パラメーター。 使用して、 [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)を標準色 ダイアログ ボックスを切り替える方法、および[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md) ダイアログ ボックス。  
  
##  <a name="setcolor"></a>  CMFCColorMenuButton::SetColor  
 現在のカラー ボタンの色を設定します。  
  
```  
virtual void SetColor(
    COLORREF clr,  
    BOOL bNotify=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `clr`  
 色の RGB 値。  
  
 [入力] `bNotify`  
 `TRUE` 適用する、`clr`パラメーターの色関連メニュー ボタンまたはツール バー ボタンです。 それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 現在のカラー ボタンの色を変更するには、このメソッドを呼び出します。 場合、`bNotify`パラメーターがゼロ以外で指定された色に関連付けられたポップアップ メニューまたはツールバーに対応するボタンの色が変更された、`clr`パラメーター。  
  
##  <a name="setcolorbycmdid"></a>  CMFCColorMenuButton::SetColorByCmdID  
 指定した色のメニュー ボタンの色を設定します。  
  
```  
static void SetColorByCmdID(
    UINT uiCmdID,  
    COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 色のメニュー ボタンのリソース ID です。  
  
 [入力] `color`  
 色の RGB 値。  
  
##  <a name="setcolorname"></a>  CMFCColorMenuButton::SetColorName  
 指定した色の新しい名前を設定します。  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 名前を変更、色の RGB 値。  
  
 [入力] `strName`  
 色の新しい名前。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setcolumnsnumber"></a>  CMFCColorMenuButton::SetColumnsNumber  
 色の選択コントロールに表示する列の数を設定 ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)オブジェクト)。  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nColumns`  
 表示する列の数。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)

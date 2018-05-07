---
title: CMFCColorButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cea6fc2a543a528a0838479b2c47bea99f21cf96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton クラス
`CMFCColorButton`と[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)カラー ピッカー コントロールを実装するクラスが一緒に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|新しい `CMFCColorButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|有効にし、通常の色のボタンの上に配置する「自動」ボタンを無効にします。 (標準のシステムの自動ボタンのラベルは**自動**)。|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|有効にし、標準のカラー ボタンの下にある、"other"ボタンを無効にします。 ("のその他"ボタンのラベルは、標準的なシステム**他の色**)。|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|現在の自動の色を取得します。|  
|[CMFCColorButton::GetColor](#getcolor)|ボタンの色を取得します。|  
|[CMFCColorButton::SetColor](#setcolor)|ボタンの色を設定します。|  
|[CMFCColorButton::SetColorName](#setcolorname)|色の名前を設定します。|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|カラー ピッカー ダイアログ ボックスの列の数を設定します。|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|カラー ピッカー ダイアログ ボックスに表示されるドキュメントに固有の色の一覧を指定します。|  
|[CMFCColorButton::SetPalette](#setpalette)|標準の表示の色のパレットを指定します。|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|そのテキストおよびイメージのサイズによっては、ボタン コントロールのサイズを変更します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Windows XP の視覚スタイルで現在のカラー ボタンを表示するかどうかを示します。|  
|[CMFCColorButton::OnDraw](#ondraw)|ボタンのイメージを表示するためにフレームワークによって呼び出されます。|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|ボタンの境界線を表示するためにフレームワークによって呼び出されます。|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|ボタンにフォーカスがあるときに、フォーカスされた四角形を表示するためにフレームワークによって呼び出されます。|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|カラー ピッカー ダイアログ ボックスが表示されると、フレームワークによって呼び出されます。|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|初期化、`m_pPalette`を指定されたパレットまたは既定のシステム パレット データ メンバーを保護します。|  
|[CMFCColorButton::UpdateColor](#updatecolor)|カラー ピッカー ダイアログ ボックスのパレットから色を選択すると、フレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`m_bAltColorDlg`|ブール値。 場合`TRUE`、フレームワークによって表示、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)色 ダイアログ ボックスの場合、*他の*ボタンがクリックされた場合、または`FALSE`システムの色 ダイアログ ボックス。 既定値は `TRUE` です。 詳細については、次を参照してください。 [CMFCColorButton::EnableOtherButton](#enableotherbutton)です。|  
|`m_bAutoSetFocus`|ブール値。 場合`TRUE`、フレームワークでは、メニューが表示されている場合、または、[色] メニューにフォーカスを設定`FALSE`フォーカスは変わりません。 既定値は `TRUE` です。|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|色のボタンのカスタマイズ モードが有効になっているかどうかを示します。|  
|`m_Color`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在選択されている色が含まれています。|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在選択されている既定の色が含まれています。|  
|`m_Colors`|A [CArray](../../mfc/reference/carray-class.md)の[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在使用可能な色が含まれます。|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md)の[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在のドキュメントの色が含まれています。|  
|`m_nColumns`|整数。 色の選択メニュー内の色のグリッドに表示する列の数が含まれています。|  
|`m_pPalette`|ポインター、 [CPalette](../../mfc/reference/cpalette-class.md)です。 現在の色の選択メニューで使用できる色が含まれます。|  
|`m_pPopup`|ポインター、 [CMFCColorPopupMenu クラス](../../mfc/reference/cmfccolorpopupmenu-class.md)オブジェクト。 色のボタンをクリックしたときに表示される色の選択メニュー。|  
|`m_strAutoColorText`|文字列。 色の選択メニューで「自動」のボタンのラベル。|  
|`m_strDocColorsText`|文字列。 ドキュメントの色を表示する色の選択メニューのボタンのラベル。|  
|`m_strOtherText`|文字列。 色の選択メニューに「その他」ボタンのラベル。|  
  
## <a name="remarks"></a>コメント  
 既定では、`CMFCColorButton`クラスは、カラー ピッカー ダイアログ ボックスを開くプッシュ ボタンとして動作します。 カラー ピッカー ダイアログ ボックスには、小さなカラー ボタンとカスタム カラー ピッカーを表示する、"other"ボタンの配列が含まれています。 ("のその他"ボタンのラベルは、標準的なシステム**他の色**)。ユーザーが新しい色を選択したときに、`CMFCColorButton`オブジェクトが、変更を反映し、選択した色が表示されます。  
  
 色のボタン コントロールを作成する、コード内で直接、またはを使用して、 **ClassWizard**ツールとダイアログ ボックス テンプレート。 色のボタン コントロールを直接作成する場合は、追加、`CMFCColorButton`変数をアプリケーション、およびコンス トラクターを呼び出しますと`Create`のメソッド、`CMFCColorButton`オブジェクト。 使用する場合、 **ClassWizard**、追加、`CButton`ため、アプリケーション変数から変数の型を変更および`CButton`に`CMFCColorButton`です。  
  
 カラー ピッカー ダイアログ ボックス ( [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)) によって表示される、 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)メソッドは、フレームワークと、`OnLButtonDown`イベント ハンドラー。 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)のカスタム色の選択をサポートするメソッドをオーバーライドすることができます。  
  
 `CMFCColorButton`オブジェクトに通知が送信することによって、色が変更されていること、親、`WM_COMMAND | BN_CLICKED`通知します。 親を使用して、 [CMFCColorButton::GetColor](#getcolor)を現在の色を取得する方法です。  
  
## <a name="example"></a>例  
 次の例でのさまざまなメソッドを使用してカラー ボタンを構成する方法、`CMFCColorButton`クラスです。 メソッドは、色のボタンと、列の数の色を設定し、自動ボタンと他のボタンを有効にします。 この例の一部である、[ステータス バーのデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>  CMFCColorButton::CMFCColorButton  
 新しい `CMFCColorButton` オブジェクトを構築します。  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorButton::EnableAutomaticButton  
 有効にするまたは、カラー ピッカー コントロールの「自動」ボタンを無効にし、自動 (既定値) の色を設定します。  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 自動ボタンのテキストを指定します。  
  
 [入力] `colorAutomatic`  
 自動ボタンの既定の色を指定する RGB 値。  
  
 [入力] `bEnable`  
 自動ボタンが有効または無効になっているかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enableotherbutton"></a>  CMFCColorButton::EnableOtherButton  
 有効にするにまたは通常の色のボタンの下に表示される"other"ボタンを無効にします。  
  
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
 指定するかどうか、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックスまたはシステムの色 ダイアログ ボックスには、ユーザーがボタンをクリックしたときに開かれます。  
  
 [入力] `bEnable`  
 「その他」ボタンが有効になっているか、無効にするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 色のダイアログ ボックスを表示する"other"ボタンをクリックします。 場合、 *bAltColorDlg*パラメーターは`TRUE`、 [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)が表示されます。 それ以外の場合、システムの色 ダイアログ ボックスが表示されます。  
  
##  <a name="getautomaticcolor"></a>  CMFCColorButton::GetAutomaticColor  
 自動 (既定値) の現在の色を取得します。  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の自動の色を表す RGB 値。  
  
### <a name="remarks"></a>コメント  
 によって現在の自動の色を設定、 [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)メソッドです。  
  
##  <a name="getcolor"></a>  CMFCColorButton::GetColor  
 現在選択されている色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdrawxptheme"></a>  CMFCColorButton::IsDrawXPTheme  
 Windows XP の視覚スタイルで現在のカラー ボタンを表示するかどうかを示します。  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` visual スタイルがサポートされていて、現在のカラー ボタンが Windows XP の視覚スタイルで表示されます。それ以外の場合、`FALSE`です。  
  
##  <a name="m_benabledincustomizemode"></a>  CMFCColorButton::m_bEnabledInCustomizeMode  
 色のボタンをカスタマイズ モードに設定します。  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>コメント  
 カラー ボタンのカスタマイズ ダイアログ ボックスのページを追加 (またはカスタマイズ中に別の色の選択をユーザーに許可する) 必要がある場合は、設定して、ボタンを有効に、`m_bEnabledInCustomizeMode`メンバー`TRUE`です。 既定では、このメンバーに設定`FALSE`です。  
  
##  <a name="ondraw"></a>  CMFCColorButton::OnDraw  
 ボタンの画像を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンの画像を表示するために使用されるデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 ボタンに外接する四角形。  
  
 [入力] `uiState`  
 ボタンの表示状態を指定します。  
  
### <a name="remarks"></a>コメント  
 表示処理をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="ondrawborder"></a>  CMFCColorButton::OnDrawBorder  
 ボタンの境界線を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 境界線の描画に使用するデバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 指定されているデバイス コンテキスト内の四角形、`pDC`で描画されるボタンの境界を定義するパラメーターです。  
  
 [入力] `uiState`  
 ボタンの表示状態を指定します。  
  
### <a name="remarks"></a>コメント  
 色のボタンの境界線の外観をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="ondrawfocusrect"></a>  CMFCColorButton::OnDrawFocusRect  
 ボタンにフォーカスがあるときに、フォーカスされた四角形を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 フォーカス四角形を描画するために使用するデバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 指定されたデバイス コンテキスト内の四角形、`pDC`ボタンの境界を定義するパラメーターです。  
  
### <a name="remarks"></a>コメント  
 フォーカス四角形の外観をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="onshowcolorpopup"></a>  CMFCColorButton::OnShowColorPopup  
 ポップアップ カラー バーが表示される前に呼び出されます。  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="rebuildpalette"></a>  CMFCColorButton::RebuildPalette  
 初期化、`m_pPalette`を指定されたパレットまたは既定のシステム パレット データ メンバーを保護します。  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pPal`|論理パレットへのポインターまたは`NULL`です。 場合`NULL`既定のシステム パレットを使用します。|  
  
##  <a name="setcolor"></a>  CMFCColorButton::SetColor  
 ボタンの色を指定します。  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 RGB 値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setcolorname"></a>  CMFCColorButton::SetColorName  
 色の名前を指定します。  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 色の RGB 値。  
  
 [入力] `strName`  
 色の名前。  
  
### <a name="remarks"></a>コメント  
 色の名前の一覧は、アプリケーションごとに共通です。 そのため、このメソッドは移動にパラメーターを[CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname)です。  
  
##  <a name="setcolumnsnumber"></a>  CMFCColorButton::SetColumnsNumber  
 ユーザーの色の選択プロセスで、ユーザーに表示される色の一覧に表示される列の数を定義します。  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nColumns`  
 列の数を指定します。  
  
### <a name="remarks"></a>コメント  
 ユーザーは、定義済みの色の一覧が表示されるポップアップ カラー バーの色を選択できます。 このメソッドを使用すると、テーブルの列の数を定義します。  
  
##  <a name="setdocumentcolors"></a>  CMFCColorButton::SetDocumentColors  
 一連の色とセットの名前を指定します。 使用して、色のセットが表示される、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクト。  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ドキュメントの色のセットを表示するラベルを指定します。  
  
 [入力] `lstColors`  
 RGB 値の一覧への参照。  
  
### <a name="remarks"></a>コメント  
 A`CMFCColorButton`ために転送する RGB 値の一覧を保持するオブジェクト、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクト。 ラベルがで指定された特別なセクションにこれらの色を示す、カラー バーが表示される場合、`lpszLabel`パラメーター。  
  
##  <a name="setpalette"></a>  CMFCColorButton::SetPalette  
 ポップアップ カラー バーに表示する標準の色を指定します。  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pPalette`  
 カラー パレットへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sizetocontent"></a>  CMFCColorButton::SizeToContent  
 ボタン コントロールに合わせてそのテキストおよびイメージのサイズを変更します。  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCalcOnly`  
 ゼロ以外の場合は、ボタン コントロールの新しいサイズが計算されますが、実際のサイズは変更されません。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`新しいボタン コントロールのサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="updatecolor"></a>  CMFCColorButton::UpdateColor  
 ユーザーは、ユーザーは、色のボタンをクリックしたときに表示されるカラー バーから色を選択すると、フレームワークによって呼び出されます。  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 ユーザーが選択した色。  
  
### <a name="remarks"></a>コメント  
 `UpdateColor`関数は、現在選択されているボタンの色を変更し、送信することによって、親に通知を`WM_COMMAND`、メッセージ、`BN_CLICKED`標準通知します。 使用して、 [CMFCColorButton::GetColor](#getcolor)メソッドを選択した色を取得します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette クラス](../../mfc/reference/cpalette-class.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)   
 [CList クラス](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)

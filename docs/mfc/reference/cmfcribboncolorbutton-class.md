---
title: CMFCRibbonColorButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bc3b4be5b7b5a6168287135511f3f401203a7e2
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037916"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton クラス
`CMFCRibbonColorButton` クラスは、リボン バーに追加できるカラー ボタンを実装します。 リボンのカラー ボタンは、1 つまたは複数のカラー パレットを含むドロップダウン メニューを表示します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|色のグループを通常の色領域に追加します。|  
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|**[自動]** ボタンを有効にするかどうかを指定します。|  
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|**[その他]** ボタンを有効にします。|  
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||  
|[CMFCRibbonColorButton::GetColor](#getcolor)|現在選ばれている色を返します。|  
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|カラー バーに表示される色要素のサイズを返します。|  
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||  
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|ポップアップ カラー パレットで現在選ばれている要素の色を返します。|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|通常の色領域からすべての色グループを削除します。|  
|[CMFCRibbonColorButton::SetColor](#setcolor)|通常の色領域から色を選びます。|  
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|カラー バーに表示されるすべての色要素のサイズを設定します。|  
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||  
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||  
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|ドキュメントの色領域に表示する RGB 値の一覧を指定します。|  
|[CMFCRibbonColorButton::SetPalette](#setpalette)||  
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||  
  
## <a name="remarks"></a>Remarks  
 ユーザーがリボンのカラー ボタンを押すと、カラー バーが表示されます。 既定では、このカラー バーには通常の色領域と呼ばれる色選択パレットが含まれます。 必要に応じて、カラー バーには **[自動]** ボタン (これを使用するとユーザーは既定の色を選択できます)、および **[その他]** ボタン (追加の色を含むポップアップ カラー パレットが表示されます) を表示できます。  
  
## <a name="example"></a>例  
 `CMFCRibbonColorButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、 `CMFCRibbonColorButton` オブジェクトの構築、大きいイメージの設定、 **[自動]** ボタンの有効化、 **[その他]** ボタンの有効化、列数の設定、カラー バーに表示されるすべての色要素のサイズの設定、通常の色領域への色グループの追加、ドキュメントの色領域に表示する RGB 値の一覧の指定方法を示します。 このコード スニペットは、「 [クライアント サンプルの描画](../../visual-cpp-samples.md)」の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxribboncolorbutton.h  
  
##  <a name="addcolorsgroup"></a>  CMFCRibbonColorButton::AddColorsGroup  
 色のグループを通常の色領域に追加します。  
  
```  
void AddColorsGroup(
    LPCTSTR lpszName,  
    const CList<COLORREF,COLORREF>& lstColors,  
    BOOL bContiguousColumns=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszName*  
 グループの名前。  
  
 [in]*lstColors*  
 色の一覧。  
  
 [in]*bContiguousColumns*  
 グループ内の色のアイテムの表示方法を制御します。 場合`TRUE`色のアイテムが上下の間隔に描画します。 場合`FALSE`色のアイテムが上下の間隔で描画されます。  
  
### <a name="remarks"></a>Remarks  
 この色のポップアップを作成する関数を使用では、いくつかの色のグループを表示します。 グループ内の色の表示方法を制御できます。  
  
##  <a name="cmfcribboncolorbutton"></a>  CMFCRibbonColorButton::CMFCRibbonColorButton  
 `CMFCRibbonColorButton` オブジェクトを構築します。  
  
```  
CMFCRibbonColorButton();

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    COLORREF color = RGB(0, 0, 0));

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    BOOL bSimpleButtonLook,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    COLORREF color = RGB(0, 0, 0));
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nID*  
 ユーザーがボタンをクリックしたときに実行するコマンドのコマンド ID を指定します。  
  
 [in]*lpszText*  
 ボタンに表示するテキストを指定します。  
  
 [in]*nSmallImageIndex*  
 ボタンに表示する小さな画像の 0 から始まるインデックス。  
  
 [in]*色*  
 (既定は黒) のボタンの色。  
  
 [in]*bSimpleButtonLook*  
 場合`TRUE`、単純な四角形として、ボタンを描画します。  
  
 [in]*nLargeImageIndex*  
 ボタンに表示する大きいイメージの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="enableautomaticbutton"></a>  CMFCRibbonColorButton::EnableAutomaticButton  
 **[自動]** ボタンを有効にするかどうかを指定します。  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE,  
    LPCTSTR lpszToolTip=NULL,  
    BOOL bOnTop=TRUE,  
    BOOL bDrawBorder=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszLabel*  
 ラベル、**自動**ボタンをクリックします。  
  
 [in]*colorAutomatic*  
 指定する RGB 値、**自動**ボタンの既定の色。  
  
 [in]*bEnable*  
 `TRUE` 場合、**自動**ボタンが有効にします。`FALSE`無効になっている場合。  
  
 [in]*lpszToolTip*  
 ツール ヒント、**自動**ボタンをクリックします。  
  
 [in]*bOnTop*  
 指定するかどうか、**自動**ボタンが上部のカラー パレットの前にします。  
  
 [in]*bDrawBorder*  
 `TRUE` 場合は、アプリケーションは、リボンのカラー ボタンをカラー バーの境界線を描画します。 カラー バーには、現在選択されている色が表示されます。 `FALSE` アプリケーションが枠線を描画していない場合  
  
##  <a name="enableotherbutton"></a>  CMFCRibbonColorButton::EnableOtherButton  
 **[その他]** ボタンを有効にします。  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    LPCTSTR lpszToolTip=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszLabel*  
 ボタンのラベル。  
  
 *lpszToolTip*  
 ツールヒントのテキスト、**他**ボタンをクリックします。  
  
### <a name="remarks"></a>Remarks  
 **他**ボタンは、色のグループの下に表示されるボタン。 ユーザーがクリックしたとき、**他の**ボタン、カラー ダイアログが表示されます。  
  
##  <a name="getautomaticcolor"></a>  CMFCRibbonColorButton::GetAutomaticColor  
 現在の自動ボタンの色を取得します。  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の自動ボタンの色を表す RGB カラー値。  
  
### <a name="remarks"></a>Remarks  
 自動ボタンの色が設定されて、`colorAutomatic`に渡されたパラメーター、`CMFCRibbonColorButton::EnableAutomaticButton`メソッドです。  
  
##  <a name="getcolor"></a>  CMFCRibbonColorButton::GetColor  
 現在選ばれている色を返します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンをクリックして選択した色。  
  
##  <a name="getcolorboxsize"></a>  CMFCRibbonColorButton::GetColorBoxSize  
 カラー バーに表示される色要素のサイズを返します。  
  
```  
CSize GetColorBoxSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドロップダウンのカラー パレットのカラー ボタンのサイズ。  
  
##  <a name="getcolumns"></a>  CMFCRibbonColorButton::GetColumns  
 リボンのカラー ボタン ギャラリー表示の行の項目の数を取得します。  
  
```  
int GetColumns() const;  
```  
  
### <a name="return-value"></a>戻り値  
 各行のアイコンの数を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gethighlightedcolor"></a>  CMFCRibbonColorButton::GetHighlightedColor  
 ポップアップ カラー パレットで現在選択されている要素の色を返します。  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ カラー パレットで現在選択されている要素の色。  
  
##  <a name="removeallcolorgroups"></a>  CMFCRibbonColorButton::RemoveAllColorGroups  
 通常の色領域からすべての色グループを削除します。  
  
```  
void RemoveAllColorGroups();
```  
  
##  <a name="setcolor"></a>  CMFCRibbonColorButton::SetColor  
 通常の色領域から色を選びます。  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*色*  
 設定する色。  
  
##  <a name="setcolorboxsize"></a>  CMFCRibbonColorButton::SetColorBoxSize  
 カラー バーに表示されるすべての色要素のサイズを設定します。  
  
```  
void SetColorBoxSize(CSize sizeBox);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*sizeBox*  
 カラー パレットのカラー ボタンの新しいサイズ。  
  
##  <a name="setcolorname"></a>  CMFCRibbonColorButton::SetColorName  
 指定した色の新しい名前を設定します。  
  
```  
static void __stdcall SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*色*  
 色の RGB 値。  
  
 [in]*strName*  
 指定した色の新しい名前。  
  
### <a name="remarks"></a>Remarks  
 呼び出すので`CMFCColorBar::SetColorName`、このメソッドは、すべてのページで指定された色の名前を変更`CMFCColorBar`アプリケーション内のオブジェクト。  
  
##  <a name="setcolumns"></a>  CMFCRibbonColorButton::SetColumns  
 ユーザーの色の選択プロセスで、ユーザーに表示される色の一覧に表示される列の数を設定します。  
  
```  
void SetColumns(int nColumns);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nColumns*  
 行ごとに表示するカラー アイコンの数。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setdocumentcolors"></a>  CMFCRibbonColorButton::SetDocumentColors  
 ドキュメントの色領域に表示する RGB 値の一覧を指定します。  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszLabel*  
 ドキュメントの色で表示されるテキストです。  
  
 [in]*lstColors*  
 RGB 値の一覧への参照。  
  
##  <a name="setpalette"></a>  CMFCRibbonColorButton::SetPalette  
 色のボタンを表示するカラー テーブルに表示する標準の色を指定します。  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pPalette*  
 カラー パレットへのポインター。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="updatecolor"></a>  CMFCRibbonColorButton::UpdateColor  
 ユーザーが、ユーザーが色のボタンをクリックしたときに表示されている色テーブルから色を選択すると、フレームワークによって呼び出されます。  
  
```  
void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*色*  
 ユーザーが選択した色。  
  
### <a name="remarks"></a>Remarks  
 `CMFCRibbonColorButton::UpdateColor`メソッドは、現在選択されているボタンの色を変更し、BN_CLICKED の標準的な通知と WM_COMMAND メッセージを送信することによって、親に通知します。 使用して、 [CMFCRibbonColorButton::GetColor](#getcolor)メソッドを選択した色を取得します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)

---
title: CMFCColorDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b2b3c2ff247014a692a78084f42c208b4497023
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040234"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog クラス
`CMFCColorDialog`クラスは、色の選択 ダイアログ ボックスを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|`CMFCColorDialog` オブジェクトを構築します。|  
|`CMFCColorDialog::~CMFCColorDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|現在選択されている色を返します。|  
|[CMFCColorDialog::GetPalette](#getpalette)|色のパレットを返します。|  
|`CMFCColorDialog::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数。 構文や詳細については、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)です。 (`CDialogEx::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|システム パレットからパレットを取得します。|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|現在の選択した色を設定します。|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|指定された RGB 値に最も近い色を設定します。|  
|[CMFCColorDialog::SetPageOne](#setpageone)|最初のプロパティ ページの RGB 値を選択します。|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|2 番目のプロパティ ページの RGB 値を選択します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE` 色の選択 ダイアログ ボックスで、独自の色パレットを使用する場合または`FALSE` ダイアログ ボックスがで指定されているパレットを使用するかどうか、`CMFCColorDialog`コンス トラクターです。|  
|`m_bPickerMode`|`TRUE` ユーザーが選択 ダイアログ ボックスから色を選択するときにそれ以外の場合、`FALSE`です。|  
|`m_btnColorSelect`|色のボタンをユーザーが選択されています。|  
|`m_CurrentColor`|現在選択されている色です。|  
|`m_hcurPicker`|色の選択に使用されるカーソルです。|  
|`m_NewColor`|見込み客に対して選択した色、永続的に選択または元の色に元に戻すことができます。|  
|`m_pColourSheetOne`|色の選択のプロパティ シートの最初のプロパティ ページへのポインター。|  
|`m_pColourSheetTwo`|色の選択のプロパティ シートの 2 番目のプロパティ ページへのポインター。|  
|`m_pPalette`|現在の論理パレット。|  
|`m_pPropSheet`|色の選択 ダイアログ ボックスのプロパティ シートへのポインター。|  
|`m_wndColors`|カラー ピッカー コントロール オブジェクトです。|  
|`m_wndStaticPlaceHolder`|カラー ピッカーのプロパティ シートのプレース ホルダーである静的なコントロールします。|  
  
## <a name="remarks"></a>Remarks  
 色の選択 ダイアログ ボックスは、2 つのページで、プロパティ シートとして表示されます。 最初のページで、システム パレットから標準色を選択します。2 番目のページでは、カスタムの色を選択します。  
  
 構築することができます、`CMFCColorDialog`スタック上のオブジェクトを呼び出す`DoModal`、最初の色をパラメーターとして渡す、`CMFCColorDialog`コンス トラクター。 色の選択 ダイアログ ボックスは、いくつか作成[CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)各色パレットを処理するオブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>例  
 次の例では、多様なメソッドを使用して、色のダイアログを構成する方法、`CMFCColorDialog`クラスです。 例では、現在と、ダイアログ ボックスの新しい色を設定する方法と、色のダイアログ ボックスの 2 つのプロパティ ページで選択した色の赤、緑、および青の要素を設定する方法を示します。 この例の一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>  CMFCColorDialog::CMFCColorDialog  
 `CMFCColorDialog` オブジェクトを構築します。  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*clrInit*  
 既定の色の選択 値が指定されていない場合は、既定では RGB(0,0,0) (黒です)。  
  
 [in]*dwFlags*  
 (予約されています。)  
  
 [in]*pParentWnd*  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
 [in]*hPal*  
 カラー パレットへのハンドル。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcolor"></a>  CMFCColorDialog::GetColor  
 色のダイアログで、ユーザーが選択した色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)色のダイアログ ボックスで選択した色の RGB 情報を含む値です。  
  
### <a name="remarks"></a>Remarks  
 呼び出した後に、この関数を呼び出して、`DoModal`メソッドです。  
  
##  <a name="getpalette"></a>  CMFCColorDialog::GetPalette  
 現在の色のダイアログ ボックスで使用可能なカラー パレットを取得します。  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPalette`で指定されているオブジェクト、`CMFCColorDialog`コンス トラクターです。  
  
### <a name="remarks"></a>Remarks  
 カラー パレットは、ユーザーが選択できる色を指定します。  
  
##  <a name="rebuildpalette"></a>  CMFCColorDialog::RebuildPalette  
 システム パレットからパレットを取得します。  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>  CMFCColorDialog::SetCurrentColor  
 ダイアログ ボックスの現在の色を設定します。  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rgb*  
 色の RGB 値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setnewcolor"></a>  CMFCColorDialog::SetNewColor  
 最も類似したは、現在のパレットで色を現在の色を設定します。  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rgb*  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) RGB 色を指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setpageone"></a>  CMFCColorDialog::SetPageOne  
 色 ダイアログ ボックスの最初のプロパティ ページで選択した色の赤、緑、および青の要素を明示的に指定します。  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*R*  
 RGB 値の赤の要素を指定します。  
  
 [in]*G*  
 RGB 値の緑の成分を指定します。  
  
 [in]*B*  
 RGB 値の青の成分を指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setpagetwo"></a>  CMFCColorDialog::SetPageTwo  
 色のダイアログの 2 番目のプロパティ ページで選択した色の赤、緑、および青の要素を明示的に指定します。  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*R*  
 RGB 値の赤の要素を指定します  
  
 [in]*G*  
 RGB 値の緑の成分を指定します  
  
 [in]*B*  
 RGB 値の青の成分を指定します  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)

---
title: CMFCColorDialog クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 987e4f1e5e89c3c56b58adaad76cfd23d5e26c52
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367715"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog クラス

クラス`CMFCColorDialog`は色選択ダイアログ ボックスを表します。

## <a name="syntax"></a>構文

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::CMFC カラー ダイアログ](#cmfccolordialog)|`CMFCColorDialog` オブジェクトを構築します。|
|`CMFCColorDialog::~CMFCColorDialog`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::取得カラー](#getcolor)|現在選択されている色を返します。|
|[ダイアログ::パレットを取得します。](#getpalette)|カラーパレットを返します。|
|`CMFCColorDialog::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 構文と詳細については[、「CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)」を参照してください。 ( `CDialogEx::PreTranslateMessage`をオーバーライドします)。|
|[ダイアログ::リビルドパレット](#rebuildpalette)|システム パレットからパレットを派生させます。|
|[ダイアログボックス::現在の色を設定します。](#setcurrentcolor)|現在選択されている色を設定します。|
|[ダイアログボックス::新しい色を設定します。](#setnewcolor)|指定した RGB 値に最も等しい色を設定します。|
|[ダイアログボックス::セットページワン](#setpageone)|最初のプロパティ ページの RGB 値を選択します。|
|[ダイアログボックス::ページ2](#setpagetwo)|2 番目のプロパティ ページの RGB 値を選択します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|`m_bIsMyPalette`|色選択ダイアログ ボックスが独自のカラー パレットを使用する場合は TRUE、`CMFCColorDialog`コンストラクターで指定されたパレットをダイアログ ボックスが使用する場合は FALSE。|
|`m_bPickerMode`|ユーザーが選択ダイアログ ボックスから色を選択している間は TRUE。それ以外の場合は FALSE。|
|`m_btnColorSelect`|ユーザーが選択したカラー ボタン。|
|`m_CurrentColor`|現在選択されている色。|
|`m_hcurPicker`|色を選択するために使用されるカーソル。|
|`m_NewColor`|選択した将来の色で、元の色に完全に選択または元の色に戻すことができます。|
|`m_pColourSheetOne`|色選択プロパティ シートの最初のプロパティ ページへのポインター。|
|`m_pColourSheetTwo`|色選択プロパティ シートの 2 番目のプロパティ ページへのポインター。|
|`m_pPalette`|現在の論理パレット。|
|`m_pPropSheet`|色選択ダイアログ ボックスのプロパティ シートへのポインター。|
|`m_wndColors`|カラー ピッカー コントロール オブジェクト。|
|`m_wndStaticPlaceHolder`|カラー ピッカーのプロパティ シートのプレースホルダーである静的コントロール。|

## <a name="remarks"></a>解説

色選択ダイアログ ボックスは、2 つのページを持つプロパティ シートとして表示されます。 最初のページでは、システム パレットから標準色を選択します。2 番目のページでは、カスタムカラーを選択します。

スタック上にオブジェクト`CMFCColorDialog`を構築し、最初の色`DoModal`を`CMFCColorDialog`コンストラクタにパラメータとして渡して呼び出すことができます。 色選択ダイアログ ボックスでは、各カラー パレットを処理する[CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)のオブジェクトを作成します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>例

クラスのさまざまなメソッドを使用して色のダイアログ を構成する方法を次の`CMFCColorDialog`例に示します。 この例では、ダイアログの現在の色と新しい色を設定する方法、および選択した色の赤、緑、青の各コンポーネントを、色ダイアログの 2 つのプロパティ ページに設定する方法を示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcolordialog.h

## <a name="cmfccolordialogcmfccolordialog"></a><a name="cmfccolordialog"></a>ダイアログ ボックス::CMFC カラー ダイアログ

`CMFCColorDialog` オブジェクトを構築します。

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>パラメーター

*clrInit*<br/>
[in]既定の色の選択。 値を指定しない場合、デフォルトは RGB(0,0,0) (黒) になります。

*dwFlags*<br/>
[in] 予約されています。

*pParentWnd*<br/>
[in]ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。

*hパル*<br/>
[in]カラー パレットへのハンドル。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfccolordialoggetcolor"></a><a name="getcolor"></a>ダイアログボックス::取得カラー

ユーザーが色ダイアログから選択した色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

カラー ダイアログ ボックスで選択した色の RGB 情報を含む[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

メソッドを呼び出した後`DoModal`、この関数を呼び出します。

## <a name="cmfccolordialoggetpalette"></a><a name="getpalette"></a>ダイアログ::パレットを取得します。

現在の色ダイアログで使用できるカラー パレットを取得します。

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>戻り値

コンストラクターで指定された`CPalette`オブジェクトへのポインター。 `CMFCColorDialog`

### <a name="remarks"></a>解説

カラー パレットは、ユーザーが選択できる色を指定します。

## <a name="cmfccolordialogrebuildpalette"></a><a name="rebuildpalette"></a>ダイアログ::リビルドパレット

システム パレットからパレットを派生させます。

```
void RebuildPalette();
```

## <a name="cmfccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>ダイアログボックス::現在の色を設定します。

ダイアログ ボックスの現在の色を設定します。

```
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>パラメーター

*Rgb*<br/>
[in]RGB カラー値

### <a name="remarks"></a>解説

## <a name="cmfccolordialogsetnewcolor"></a><a name="setnewcolor"></a>ダイアログボックス::新しい色を設定します。

現在のカラーを、最も類似したパレットの色に設定します。

```
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>パラメーター

*Rgb*<br/>
[in]RGB カラーを指定する[COLORREF](/windows/win32/gdi/colorref)です。

### <a name="remarks"></a>解説

## <a name="cmfccolordialogsetpageone"></a><a name="setpageone"></a>ダイアログボックス::セットページワン

色ダイアログの最初のプロパティ ページで、選択した色の赤、緑、青の各コンポーネントを明示的に指定します。

```
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>パラメーター

*R*<br/>
[in]RGB 値の赤のコンポーネントを指定します。

*G*<br/>
[in]RGB 値の緑色のコンポーネントを指定します。

*B*<br/>
[in]RGB 値の青いコンポーネントを指定します。

### <a name="remarks"></a>解説

## <a name="cmfccolordialogsetpagetwo"></a><a name="setpagetwo"></a>ダイアログボックス::ページ2

色ダイアログの 2 番目のプロパティ ページで選択した色の赤、緑、青のコンポーネントを明示的に指定します。

```
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>パラメーター

*R*<br/>
[in]RGB 値の赤のコンポーネントを指定します。

*G*<br/>
[in]RGB 値の緑色のコンポーネントを指定します。

*B*<br/>
[in]RGB 値の青いコンポーネントを指定します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)

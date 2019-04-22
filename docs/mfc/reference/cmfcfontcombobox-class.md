---
title: CMFCFontComboBox クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
ms.openlocfilehash: ccc4e545b2274d6dbb9989cfb9c047de819b8d32
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781303"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox クラス

`CMFCFontComboBox`クラスは、フォントの一覧を含むコンボ ボックス コントロールを作成します。

## <a name="syntax"></a>構文

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|`CMFCFontComboBox` オブジェクトを構築します。|
|`CMFCFontComboBox::~CMFCFontComboBox`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|現在のフォント コンボ ボックス コントロールの並べ替えられたリスト ボックスに新しい項目の相対位置を決定するためにフレームワークによって呼び出されます。 (上書き[CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem))。|
|`CMFCFontComboBox::DrawItem`|現在のフォント コンボ ボックス コントロールで、指定した項目を描画するためにフレームワークによって呼び出されます。 (上書き[CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem))。|
|[CMFCFontComboBox::GetSelFont](#getselfont)|現在選択されているフォントについての情報を取得します。|
|`CMFCFontComboBox::MeasureItem`|現在のフォント コンボ ボックス コントロールでリスト ボックスのサイズの Windows に通知するためにフレームワークによって呼び出されます。 (上書き[CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem))。|
|`CMFCFontComboBox::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[CMFCFontComboBox::SelectFont](#selectfont)|フォント コンボ ボックスから、指定した条件に一致するフォントを選択します。|
|[CMFCFontComboBox::Setup](#setup)|フォント コンボ ボックス内の項目の一覧を初期化します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|現在のフォント コンボ ボックス内の項目のラベルの描画に使用するフォントのフレームワークを示します。|

## <a name="remarks"></a>Remarks

使用する、 `CMFCFontComboBox`  ダイアログ ボックスでオブジェクトを追加、`CMFCFontComboBox`変数 ダイアログ ボックスのクラスにします。 次に、`OnInitDialog`呼び出し、ダイアログ ボックス クラスのメソッド、 [CMFCFontComboBox::Setup](#setup)コンボ ボックス コントロール内の項目の一覧を初期化します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxfontcombobox.h

##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox

`CMFCFontComboBox` オブジェクトを構築します。

```
CMFCFontComboBox();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont

現在選択されているフォントについての情報を取得します。

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>戻り値

ポインター [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)フォントを表すオブジェクト。 NULL は、コンボ ボックスのフォントが選択されていない場合にそのことができます。

### <a name="remarks"></a>Remarks

##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont

現在のフォント コンボ ボックス内の項目のラベルの描画に使用するフォントのフレームワークを示します。

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Remarks

このメンバーは、各項目のラベルを描画するために同じフォントを使用するようフレームワークに指示する場合は TRUE を設定します。 このメンバーをフレームワークの名前は、ラベルと同じフォントを使用して各項目のラベルの描画に指示する場合は FALSE に設定します。 このメンバーの既定値は FALSE です。

##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont

フォント コンボ ボックスから、指定した条件に一致するフォントを選択します。

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>パラメーター

*pDesc*<br/>
[in]フォントの説明オブジェクトを指します。

*lpszName*<br/>
[in]フォント名を指定します。

*nCharSet*<br/>
[in]文字セットを指定します。 既定値は、DEFAULT_CHARSET です。 詳細については、次を参照してください。、`lfCharSet`のメンバー、 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)構造体。

### <a name="return-value"></a>戻り値

フォント コンボ ボックス内の項目は、説明オブジェクトの指定したフォントまたはフォントの名前と charset; と一致する場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドを使用して、選択し、指定したフォントに対応するフォント コンボ ボックス内の項目までスクロールします。

### <a name="example"></a>例

次の例では、使用する方法、`SelectFont`メソッドで、`CMFCFontComboBox`クラス。 この例は、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>  CMFCFontComboBox::Setup

フォント コンボ ボックス内の項目の一覧を初期化します。

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>パラメーター

*nFontType*<br/>
[in]フォントの種類を指定します。 既定値は、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE のビットごとの組み合わせ (OR です)。

*nCharSet*<br/>
[in]フォントの文字セットを指定します。 既定値は、DEFAULT_CHARSET です。

*nPitchAndFamily*<br/>
[in]フォントのピッチとファミリを指定します。 既定値は、DEFAULT_PITCH です。

### <a name="return-value"></a>戻り値

フォント コンボ ボックスが正常に初期化されている場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、指定されたパラメーターと一致する現在インストールされているフォントを列挙して、フォント コンボ ボックスにそのフォント名を挿入する、フォント コンボ ボックスを初期化します。

### <a name="example"></a>例

次の例では、使用する方法、`Setup`メソッドで、`CMFCFontComboBox`クラス。 この例は、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)

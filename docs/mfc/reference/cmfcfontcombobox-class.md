---
title: クラス
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
ms.openlocfilehash: 60b4b7cdfdace2332de35dd93c43eacf592e99e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367501"
---
# <a name="cmfcfontcombobox-class"></a>クラス

この`CMFCFontComboBox`クラスは、フォントのリストを含むコンボ ボックス コントロールを作成します。

## <a name="syntax"></a>構文

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コンボボックス::CMFCフォントコンボボックス](#cmfcfontcombobox)|`CMFCFontComboBox` オブジェクトを構築します。|
|`CMFCFontComboBox::~CMFCFontComboBox`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|現在のフォント コンボ ボックス コントロールの並べ替えられたリスト ボックス内の新しい項目の相対位置を決定するために、フレームワークによって呼び出されます。 (C[コンボボックスをオーバーライドします::アイテムを比較](../../mfc/reference/ccombobox-class.md#compareitem)します。|
|`CMFCFontComboBox::DrawItem`|現在のフォント コンボ ボックス コントロールで指定した項目を描画するために、フレームワークによって呼び出されます。 (C[コンボ ボックス::Dローアイテム](../../mfc/reference/ccombobox-class.md#drawitem)をオーバーライドします。|
|[コンボボックス::ゲットセルフォント](#getselfont)|現在選択されているフォントに関する情報を取得します。|
|`CMFCFontComboBox::MeasureItem`|現在のフォント コンボ ボックス コントロールのリスト ボックスのサイズを Windows に通知するために、フレームワークによって呼び出されます。 (C[コンボボックスをオーバーライドします::メジャーアイテム](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[コンボボックス::フォントを選択します。](#selectfont)|フォントコンボボックスから指定した条件に一致するフォントを選択します。|
|[コンボボックス::セットアップ](#setup)|フォント コンボ ボックス内の項目のリストを初期化します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[コンボボックス:m_bDrawUsingFont](#m_bdrawusingfont)|現在のフォント コンボ ボックスで項目ラベルを描画するために使用するフォントをフレームワークに示します。|

## <a name="remarks"></a>解説

ダイアログ ボックス`CMFCFontComboBox`でオブジェクトを使用するには、ダイアログ`CMFCFontComboBox`ボックスクラスに変数を追加します。 次に`OnInitDialog`、ダイアログ ボックス クラスのメソッドで、コンボ ボックス コントロール内の項目のリストを初期化する[CMFCFontComboBox::Setup](#setup)メソッドを呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx フォントコンボボックス.h

## <a name="cmfcfontcomboboxcmfcfontcombobox"></a><a name="cmfcfontcombobox"></a>コンボボックス::CMFCフォントコンボボックス

`CMFCFontComboBox` オブジェクトを構築します。

```
CMFCFontComboBox();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcfontcomboboxgetselfont"></a><a name="getselfont"></a>コンボボックス::ゲットセルフォント

現在選択されているフォントに関する情報を取得します。

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>戻り値

フォントを記述する[CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)オブジェクトへのポインター。 コンボ ボックスでフォントが選択されていない場合は、NULL を指定できます。

### <a name="remarks"></a>解説

## <a name="cmfcfontcomboboxm_bdrawusingfont"></a><a name="m_bdrawusingfont"></a>コンボボックス:m_bDrawUsingFont

現在のフォント コンボ ボックスで項目ラベルを描画するために使用するフォントをフレームワークに示します。

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>解説

各項目ラベルを描画するために同じフォントを使用するようにフレームワークに指示するには、このメンバーを TRUE に設定します。 このメンバーを FALSE に設定すると、ラベルと同じ名前のフォントで各項目ラベルを描画するようにフレームワークに指示します。 このメンバーのデフォルト値は FALSE です。

## <a name="cmfcfontcomboboxselectfont"></a><a name="selectfont"></a>コンボボックス::フォントを選択します。

フォントコンボボックスから指定した条件に一致するフォントを選択します。

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>パラメーター

*pDesc*<br/>
[in]フォント記述オブジェクトへのポイント。

*名前を指定します。*<br/>
[in]フォント名を指定します。

*nCharセット*<br/>
[in]文字セットを指定します。 既定値は DEFAULT_CHARSET です。 詳しくは[、LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) `lfCharSet`構造体のメンバーを参照してください。

### <a name="return-value"></a>戻り値

フォント コンボ ボックスの項目が、指定したフォント記述オブジェクトまたはフォント名と文字セットと一致する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、指定したフォントに対応するフォント コンボ ボックスの項目を選択してスクロールするために使います。

### <a name="example"></a>例

クラスでメソッドを使用する方法を`SelectFont`次の例に`CMFCFontComboBox`示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

## <a name="cmfcfontcomboboxsetup"></a><a name="setup"></a>コンボボックス::セットアップ

フォント コンボ ボックス内の項目のリストを初期化します。

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>パラメーター

*nフォントタイプ*<br/>
[in]フォントの種類を指定します。 既定値は、DEVICE_FONTTYPE、RASTER_FONTTYPE、およびTRUETYPE_FONTTYPEのビットごとの組み合わせ (OR) です。

*nCharセット*<br/>
[in]フォント文字セットを指定します。 既定値は DEFAULT_CHARSET です。

*アンドファミリー*<br/>
[in]フォントのピッチとファミリを指定します。 既定値はDEFAULT_PITCHです。

### <a name="return-value"></a>戻り値

フォント コンボ ボックスが正常に初期化された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、指定したパラメーターに一致する現在インストールされているフォントを列挙し、フォント コンボ ボックスにそれらのフォント名を挿入することによって、フォント コンボ ボックスを初期化します。

### <a name="example"></a>例

クラスでメソッドを使用する方法を`Setup`次の例に`CMFCFontComboBox`示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[コンボボックス クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)

---
title: CMFCPropertyGridFontProperty クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
ms.openlocfilehash: b348dc2ac68ced89fb0702073f57a114befaf1cb
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769356"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty クラス

`CMFCPropertyGridFileProperty`クラスは、フォントの選択 ダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートしています。

## <a name="syntax"></a>構文

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|`CMFCPropertyGridFontProperty` オブジェクトを構築します。|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|プロパティ値のテキスト表現の書式を設定します  (上書き[cmfcpropertygridproperty::formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty))。|
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|ユーザーが、[フォント] ダイアログ ボックスから選択したフォントの色を取得します。|
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|ユーザーが、[フォント] ダイアログ ボックスから選択したフォントを取得します。|
|`CMFCPropertyGridFontProperty::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|
|`CMFCPropertyGridFontProperty::OnClickButton`|プロパティに含まれているボタンをユーザーがクリックすると、フレームワークによって呼び出されます  (上書き[cmfcpropertygridproperty::onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton))。|

## <a name="remarks"></a>Remarks

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpropertygridctrl.h

##  <a name="cmfcpropertygridfontproperty"></a>  CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty

`CMFCPropertyGridFontProperty` オブジェクトを構築します。

```
CMFCPropertyGridFontProperty(
    const CString& strName,
    LOGFONT& lf,
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0,
    COLORREF color = (COLORREF)-1);
```

### <a name="parameters"></a>パラメーター

*strName*<br/>
[in]プロパティの名前。

*lf*<br/>
[in]フォントの属性を指定するフォントの論理構造体。

*dwFontDialogFlags*<br/>
[in]プロパティ値のドロップダウン ボタンをクリックすると表示される [フォント] ダイアログ ボックスに適用されるスタイル。 既定値は、CF_EFFECTS と CF_SCREENFONTS のビットごとの組み合わせ (OR です)。 詳細については、、*フラグ*のパラメーター、 [CHOOSEFONT 構造](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta)を参照してください。

*lpszDescr*<br/>
[in]フォントのプロパティの説明。 既定値は、NULL です。

*dwData*<br/>
[in]整数プロパティに関連付けられているその他のデータへのポインターなどのアプリケーションに固有のデータ。 既定値は 0 です。

*色*<br/>
[in]フォントの色。 既定値は既定の色です。

### <a name="remarks"></a>Remarks

A`CMFCPropertyGridFontProperty`オブジェクト、プロパティ グリッドのフォント コントロールのフォント プロパティを表します。

### <a name="example"></a>例

次の例のオブジェクトを構築する方法、`CMFCPropertyGridFontProperty`クラス。 この例は、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

##  <a name="getcolor"></a>  CMFCPropertyGridFontProperty::GetColor

ユーザーが、[フォント] ダイアログ ボックスから選択したフォントの色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

選択したフォントの色を表す RGB カラー値。

### <a name="remarks"></a>Remarks

##  <a name="getlogfont"></a>  CMFCPropertyGridFontProperty::GetLogFont

ユーザーが、[フォント] ダイアログ ボックスから選択したフォントを取得します。

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>戻り値

ポインターを[LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)選択したフォントを記述する構造体。

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty クラス](../../mfc/reference/cmfcpropertygridproperty-class.md)

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
ms.openlocfilehash: a1c9905d8d7f32a049496c4e164c9eaac13455d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361836"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty クラス

この`CMFCPropertyGridFileProperty`クラスは、フォント選択ダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートします。

## <a name="syntax"></a>構文

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティプロパティ::プロパティ グリッド フォント プロパティ](#cmfcpropertygridfontproperty)|`CMFCPropertyGridFontProperty` オブジェクトを構築します。|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|プロパティ値のテキスト表現の書式を設定します  (プロパティ[プロパティをオーバーライドします](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)。|
|[プロパティ::取得色](#getcolor)|フォント ダイアログ ボックスからユーザーが選択したフォントの色を取得します。|
|[プロパティ::取得ログフォント](#getlogfont)|フォント ダイアログ ボックスからユーザーが選択したフォントを取得します。|
|`CMFCPropertyGridFontProperty::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|`CMFCPropertyGridFontProperty::OnClickButton`|プロパティに含まれているボタンをユーザーがクリックすると、フレームワークによって呼び出されます  ([プロパティプロパティをオーバーライドします。](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)|

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfontpropertycmfcpropertygridfontproperty"></a><a name="cmfcpropertygridfontproperty"></a>プロパティプロパティ::プロパティ グリッド フォント プロパティ

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

*Lf*<br/>
[in]フォントの属性を指定する論理フォント構造。

*ダイアログ ボックス*<br/>
[in]プロパティ値ドロップダウン ボタンをクリックしたときに表示されるフォント ダイアログ ボックスに適用されるスタイル。 既定値は、CF_EFFECTSとCF_SCREENFONTSのビットごとの組み合わせ (OR) です。 詳細については[、CHOOSEFONT 構造体](/windows/win32/api/commdlg/ns-commdlg-choosefontw)の*フラグ*パラメータを参照してください。

*lpszDescr*<br/>
[in]フォント プロパティの説明です。 既定値は NULL です。

*dw データ*<br/>
[in]整数やプロパティに関連付けられている他のデータへのポインターなど、アプリケーション固有のデータ。 既定値は 0 です。

*色*<br/>
[in]フォントの色。 既定値は既定の色です。

### <a name="remarks"></a>解説

オブジェクト`CMFCPropertyGridFontProperty`は、プロパティ グリッドフォント コントロールのフォント プロパティを表します。

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例`CMFCPropertyGridFontProperty`に示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

## <a name="cmfcpropertygridfontpropertygetcolor"></a><a name="getcolor"></a>プロパティ::取得色

フォント ダイアログ ボックスからユーザーが選択したフォントの色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

選択したフォントの色を表す RGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridfontpropertygetlogfont"></a><a name="getlogfont"></a>プロパティ::取得ログフォント

フォント ダイアログ ボックスからユーザーが選択したフォントを取得します。

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>戻り値

選択したフォントを記述する[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体へのポインター。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[プロパティプロパティ](../../mfc/reference/cmfcpropertygridproperty-class.md)

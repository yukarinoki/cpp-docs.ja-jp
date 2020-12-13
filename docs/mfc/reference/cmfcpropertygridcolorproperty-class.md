---
description: '詳細情報: CMFCPropertyGridColorProperty クラス'
title: CMFCPropertyGridColorProperty クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
ms.openlocfilehash: 7673044a149dc1b5171167ed0854918434651dc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334704"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty クラス

`CMFCPropertyGridColorProperty` クラスは、色の選択用のダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートします。

## <a name="syntax"></a>構文

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|`CMFCPropertyGridColorProperty` オブジェクトを構築します。|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|[色の選択] ダイアログボックスの [ *自動* ] ボタンを有効にします。 (標準の自動ボタンには [ **自動**] というラベルが付いています)。|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|[色の選択] ダイアログボックスの [ *その他* ] ボタンを有効にします。 ([その他] ボタンには、[その他の **色**] というラベルが付いています)。|
|`CMFCPropertyGridColorProperty::FormatProperty`|プロパティ値のテキスト表現の書式を設定します  ( [Cmfcpropertygridproperty:: formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)をオーバーライドします)。|
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|プロパティの現在の色を取得します。|
|`CMFCPropertyGridColorProperty::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|`CMFCPropertyGridColorProperty::OnClickButton`|プロパティに含まれているボタンをユーザーがクリックすると、フレームワークによって呼び出されます  ( [Cmfcpropertygridproperty:: OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)をオーバーライドします)。|
|`CMFCPropertyGridColorProperty::OnDrawValue`|プロパティ値を表示するためにフレームワークによって呼び出されます  ( [Cmfcpropertygridproperty:: OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue)をオーバーライドします)。|
|`CMFCPropertyGridColorProperty::OnEdit`|ユーザーがプロパティ値を変更しようとすると、フレームワークによって呼び出されます  ( [Cmfcpropertygridproperty:: OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit)をオーバーライドします)。|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|編集可能なプロパティの値が変更されると、フレームワークによって呼び出されます  ( [Cmfcpropertygridproperty:: OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue)をオーバーライドします)。|
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|プロパティの新しい色を設定します。|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|現在のカラー プロパティ グリッド内の列の数を指定します。|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|編集可能なプロパティの元の値を設定します。|

## <a name="remarks"></a>解説

`CMFCPropertyGridColorProperty` クラスは、プロパティ リスト コントロールに追加できるカラー プロパティをサポートします。 詳細については、「 [Cmfcpropertygridctrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)」を参照してください。

## <a name="example"></a>例

`CMFCPropertyGridColorProperty` クラスのオブジェクトを構築する方法、および `CMFCPropertyGridColorProperty` クラスの各種メソッドを使用してこのオブジェクトを構成する方法を次の例に示します。 このコードでは、自動ボタンとその他ボタンを有効にする方法、および色と列番号を設定する方法を示しています。 この例は、「 [新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxpropertygridctrl

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a> CMFCPropertyGridColorProperty:: CMFCPropertyGridColorProperty

`CMFCPropertyGridColorProperty` オブジェクトを構築します。

```
CMFCPropertyGridColorProperty(
    const CString& strName,
    const COLORREF& color,
    CPalette* pPalette = NULL,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0);
```

### <a name="parameters"></a>パラメーター

*strName*<br/>
からプロパティの名前。

*color*<br/>
からプロパティの色の値。

*pPalette*<br/>
から色のパレットへのポインター。 既定値は NULL です。

*lpszDescr*<br/>
からプロパティの説明。 既定値は NULL です。

*dwData*<br/>
から整数や、プロパティに関連付けられている他のデータへのポインターなど、アプリケーション固有のデータ。 既定値は 0 です。

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCPropertyGridColorProperty:: Enable自動ボタン

[色の選択] ダイアログボックスの [ *自動* ] ボタンを有効にします。 (標準の自動ボタンには [ **自動**] というラベルが付いています)。

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
から自動ボタンのラベルテキスト。

*colorAutomatic*<br/>
から自動 (既定) 色の RGB カラー値。

*bEnable*<br/>
から[自動] ボタンを有効にする場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a> CMFCPropertyGridColorProperty:: EnableOtherButton

[色の選択] ダイアログボックスの [ *その他* ] ボタンを有効にします。 ([その他] ボタンには、[その他の **色**] というラベルが付いています)。

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
から[その他] ボタンのラベルテキスト。

*Tcolordlg*<br/>
からダイアログボックスを表示する場合は TRUE `CMFCColorDialog` 。[標準色の選択] ダイアログボックスを表示する場合は FALSE。 既定値は TRUE です。

*bEnable*<br/>
から[その他] ボタンを表示する場合は TRUE。それ以外の場合は FALSE。  既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a> CMFCPropertyGridColorProperty:: GetColor

プロパティの現在の色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

RGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a> CMFCPropertyGridColorProperty:: SetColor

プロパティの新しい色を設定します。

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
からRGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a> CMFCPropertyGridColorProperty:: SetColumnsNumber

現在のカラー プロパティ グリッド内の列の数を指定します。

```cpp
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>パラメーター

*n コラム番号*<br/>
からColor プロパティグリッド内の列数を指定します。

### <a name="remarks"></a>解説

このメソッドは、保護されたデータメンバーの値を設定し `m_nColumnsNumber` ます。

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a> CMFCPropertyGridColorProperty:: SetOriginalValue

編集可能なプロパティの元の値を設定します。

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>パラメーター

*varValue*<br/>
から値。

### <a name="remarks"></a>解説

[Cmfcpropertygridproperty:: ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue)メソッドを使用して、編集されたプロパティの元の値をリセットします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty クラス](../../mfc/reference/cmfcpropertygridproperty-class.md)

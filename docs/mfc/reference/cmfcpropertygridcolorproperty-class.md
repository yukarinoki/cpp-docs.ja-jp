---
title: プロパティプロパティ
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
ms.openlocfilehash: 62015f384fa5f72ceeceed2605cbf9a6b646a1eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375326"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>プロパティプロパティ

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
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|色選択ダイアログ ボックスの*自動*ボタンを有効にします。 (標準の自動ボタンには**自動**と表示されます。|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|色選択ダイアログ ボックスの*他*のボタンを有効にします。 (標準の他のボタンには、**その他の色**のラベルが付いています。|
|`CMFCPropertyGridColorProperty::FormatProperty`|プロパティ値のテキスト表現の書式を設定します  (プロパティ[プロパティをオーバーライドします](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)。|
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|プロパティの現在の色を取得します。|
|`CMFCPropertyGridColorProperty::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|`CMFCPropertyGridColorProperty::OnClickButton`|プロパティに含まれているボタンをユーザーがクリックすると、フレームワークによって呼び出されます  ([プロパティプロパティをオーバーライドします。](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|プロパティ値を表示するためにフレームワークによって呼び出されます  ([プロパティプロパティ](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue)をオーバーライドします。|
|`CMFCPropertyGridColorProperty::OnEdit`|ユーザーがプロパティ値を変更しようとすると、フレームワークによって呼び出されます  (プロパティ[プロパティ](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit)をオーバーライドします。|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|編集可能なプロパティの値が変更されると、フレームワークによって呼び出されます  ([プロパティプロパティをオーバーライドします。](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue)|
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|プロパティの新しい色を設定します。|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|現在のカラー プロパティ グリッド内の列の数を指定します。|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|編集可能なプロパティの元の値を設定します。|

## <a name="remarks"></a>解説

`CMFCPropertyGridColorProperty` クラスは、プロパティ リスト コントロールに追加できるカラー プロパティをサポートします。 詳細については、「[クラス」を](../../mfc/reference/cmfcpropertygridctrl-class.md)参照してください。

## <a name="example"></a>例

`CMFCPropertyGridColorProperty` クラスのオブジェクトを構築する方法、および `CMFCPropertyGridColorProperty` クラスの各種メソッドを使用してこのオブジェクトを構成する方法を次の例に示します。 このコードでは、自動ボタンとその他ボタンを有効にする方法、および色と列番号を設定する方法を示しています。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpropertygridctrl.h

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a>プロパティプロパティ::プロパティ グリッド プロパティ

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
[in]プロパティの名前。

*色*<br/>
[in]プロパティのカラー値。

*をクリックします。*<br/>
[in]色のパレットへのポインター。 既定値は NULL です。

*lpszDescr*<br/>
[in]プロパティの説明。 既定値は NULL です。

*dw データ*<br/>
[in]整数やプロパティに関連付けられている他のデータへのポインターなど、アプリケーション固有のデータ。 既定値は 0 です。

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a>プロパティ::自動ボタンを有効にします。

色選択ダイアログ ボックスの*自動*ボタンを有効にします。 (標準の自動ボタンには**自動**と表示されます。

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]自動ボタンのラベル テキスト。

*カラー自動*<br/>
[in]自動 (既定) 色の RGB カラー値。

*b 有効にする*<br/>
[in]自動ボタンを有効にする場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a>プロパティ::その他のボタンを有効にします。

色選択ダイアログ ボックスの*他*のボタンを有効にします。 (標準の他のボタンには、**その他の色**のラベルが付いています。

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]もう一方のボタンのラベル テキスト。

*アルトカラードグルグ*<br/>
[in]ダイアログ ボックスを`CMFCColorDialog`表示する場合は TRUE。FALSE を指定すると、標準の色選択ダイアログ ボックスが表示されます。 既定値は TRUE です。

*b 有効にする*<br/>
[in]もう一方のボタンを表示する場合は TRUE。それ以外の場合は FALSE。  既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a>プロパティ::取得色

プロパティの現在の色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

RGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a>プロパティ::セットカラー

プロパティの新しい色を設定します。

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]RGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a>プロパティ::列番号

現在のカラー プロパティ グリッド内の列の数を指定します。

```
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>パラメーター

*数列番号*<br/>
[in]色プロパティ グリッド内の推奨される列数。

### <a name="remarks"></a>解説

このメソッドは、保護されたデータ`m_nColumnsNumber`メンバーの値を設定します。

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a>プロパティ::元の値を設定します。

編集可能なプロパティの元の値を設定します。

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>パラメーター

*値*<br/>
[in]値。

### <a name="remarks"></a>解説

編集された[プロパティ](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue)の元の値をリセットするには、メソッドを使用します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[プロパティプロパティ](../../mfc/reference/cmfcpropertygridproperty-class.md)

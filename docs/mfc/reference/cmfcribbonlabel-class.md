---
description: '詳細情報: CMFCRibbonLabel クラス'
title: CMFCRibbonLabel クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
ms.openlocfilehash: 0699e76dfe90b87cd813d18d076adf23f8512bee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321827"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel クラス

リボンのクリックできないテキスト ラベルを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|`CMFCRibbonLabel`指定したテキスト文字列を使用してオブジェクトを構築し、初期化します。|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonLabel::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCRibbonLabel:: Setのデータ](#setaccdata)|現在のリボンラベル要素のアクセシビリティデータを決定します。 ( [CMFCRibbonButton:: setのデータ](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata)をオーバーライドします)。|

### <a name="remarks"></a>解説

リボンラベルを作成したら、 [CMFCRibbonPanel:: add](../../mfc/reference/cmfcribbonpanel-class.md#add)を呼び出してパネルに追加します。

クイックアクセスツールバーにリボンラベルを追加することはできません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxRibbonLabel

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a> CMFCRibbonLabel::CMFCRibbonLabel

指定されたテキスト文字列を表示する [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) オブジェクトを構築し、初期化します。

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
からラベルに表示されるテキスト。

*bIsMultiLine*<br/>
からラベルが複数行のラベルであることを指定する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a> CMFCRibbonLabel:: Setのデータ

現在のリボンラベル要素のアクセシビリティデータを決定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
から現在のリボンラベルの親ウィンドウを表します。

*data*<br/>
入出力 `CAccessibilityData` 現在のリボンラベルのアクセシビリティデータを格納する型のオブジェクト。

### <a name="return-value"></a>戻り値

*データ* パラメーターに現在のリボンラベルのアクセシビリティデータが正常に設定された場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)

---
title: クラス
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
ms.openlocfilehash: cd30e374441661368d3ea7abf5177424f8dffb3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375124"
---
# <a name="cmfcribbonlabel-class"></a>クラス

リボンのクリックできないテキスト ラベルを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCリボンラベル::CMFCリボンラベル](#cmfcribbonlabel)|指定したテキスト文字列を使用`CMFCRibbonLabel`してオブジェクトを構築および初期化します。|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonLabel::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[を設定します。](#setaccdata)|現在のリボン ラベル要素のアクセシビリティ データを決定します。 (オーバーライド[CMFCリボンボタン:::セットアックデータ](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>解説

リボン ラベルを作成したら[、CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)を呼び出してパネルに追加します。

クイック アクセス ツールバーにリボン ラベルを追加することはできません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbonLabel.h

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a>CMFCリボンラベル::CMFCリボンラベル

指定したテキスト文字列を表示する[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)オブジェクトを構築および初期化します。

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]ラベルに表示するテキスト。

*ビスマルチライン*<br/>
[in]ラベルが複数行ラベルであることを指定する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a>を設定します。

現在のリボン ラベル要素のアクセシビリティ データを決定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*親*<br/>
[in]現在のリボン ラベルの親ウィンドウを表します。

*データ*<br/>
[アウト]現在のリボン`CAccessibilityData`ラベルのアクセシビリティ データが設定されている型のオブジェクト。

### <a name="return-value"></a>戻り値

現在のリボン ラベルのアクセシビリティ データが*データ*パラメーターに正常に設定された場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)

---
title: CMFCRibbonContextCaption クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5726605af6b9a0d63c15cb232a094d48dd2f95a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405874"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption クラス

リボン カテゴリまたはコンテキスト カテゴリの最上位に表示される色付きのキャプションを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCRibbonContextCaption::GetColor](#getcolor)|キャプションの色を返します。|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|

## <a name="remarks"></a>Remarks

このクラスを直接インスタンス化することはできません。 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)クラスを使用してこのクラス内部でのリボン カテゴリに色を追加します。

リボン カテゴリの色を設定するには、呼び出す[cmfcribboncategory::settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)します。 コンテキスト カテゴリの色を設定するには、呼び出す[cmfcribbonbar::addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxRibbonBar.h

##  <a name="getcolor"></a>  CMFCRibbonContextCaption::GetColor

キャプションの背景色を返します。

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>戻り値

返される値には、次の列挙値のいずれかを指定できます。

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>Remarks

キャプションの色を呼び出すことによって設定できる[cmfcribboncategory::settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)または[cmfcribbonbar::addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)します。

##  <a name="getrighttabx"></a>  CMFCRibbonContextCaption::GetRightTabX

カテゴリのリボン タブの右側の端の位置を取得します。

```
int GetRightTabX() const;
```

### <a name="return-value"></a>戻り値

それを囲む四角形の右辺の X 値を返します、`CMFCRibbonCategory`オブジェクトのリボン タブまたはタブが切り捨てられる場合は-1 の値。

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonCategory クラス](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)

---
description: '詳細情報: CMFCRibbonContextCaption クラス'
title: CMFCRibbonContextCaption クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: fa4134b89055274e4f44bef1150518207e06143e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293626"
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
|`CMFCRibbonContextCaption::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

## <a name="remarks"></a>解説

このクラスを直接インスタンス化することはできません。 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)クラスは、このクラスを内部的に使用して、リボンカテゴリに色を追加します。

リボンのカテゴリの色を設定するには、 [CMFCRibbonCategory:: SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)を呼び出します。 コンテキストカテゴリの色を設定するには、 [CMFCRibbonBar:: AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribbonbar.h

## <a name="cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a> CMFCRibbonContextCaption:: GetColor

キャプションの背景色を返します。

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>戻り値

返される値は、次の列挙値のいずれかになります。

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>解説

キャプションの色は、 [CMFCRibbonCategory:: SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) または [CMFCRibbonBar:: addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)を呼び出すことによって設定できます。

## <a name="cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a> CMFCRibbonContextCaption::GetRightTabX

カテゴリのリボンタブの右端の位置を取得します。

```
int GetRightTabX() const;
```

### <a name="return-value"></a>戻り値

オブジェクトのリボンタブの囲んでいる四角形の右側の X 値、 `CMFCRibbonCategory` またはタブが切り捨てられた場合は-1 の値を返します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonCategory クラス](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)

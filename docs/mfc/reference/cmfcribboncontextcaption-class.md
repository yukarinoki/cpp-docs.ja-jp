---
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
ms.openlocfilehash: 7aacbe23684914c91129d9962ae847d442cc411b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375214"
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
|`CMFCRibbonContextCaption::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

## <a name="remarks"></a>解説

このクラスを直接インスタンス化することはできません。 [CMFCRibbonBar クラスクラス](../../mfc/reference/cmfcribbonbar-class.md)は、リボン カテゴリに色を追加するために、内部的にこのクラスを使用します。

リボン カテゴリの色を設定するには[、CMFC リボン カテゴリ::セットタブカラー](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)を呼び出します。 コンテキスト カテゴリの色を設定するには[、CMFC リボン バー::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbonBar.h

## <a name="cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a>コンテキストキャプション::取得カラー

キャプションの背景色を返します。

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>戻り値

返される値は、次の列挙値のいずれかです。

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>解説

キャプションの色は、呼び出すことによって設定することができます[。](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)

## <a name="cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a>コンテキストキャプション::右タブ

カテゴリのリボン タブの右端の位置を取得します。

```
int GetRightTabX() const;
```

### <a name="return-value"></a>戻り値

`CMFCRibbonCategory`オブジェクトのリボン タブの囲む四角形の右側の X 値を返します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[クラス](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbar-class.md)

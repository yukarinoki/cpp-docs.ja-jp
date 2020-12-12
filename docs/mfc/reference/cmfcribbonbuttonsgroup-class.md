---
description: '詳細情報: CMFCRibbonButtonsGroup クラス'
title: CMFCRibbonButtonsGroup クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
ms.openlocfilehash: 0b86ce6ff21bd36daaac9d68ce511ae395141170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293831"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup クラス

`CMFCRibbonButtonsGroup`クラスを使用すると、一連のリボンボタンをグループにまとめることができます。 グループ内のすべてのボタンは互いに隣接して水平に並べられ、1 つの枠で囲まれます。

## <a name="syntax"></a>構文

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|`CMFCRibbonButtonsGroup` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonButtonsGroup:: AddButton](#addbutton)|グループにボタンを追加します。|
|[CMFCRibbonButtonsGroup:: AddButtons](#addbuttons)|グループにボタンの一覧を追加します。|
|[CMFCRibbonButtonsGroup:: GetButton](#getbutton)|指定したインデックス位置にあるボタンへのポインターを返します。|
|[CMFCRibbonButtonsGroup:: GetCount](#getcount)|グループ内のボタンの数を返します。|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|リボングループ内の通常のイメージのイメージサイズを返します ( [CMFCRibbonBaseElement:: GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize)をオーバーライドします)。|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します ( [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)をオーバーライドします)。|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|`CMFCRibbonButtonsGroup`オブジェクトにツールバー画像が含まれているかどうかを報告します。|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|ボタンが通常、強調表示、または無効になっているかどうかに応じて、指定したボタンの適切なイメージを描画します。|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|オブジェクトからすべてのボタンを削除 `CMFCRibbonButtonsGroup` します。|
|[CMFCRibbonButtonsGroup:: SetImages](#setimages)|グループにイメージを割り当てます。|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|`CMFCRibbonCategory`オブジェクトの親 `CMFCRibbonButtonsGroup` とその中のすべてのボタンを設定します ( [CMFCRibbonBaseElement:: setparentcategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory)をオーバーライドします)。|

## <a name="remarks"></a>解説

このグループは、 [Cmfcbaseribbonelement](../../mfc/reference/cmfcribbonbaseelement-class.md) から派生し、単一のエンティティとして操作できます。 グループは、任意のパネルまたはポップアップメニューに配置できます。

## <a name="example"></a>例

`CMFCRibbonButtonsGroup` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、オブジェクトを構築し `CMFCRibbonButtonsGroup` 、リボンのボタンのグループにイメージを割り当て、リボンのボタンのグループにボタンを追加する方法を示します。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribbonbuttonsgroup

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a> CMFCRibbonButtonsGroup:: AddButton

グループにボタンを追加します。

```cpp
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>パラメーター

*pButton*<br/>
から追加するボタンへのポインター。

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a> CMFCRibbonButtonsGroup:: AddButtons

グループにボタンの一覧を追加します。

```cpp
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>パラメーター

*lstButtons*<br/>
から追加するボタンへのポインターのリスト。

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a> CMFCRibbonButtonsGroup:: CMFCRibbonButtonsGroup

`CMFCRibbonButtonsGroup` オブジェクトを構築します。

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>パラメーター

*pButton*<br/>
から新しく作成されたオブジェクトに追加するボタンを指定し `CMFCRibbonButtonsGroup` ます。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a> CMFCRibbonButtonsGroup:: GetButton

指定したインデックス位置にあるボタンへのポインターを返します。

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>パラメーター

*i*<br/>
から返されるボタンの0から始まるインデックス。

### <a name="return-value"></a>戻り値

指定したインデックス位置にあるボタンへのポインター。 指定されたインデックスが範囲外の場合は NULL です。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a> CMFCRibbonButtonsGroup:: GetCount

グループ内のボタンの数を返します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

グループ内のボタンの数。

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a> CMFCRibbonButtonsGroup:: GetImageSize

保護されたメンバーのソースイメージのサイズを取得し `CMFCToolBarImages` `m_Images` ます。

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>戻り値

ツールバーイメージ (存在する場合) のソースイメージサイズを返し `CSize` ます。それ以外の場合は0を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonButtonsGroup:: GetRegularSize

リボングループ要素の最大サイズを取得します。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からリボングループのデバイスコンテキストへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a> CMFCRibbonButtonsGroup:: HasImages

`CMFCRibbonButtonsGroup`オブジェクトにツールバー画像が含まれているかどうかを報告します。

```
BOOL HasImages() const;
```

### <a name="return-value"></a>戻り値

保護された `CMFCToolBarImages` メンバーに `m_Images` 画像が含まれている場合は TRUE、そうでない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a> CMFCRibbonButtonsGroup:: OnDrawImage

ボタンが通常、強調表示、または無効になっているかどうかに応じて、指定したボタンの適切なイメージを描画します。

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からオブジェクトのデバイスコンテキストへのポインター `CMFCRibbonButtonsGroup` 。

*rectImage*<br/>
からイメージを描画する四角形。

*pButton*<br/>
からイメージを描画するボタン。

*nImageIndex*<br/>
からボタン上に描画するイメージのインデックス (通常、強調表示、または無効になっているボタンの3つのイメージ配列のいずれか)。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a> CMFCRibbonButtonsGroup:: RemoveAll

オブジェクトからすべてのボタンを削除 `CMFCRibbonButtonsGroup` します。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a> CMFCRibbonButtonsGroup:: SetImages

リボンのボタンのグループにイメージを割り当てます。

```cpp
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>パラメーター

*pImages*<br/>
から通常の画像。

*pHotImages*<br/>
からホットイメージ。

*pDisabledImages*<br/>
から無効なイメージ。

### <a name="remarks"></a>解説

`SetImages`グループにボタンを追加する前に、を呼び出します。 イメージの数は、グループに追加するボタンの数以上でなければなりません。

> [!NOTE]
> ホットイメージは、ユーザーがボタンの上にマウスを置いたときに表示されるイメージです。 無効な画像は、ボタンが無効になっているときに表示される画像です。

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a> CMFCRibbonButtonsGroup:: SetParentCategory

`CMFCRibbonCategory`オブジェクトの親 `CMFCRibbonButtonsGroup` とその中のすべてのボタンを設定します。

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>パラメーター

*pCategory*<br/>
から設定する親カテゴリへのポインター (リボンコントロールのタブ付きグループはカテゴリと呼ばれます)。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)

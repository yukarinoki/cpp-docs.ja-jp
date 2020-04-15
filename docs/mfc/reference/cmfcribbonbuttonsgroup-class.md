---
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
ms.openlocfilehash: af5919ff2a72fc2aa1eeeb95fc93afbe9e743582
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375288"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup クラス

この`CMFCRibbonButtonsGroup`クラスでは、リボン ボタンのセットをグループに整理できます。 グループ内のすべてのボタンは互いに隣接して水平に並べられ、1 つの枠で囲まれます。

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
|[グループ:ボタンの追加](#addbutton)|ボタンをグループに追加します。|
|[グループ:ボタンの追加](#addbuttons)|ボタンのリストをグループに追加します。|
|[グループをクリックします。](#getbutton)|指定したインデックス位置にあるボタンへのポインターを返します。|
|[グループを取得します。](#getcount)|グループ内のボタンの数を返します。|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|リボン グループ内の通常のイメージのイメージ サイズを返します (オーバーライド[します](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize)。|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します ([オーバーライド](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)します。|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|オブジェクトにツールバー`CMFCRibbonButtonsGroup`イメージが含まれているかどうかを報告します。|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|ボタンが標準であるか、強調表示されているか、または無効であるかに応じて、指定したボタンに適したイメージを描画します。|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|オブジェクトからすべてのボタンを`CMFCRibbonButtonsGroup`削除します。|
|[グループ::セットイメージズ](#setimages)|グループにイメージを割り当てます。|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|オブジェクトの親`CMFCRibbonCategory`とその中のすべてのボタンを設定します (オーバーライドします。 [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory) `CMFCRibbonButtonsGroup`|

## <a name="remarks"></a>解説

グループは[CMFCBaseRibbonElement から](../../mfc/reference/cmfcribbonbaseelement-class.md)派生し、単一のエンティティとして操作できます。 グループは、任意のパネルまたはポップアップメニューに配置できます。

## <a name="example"></a>例

`CMFCRibbonButtonsGroup` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、オブジェクトの`CMFCRibbonButtonsGroup`作成方法、リボン ボタンのグループにイメージを割り当て、リボン ボタンのグループにボタンを追加する方法を示します。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxリボンボタングループ.h

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a>グループ:ボタンの追加

ボタンをグループに追加します。

```
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>パラメーター

*ボタン*<br/>
[in]追加するボタンへのポインター。

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a>グループ:ボタンの追加

ボタンのリストをグループに追加します。

```
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>パラメーター

*ボタン*<br/>
[in]追加するボタンへのポインターのリスト。

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a>グループ::CMFCリボンボタングループ

`CMFCRibbonButtonsGroup` オブジェクトを構築します。

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>パラメーター

*ボタン*<br/>
[in]新しく作成`CMFCRibbonButtonsGroup`したオブジェクトに追加するボタンを指定します。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a>グループをクリックします。

指定したインデックス位置にあるボタンへのポインターを返します。

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>パラメーター

*私*<br/>
[in]返すボタンの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定したインデックス位置にあるボタンへのポインター。 指定したインデックスが範囲外の場合は NULL です。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a>グループを取得します。

グループ内のボタンの数を返します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

グループ内のボタンの数。

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a>グループ::イメージサイズ

保護された`CMFCToolBarImages`メンバ`m_Images`のソース イメージ サイズを取得します。

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>戻り値

ツール バー イメージのソース イメージ サイズ (存在する場合)`CSize`を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a>グループ::ゲットレギュラーサイズ

リボン グループ要素の最大サイズを取得します。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]リボン グループのデバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a>グループ::HasImages

オブジェクトにツールバー`CMFCRibbonButtonsGroup`イメージが含まれているかどうかを報告します。

```
BOOL HasImages() const;
```

### <a name="return-value"></a>戻り値

保護された`CMFCToolBarImages`メンバー`m_Images`にイメージが含まれている場合は TRUE を返し、含まれていない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a>グループ::アドオン

ボタンが標準であるか、強調表示されているか、または無効であるかに応じて、指定したボタンに適したイメージを描画します。

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]`CMFCRibbonButtonsGroup`オブジェクトのデバイス コンテキストへのポインター。

*レクトイメージ*<br/>
[in]イメージを描画する四角形。

*ボタン*<br/>
[in]イメージを描画するボタン。

*インデックスを使用します。*<br/>
[in]ボタンに描画するイメージのインデックス (通常のボタン、ハイライトされたボタン、または無効になっている 3 つのイメージ配列のいずれか)。

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a>グループ::すべて削除

オブジェクトからすべてのボタンを`CMFCRibbonButtonsGroup`削除します。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a>グループ::セットイメージズ

リボン ボタンのグループにイメージを割り当てます。

```
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>パラメーター

*pイメージズ*<br/>
[in]通常の画像。

*イメージズ*<br/>
[in]ホット画像。

*を無効にします。*<br/>
[in]無効な画像。

### <a name="remarks"></a>解説

グループ`SetImages`にボタンを追加する前に電話をかけます。 画像の数は、グループに追加するボタンの数以上でなければなりません。

> [!NOTE]
> ホットイメージは、ユーザーがボタンの上に置いたときに表示される画像です。 無効にされたイメージとは、ボタンが無効になっているときに表示されるイメージです。

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a>グループ::親カテゴリを設定します。

`CMFCRibbonButtonsGroup`オブジェクトの親`CMFCRibbonCategory`と、その中のすべてのボタンを設定します。

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>パラメーター

*カテゴリ*<br/>
[in]設定する親カテゴリへのポインター (リボン コントロールのタブ付きグループはカテゴリと呼ばれます)。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)

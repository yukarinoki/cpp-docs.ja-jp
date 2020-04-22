---
title: コンボボックス クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: 6c90bb1ce464a90295e7edb933d87594444c3648
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745320"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>コンボボックス クラス

ユーザーがフォント サイズを選択できるようにするコンボ ボックス コントロールを含むツール バー ボタン。

## <a name="syntax"></a>構文

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[コンボボックス::CMFCツールバーフォントサイズコンボボックス](#cmfctoolbarfontsizecombobox)|`CMFCToolBarFontSizeComboBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コンボボックス::ゲットトウィップサイズ](#gettwipsize)|選択したフォント サイズを twip 単位で返します。|
|[コンボボックス::フォントサイズの再構築](#rebuildfontsizes)|指定したフォントでサポートされているすべてのフォント サイズをコンボ ボックスの一覧に塗りつぶします。|
|[コンボボックス::セットトウィプサイズ](#settwipsize)|twip のフォント サイズを設定します。|

## <a name="remarks"></a>解説

オブジェクトを`CMFCToolBarFontSizeComboBox` [CMFCToolBarFontCombo クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)と共に使用して、ユーザーがフォントとフォント サイズを選択できるようにします。

フォント サイズのコンボ ボックス ボタンは、フォント コンボ ボックス ボタンを追加するのと同じように、ツール バーに追加できます。 詳細については、「[クラスを表示します](../../mfc/reference/cmfctoolbarfontcombobox-class.md)。

ユーザーがオブジェクト内の新しいフォントを`CMFCToolBarFontComboBox`選択すると[、CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)メソッドを使用して、フォントサイズコンボボックスにそのフォントでサポートされているサイズを塗りつぶすことができます。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用してオブジェクトを構成する方法を`CMFCToolBarFontSizeComboBox`次の例に`CMFCToolBarFontSizeComboBox`示します。 この例では、テキスト ボックスからフォント サイズを twip 単位で取得し、指定されたフォントの有効なすべてのサイズをフォント サイズコンボ ボックスに入力し、フォント サイズを twip 単位で指定する方法を示します。 このコード スニペットは、 [Word パッド サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[コンボボックスボタン](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[コンボボックス](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールバーフォントコンボボックス.h

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a>コンボボックス::CMFCツールバーフォントサイズコンボボックス

`CMFCToolBarFontSizeComboBox` オブジェクトを構築します。

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a>コンボボックス::ゲットトウィップサイズ

フォント サイズコンボ ボックスのテキスト ボックスから、twip 単位のフォント サイズを取得します。

```
int GetTwipSize() const;
```

### <a name="return-value"></a>戻り値

戻り値が正の場合は、twip のフォント サイズです。 コンボ ボックスのテキスト ボックスが空の場合は -1 です。 エラーが発生した場合は -2 です。

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a>コンボボックス::フォントサイズの再構築

指定したフォントの有効なすべてのサイズをフォント サイズコンボ ボックスに塗りつぶします。

```cpp
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>パラメーター

*フォント名*<br/>
[in]フォント名を指定します。

### <a name="remarks"></a>解説

この関数は、フォント コンボ ボックスの選択と[、CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)などのフォント サイズコンボ ボックスの間で同期をとる場合に呼び出します。

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a>コンボボックス::セットトウィプサイズ

指定したサイズ (twip 単位) をポイント単位で最も近いサイズに丸めた後、コンボ ボックスで選択したサイズをその値に設定します。

```cpp
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>パラメーター

*Nsize*<br/>
[in]設定するフォント サイズ (twip 単位) を指定します。

### <a name="remarks"></a>解説

メソッドを呼び出すことによって、前の有効な[フォント サイズ](#gettwipsize)を後で取得できます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[ボタンを置き換える](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)

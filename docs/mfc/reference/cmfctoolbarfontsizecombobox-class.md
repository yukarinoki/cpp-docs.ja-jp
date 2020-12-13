---
description: '詳細情報: CMFCToolBarFontSizeComboBox クラス'
title: CMFCToolBarFontSizeComboBox クラス
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
ms.openlocfilehash: a355e62f2ef538372d70b9b2b393bc16bff2ef4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331754"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox クラス

ユーザーがフォントサイズを選択できるようにするコンボボックスコントロールを含むツールバーボタン。

## <a name="syntax"></a>構文

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox:: CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|`CMFCToolBarFontSizeComboBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox:: GetTwipSize](#gettwipsize)|選択されたフォントサイズを twip 単位で返します。|
|[CMFCToolBarFontSizeComboBox:: RebuildFontSizes](#rebuildfontsizes)|コンボボックスの一覧に、指定したフォントでサポートされているすべてのフォントサイズを設定します。|
|[CMFCToolBarFontSizeComboBox:: SetTwipSize](#settwipsize)|フォントサイズを twip 単位で設定します。|

## <a name="remarks"></a>解説

`CMFCToolBarFontSizeComboBox`オブジェクトを[Cmfctoolbarfontcombobox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)オブジェクトと共に使用して、ユーザーがフォントおよびフォントサイズを選択できるようにすることができます。

フォントサイズのコンボボックスボタンをツールバーに追加するには、フォントのコンボボックスボタンを追加します。 詳細については、「 [Cmfctoolbarfontcombobox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)」を参照してください。

ユーザーがオブジェクトで新しいフォントを選択すると `CMFCToolBarFontComboBox` 、 [Cmfctoolbarfontsizecombobox:: RebuildFontSizes](#rebuildfontsizes) メソッドを使用して、フォントサイズのコンボボックスに、そのフォントでサポートされているサイズを設定できます。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用してオブジェクトを構成する方法を次の例に示し `CMFCToolBarFontSizeComboBox` `CMFCToolBarFontSizeComboBox` ます。 この例では、テキストボックスからフォントサイズを twip 単位で取得し、[フォントサイズ] コンボボックスに特定のフォントの有効なサイズを入力し、フォントサイズを twip 単位で指定する方法を示します。 このコード スニペットは、 [Word パッド サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxtoolbarfontcombobox

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a> CMFCToolBarFontSizeComboBox:: CMFCToolBarFontSizeComboBox

`CMFCToolBarFontSizeComboBox` オブジェクトを構築します。

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a> CMFCToolBarFontSizeComboBox:: GetTwipSize

フォントサイズコンボボックスのテキストボックスからフォントサイズを twip 単位で取得します。

```
int GetTwipSize() const;
```

### <a name="return-value"></a>戻り値

戻り値が正の場合は、twip 単位のフォントサイズになります。 コンボボックスのテキストボックスが空の場合は、-1 になります。 エラーが発生した場合は、-2 になります。

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a> CMFCToolBarFontSizeComboBox:: RebuildFontSizes

フォントサイズコンボボックスに、指定したフォントのすべての有効なサイズを設定します。

```cpp
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>パラメーター

*strFontName*<br/>
からフォント名を指定します。

### <a name="remarks"></a>解説

フォントコンボボックス内の選択項目と、 [Cmfctoolbarfontcombobox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)などのフォントサイズコンボボックスを同期する場合に、この関数を呼び出します。

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a> CMFCToolBarFontSizeComboBox:: SetTwipSize

指定されたサイズ (twip 単位) をポイントの最も近いサイズに丸め、コンボボックスで選択したサイズをその値に設定します。

```cpp
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>パラメーター

*nSize*<br/>
から設定するフォントサイズ (twip 単位) を指定します。

### <a name="remarks"></a>解説

以前に有効なフォントサイズを取得するには、後で [Cmfctoolbarfontsizecombox:: GetTwipSize](#gettwipsize) メソッドを呼び出します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツールバーへのコントロールの配置](../../mfc/walkthrough-putting-controls-on-toolbars.md)

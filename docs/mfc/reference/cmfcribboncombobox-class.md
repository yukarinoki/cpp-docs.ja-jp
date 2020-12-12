---
description: '詳細情報: CMFCRibbonComboBox クラス'
title: CMFCRibbonComboBox クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: be4078145817d06fafddb76f2cefbd0df0083503
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293667"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox クラス

クラスは、リボン `CMFCRibbonComboBox` バー、リボンパネル、またはリボンポップアップメニューに追加できるコンボボックスコントロールを実装します。

## <a name="syntax"></a>構文

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonComboBox:: CMFCRibbonComboBox](#cmfcribboncombobox)|CMFCRibbonComboBox オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonComboBox:: AddItem](#additem)|リストボックスに一意の項目を追加します。|
|[CMFCRibbonComboBox::D eleteItem](#deleteitem)|指定した項目をリストボックスから削除します。|
|[CMFCRibbonComboBox:: EnableDropDownListResize](#enabledropdownlistresize)|リストボックスがドロップダウンしたときにサイズを変更できるかどうかを指定します。|
|[CMFCRibbonComboBox:: FindItem](#finditem)|リストボックス内で、指定した文字列と一致する最初の項目のインデックスを返します。|
|[CMFCRibbonComboBox:: GetCount](#getcount)|リストボックス内の項目の数を返します。|
|[CMFCRibbonComboBox:: GetCurSel](#getcursel)|リストボックス内で現在選択されている項目のインデックスを取得します。|
|[CMFCRibbonComboBox:: GetDropDownHeight](#getdropdownheight)|リストボックスがドロップダウンされたときのリストボックスの高さを取得します。|
|[CMFCRibbonComboBox:: GetIntermediateSize](#getintermediatesize)|中間モードで表示されるコンボボックスのサイズを返します。|
|[CMFCRibbonComboBox:: GetItem](#getitem)|リストボックス内の指定したインデックス位置にある項目に関連付けられている文字列を返します。|
|[CMFCRibbonComboBox:: GetItemData](#getitemdata)|リストボックス内の指定したインデックス位置にある項目に関連付けられたデータを返します。|
|[CMFCRibbonComboBox:: HasEditBox](#haseditbox)|コントロールにエディットボックスが含まれているかどうかを示します。|
|[CMFCRibbonComboBox:: IsResizeDropDownList](#isresizedropdownlist)|リストボックスのサイズを変更できるかどうかを示します。|
|[CMFCRibbonComboBox:: OnSelectItem](#onselectitem)|ユーザーがリストボックス内の項目を選択すると、フレームワークによって呼び出されます。|
|[CMFCRibbonComboBox:: RemoveAllItems](#removeallitems)|リストボックスからすべての項目を削除し、エディットボックスをクリアします。|
|[CMFCRibbonComboBox:: SelectItem](#selectitem)|リストボックス内の項目を選択します。|
|[CMFCRibbonComboBox:: SetDropDownHeight](#setdropdownheight)|リストボックスがドロップダウンされたときの高さを設定します。|

## <a name="remarks"></a>解説

リボンコンボボックスは、ユーザーが編集できる静的ラベルまたはラベルと組み合わせたリストボックスで構成されます。 リボンコンボボックスを作成するときに、使用する種類を指定する必要があります。

## <a name="example"></a>例

次の例では、クラスのオブジェクトを作成し、 `CMFCRibbonComboBox` コンボボックスに項目を追加し、コンボボックスで項目を選択し、パネルにコンボボックスを追加する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribboncombobox

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a> CMFCRibbonComboBox:: AddItem

リストボックスに一意の項目を追加します。

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>パラメーター

*lpszItem*<br/>
から追加する項目の文字列。

*dwData*<br/>
から追加する項目に関連付けられているデータ。

### <a name="return-value"></a>戻り値

追加された項目の0から始まるインデックス。

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a> CMFCRibbonComboBox:: CMFCRibbonComboBox

`CMFCRibbonComboBox` オブジェクトを構築します。

```cpp
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
からコンボボックスの ID。

*bHasEditBox*<br/>
からコントロール内にエディットボックスが必要な場合は TRUE。それ以外の場合は FALSE。

*nWidth*<br/>
からコンボボックスの幅 (ピクセル単位)。既定の幅の場合は-1。

*lpszLabel*<br/>
からコンボボックスの表示ラベル。

*nImage*<br/>
からコンボボックスの小さいイメージインデックス。

### <a name="remarks"></a>解説

既定の幅は108ピクセルです。

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a> CMFCRibbonComboBox::D eleteItem

指定した項目をリストボックスから削除します。

```cpp
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
から削除する項目の0から始まるインデックス。

*dwData*<br/>
から削除する項目に関連付けられているデータ。

*lpszText*<br/>
から削除する項目の文字列。 同じ文字列の項目が複数ある場合、最初の項目は削除されます。

### <a name="return-value"></a>戻り値

指定した項目が削除された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a> CMFCRibbonComboBox:: EnableDropDownListResize

リストボックスがドロップダウンしたときにサイズを変更できるかどうかを指定します。

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からサイズ変更を有効にする場合は TRUE。サイズ変更を無効にする場合は FALSE。

### <a name="remarks"></a>解説

サイズ変更が有効になっている場合、リストボックスは、表示される項目に応じてサイズを変更します。

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a> CMFCRibbonComboBox:: FindItem

リストボックス内で、指定した文字列と一致する最初の項目のインデックスを返します。

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
からリストボックス内の項目の文字列。

### <a name="return-value"></a>戻り値

項目の0から始まるインデックス。項目が見つからない場合は-1。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a> CMFCRibbonComboBox:: GetCount

リストボックス内の項目の数を返します。

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

リストボックス内の項目の数。リストボックスに項目が含まれていない場合は0。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a> CMFCRibbonComboBox:: GetCurSel

リストボックス内で現在選択されている項目のインデックスを取得します。

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

リストボックス内で現在選択されている項目の0から始まるインデックス。または、項目が選択されていない場合は-1 になります。

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a> CMFCRibbonComboBox:: GetDropDownHeight

リストボックスがドロップダウンされたときのリストボックスの高さを取得します。

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>戻り値

リストボックスの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a> CMFCRibbonComboBox:: GetIntermediateSize

中間モードで表示されるコンボボックスのサイズを返します。

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からコンボボックスのデバイスコンテキストへのポインター。

### <a name="return-value"></a>戻り値

コンボボックスのサイズ。

### <a name="remarks"></a>解説

返されるサイズは、小さい画像を表示するときのコンボボックスのサイズに基づいています。

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a> CMFCRibbonComboBox:: GetItem

リストボックス内の指定したインデックス位置にある項目に関連付けられている文字列を返します。

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
からリストボックス内の項目の0から始まるインデックス。

### <a name="return-value"></a>戻り値

項目に関連付けられている文字列へのポインター。それ以外の場合は、index パラメーターが無効であるか、またはインデックスパラメーターが-1 で、コンボボックスに項目が選択されていない場合は NULL になります。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a> CMFCRibbonComboBox:: GetItemData

リストボックス内の指定したインデックス位置にある項目に関連付けられたデータを返します。

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
からリストボックス内の項目の0から始まるインデックス。

### <a name="return-value"></a>戻り値

項目に関連付けられているデータ。項目が存在しない場合、またはインデックスパラメーターが-1 で、リストボックスに項目が選択されていない場合は0。

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a> CMFCRibbonComboBox:: HasEditBox

コントロールにエディットボックスが含まれているかどうかを示します。

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>戻り値

コントロールにエディットボックスが含まれている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a> CMFCRibbonComboBox:: IsResizeDropDownList

リストボックスのサイズを変更できるかどうかを示します。

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>戻り値

リストボックスのサイズを変更できる場合は TRUE。それ以外の場合は FALSE。 [CMFCRibbonComboBox:: EnableDropDownListResize](#enabledropdownlistresize)

### <a name="remarks"></a>解説

[CMFCRibbonComboBox:: EnableDropDownListResize](#enabledropdownlistresize)メソッドを使用して、リストボックスのサイズ変更を有効にすることができます。

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a> CMFCRibbonComboBox:: OnSelectItem

ユーザーがリストボックス内の項目を選択すると、フレームワークによって呼び出されます。

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
から選択された項目のインデックス。

### <a name="remarks"></a>解説

ユーザー入力の選択を処理する場合は、このメソッドをオーバーライドします。

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a> CMFCRibbonComboBox:: RemoveAllItems

リストボックスからすべての項目を削除し、エディットボックスをクリアします。

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a> CMFCRibbonComboBox:: SelectItem

リストボックス内の項目を選択します。

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
からリストボックス内の項目の0から始まるインデックス。

*dwData*<br/>
からリストボックス内の項目に関連付けられているデータ。

*lpszText*<br/>
からリストボックス内の項目の文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a> CMFCRibbonComboBox:: SetDropDownHeight

リストボックスがドロップダウンされたときの高さを設定します。

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>パラメーター

*nHeight*<br/>
からリストボックスの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

既定の高さは150ピクセルです。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonEdit クラス](../../mfc/reference/cmfcribbonedit-class.md)

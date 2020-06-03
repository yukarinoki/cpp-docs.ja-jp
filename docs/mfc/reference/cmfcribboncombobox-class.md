---
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
ms.openlocfilehash: 5846b1c5590a756f0a0820583af3d0b159968ea2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375228"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox クラス

この`CMFCRibbonComboBox`クラスは、リボン バー、リボン パネル、またはリボン ポップアップ メニューに追加できるコンボ ボックス コントロールを実装します。

## <a name="syntax"></a>構文

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[コンボボックス::CMFCリボンコンボボックス](#cmfcribboncombobox)|オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コンボボックス::アイテムの追加](#additem)|リスト ボックスに一意の項目を追加します。|
|[コトリボンコンボボックス::Dエレテアイテム](#deleteitem)|リスト ボックスから指定した項目を削除します。|
|[コンボボックス::ドロップダウンリストのサイズ変更を有効にします。](#enabledropdownlistresize)|ドロップダウンしたときにリスト ボックスのサイズを変更できるかどうかを指定します。|
|[コンボボックスを検索します。](#finditem)|指定した文字列に一致するリスト ボックス内の最初の項目のインデックスを返します。|
|[コンボボックス::カウントを取得します。](#getcount)|リスト ボックス内の項目数を返します。|
|[コンボボックス::ゲットカーセル](#getcursel)|リスト ボックス内で現在選択されている項目のインデックスを取得します。|
|[コンボボックス::ゲットドロップダウンハイト](#getdropdownheight)|リスト ボックスがドロップダウンされたときのリスト ボックスの高さを取得します。|
|[コンボボックス::取得中間サイズ](#getintermediatesize)|中間モードで表示されるコンボ ボックスのサイズを返します。|
|[コンボボックス::ゲットアイテム](#getitem)|リスト ボックス内の指定したインデックスにある項目に関連付けられた文字列を返します。|
|[コンボボックス::ゲットアイテムデータ](#getitemdata)|リスト ボックス内の指定したインデックスにある項目に関連付けられたデータを返します。|
|[コンボボックスを使用します。](#haseditbox)|コントロールにエディット ボックスが含まれているかどうかを示します。|
|[コンボボックス::イズリサイズドロップダウンリスト](#isresizedropdownlist)|リスト ボックスのサイズを変更できるかどうかを示します。|
|[コンボボックス::オンセレクトアイテム](#onselectitem)|ユーザーがリスト ボックス内の項目を選択したときに、フレームワークによって呼び出されます。|
|[コンボボックス::すべてのアイテムを削除します。](#removeallitems)|リスト ボックスからすべての項目を削除し、編集ボックスをクリアします。|
|[コンボボックス::アイテムを選択します。](#selectitem)|リスト ボックス内の項目を選択します。|
|[コンボボックス::セットドロップダウンハイト](#setdropdownheight)|ドロップダウンしたときのリスト ボックスの高さを設定します。|

## <a name="remarks"></a>解説

リボン コンボ ボックスは、リスト ボックスと、ユーザーが編集できる静的ラベルまたはラベルを組み合わせたもので構成されます。 リボン コンボ ボックスを作成するときに、必要な種類を指定する必要があります。

## <a name="example"></a>例

`CMFCRibbonComboBox`クラスのオブジェクトを構築し、コンボ ボックスに項目を追加し、コンボ ボックス内の項目を選択して、パネルにコンボ ボックスを追加する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbon コンボボックス.h

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a>コンボボックス::アイテムの追加

リスト ボックスに一意の項目を追加します。

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]追加する項目の文字列。

*dw データ*<br/>
[in]追加する項目に関連付けられているデータ。

### <a name="return-value"></a>戻り値

追加された項目の 0 から始まるインデックス。

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a>コンボボックス::CMFCリボンコンボボックス

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
[in]コンボ ボックスの ID。

*ボックス*<br/>
[in]コントロール内にエディット ボックスを設定する場合は TRUE。それ以外の場合は FALSE。

*n幅*<br/>
[in]コンボ ボックスの幅 (ピクセル単位)。既定の幅の場合は -1。

*ラベル*<br/>
[in]コンボ ボックスの表示ラベル。

*nイメージ*<br/>
[in]コンボ ボックスの小さいイメージ インデックス。

### <a name="remarks"></a>解説

既定の幅は 108 ピクセルです。

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a>コトリボンコンボボックス::Dエレテアイテム

リスト ボックスから指定した項目を削除します。

```cpp
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]削除する項目の 0 から始まるインデックス。

*dw データ*<br/>
[in]削除するアイテムに関連付けられているデータ。

*lpszText*<br/>
[in]削除する項目の文字列。 同じ文字列を持つ複数の項目がある場合、最初の項目は削除されます。

### <a name="return-value"></a>戻り値

指定された項目が削除された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a>コンボボックス::ドロップダウンリストのサイズ変更を有効にします。

ドロップダウンしたときにリスト ボックスのサイズを変更できるかどうかを指定します。

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]サイズ変更を有効にする場合は TRUE。FALSE を指定すると、サイズ変更を無効にします。

### <a name="remarks"></a>解説

サイズ変更を有効にすると、リスト ボックスのサイズは表示される項目に合わせて変更されます。

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a>コンボボックスを検索します。

指定した文字列に一致するリスト ボックス内の最初の項目のインデックスを返します。

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]リスト ボックス内の項目の文字列。

### <a name="return-value"></a>戻り値

項目の 0 から始まるインデックス。アイテムが見つからない場合は -1。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a>コンボボックス::カウントを取得します。

リスト ボックス内の項目数を返します。

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の項目数を指定します。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a>コンボボックス::ゲットカーセル

リスト ボックス内で現在選択されている項目のインデックスを取得します。

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内で現在選択されている項目の 0 から始まるインデックス。項目が選択されていない場合は -1 を指定します。

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a>コンボボックス::ゲットドロップダウンハイト

リスト ボックスがドロップダウンされたときのリスト ボックスの高さを取得します。

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>戻り値

リスト ボックスの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a>コンボボックス::取得中間サイズ

中間モードで表示されるコンボ ボックスのサイズを返します。

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]コンボ ボックスのデバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

コンボ ボックスのサイズ。

### <a name="remarks"></a>解説

返されるサイズは、小さいイメージを表示するときのコンボ ボックスのサイズに基づいています。

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a>コンボボックス::ゲットアイテム

リスト ボックス内の指定したインデックスにある項目に関連付けられた文字列を返します。

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

項目に関連付けられている文字列へのポインター。それ以外の場合は、インデックス パラメーターが無効な場合、またはインデックス パラメーターが -1 で、コンボ ボックスで項目が選択されていない場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a>コンボボックス::ゲットアイテムデータ

リスト ボックス内の指定したインデックスにある項目に関連付けられたデータを返します。

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

アイテムに関連付けられているデータ。項目が存在しない場合、または index パラメーターが -1 で、リスト ボックスに選択されている項目がない場合は 0。

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a>コンボボックスを使用します。

コントロールにエディット ボックスが含まれているかどうかを示します。

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>戻り値

コントロールにエディット ボックスが含まれている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a>コンボボックス::イズリサイズドロップダウンリスト

リスト ボックスのサイズを変更できるかどうかを示します。

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>戻り値

リスト ボックスのサイズを変更できる場合は TRUE。それ以外の場合は FALSE。 [コンボボックス::ドロップダウンリストのサイズ変更を有効にします。](#enabledropdownlistresize)

### <a name="remarks"></a>解説

リスト ボックスのサイズ変更を有効にするには、[メソッド](#enabledropdownlistresize)を使用します。

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a>コンボボックス::オンセレクトアイテム

ユーザーがリスト ボックス内の項目を選択したときに、フレームワークによって呼び出されます。

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
[in]選択した項目のインデックス。

### <a name="remarks"></a>解説

ユーザー入力の選択を処理する場合は、このメソッドをオーバーライドします。

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a>コンボボックス::すべてのアイテムを削除します。

リスト ボックスからすべての項目を削除し、編集ボックスをクリアします。

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a>コンボボックス::アイテムを選択します。

リスト ボックス内の項目を選択します。

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

*dw データ*<br/>
[in]リスト ボックス内の項目に関連付けられているデータ。

*lpszText*<br/>
[in]リスト ボックス内の項目の文字列。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a>コンボボックス::セットドロップダウンハイト

ドロップダウンしたときのリスト ボックスの高さを設定します。

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>パラメーター

*nHeight*<br/>
[in]リスト ボックスの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

既定の高さは 150 ピクセルです。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonEdit クラス](../../mfc/reference/cmfcribbonedit-class.md)

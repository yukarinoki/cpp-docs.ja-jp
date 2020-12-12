---
description: '詳細情報: CMFCRibbonUndoButton クラス'
title: CMFCRibbonUndoButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: 8bfc02b61160a5f11a6913736c5dc784c4d00ce4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264935"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton クラス

クラスには、 `CMFCRibbonUndoButton` 最新のユーザーコマンドを含むドロップダウンリストボタンが実装されています。 ユーザーは、ドロップダウンリストから、最新のコマンドを1つ以上選択して、再実行または元に戻すことができます。

## <a name="syntax"></a>構文

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|指定した `CMFCRibbonUndoButton` コマンド ID、テキストラベル、および親オブジェクトのイメージリストのイメージを使用して、新しいオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|アクションの一覧に新しいアクションを追加します。|
|[CMFCRibbonUndoButton:: CleanUpUndoList](#cleanupundolist)|ドロップダウンリストのアクションリストをクリアします。|
|[CMFCRibbonUndoButton:: GetActionNumber](#getactionnumber)|ユーザーがドロップダウンリストから選択した項目の数を確認します。|
|[CMFCRibbonUndoButton:: HasMenu](#hasmenu)|オブジェクトにメニューが含まれているかどうかを示します。|

## <a name="remarks"></a>解説

クラスは、 `CMFCRibbonUndoButton` スタックを使用してドロップダウンリストを表します。

## <a name="example"></a>例

次の例は、クラスのオブジェクトを構築 `CMFCRibbonUndoButton` し、アクションの一覧に新しいアクションを追加する方法を示しています。 このコードスニペットは、リボンの [ガジェットサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribbonundobutton

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a> CMFCRibbonUndoButton::AddUndoAction

アクションの一覧に新しいアクションを追加します。

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
からドロップダウンリストに表示されるアクションラベル。

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a> CMFCRibbonUndoButton:: CleanUpUndoList

ドロップダウンリストのアクションリストをクリアします。

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a> CMFCRibbonUndoButton::CMFCRibbonUndoButton

指定した `CMFCRibbonUndoButton` コマンド ID、テキストラベル、および親オブジェクトのイメージリストのイメージを使用して、新しいオブジェクトを構築します。

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
からコマンド識別子を指定します。

*lpszText*<br/>
からボタンのテキストラベルを指定します。

*nSmallImageIndex*<br/>
からボタンの小さい画像の親オブジェクトのイメージリストの0から始まるインデックス。

*nLargeImageIndex*<br/>
からボタンの大きな画像の親オブジェクトのイメージリストの0から始まるインデックス。

*hIcon*<br/>
からボタンのイメージとして使用できるアイコンを示すハンドル。

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a> CMFCRibbonUndoButton:: GetActionNumber

ユーザーがドロップダウンリストから選択した項目の数を確認します。

```
int GetActionNumber() const;
```

### <a name="return-value"></a>戻り値

ユーザーが選択した項目の数。

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a> CMFCRibbonUndoButton:: HasMenu

オブジェクトにメニューが含まれているかどうかを示します。

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)

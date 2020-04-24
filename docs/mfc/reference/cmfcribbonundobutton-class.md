---
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
ms.openlocfilehash: 15cf93d39057f0e235779d47cf24d920d80a807d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753494"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton クラス

クラス`CMFCRibbonUndoButton`は、最新のユーザー コマンドを含むドロップダウン リスト ボタンを実装します。 ユーザーは、ドロップダウン リストから最新のコマンドを 1 つ以上選択して、やり直しまたは元に戻すことができます。

## <a name="syntax"></a>構文

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ボタンを押す](#cmfcribbonundobutton)|指定したコマンド`CMFCRibbonUndoButton`ID、テキスト ラベル、および親オブジェクトのイメージ リストのイメージを使用して、新しいオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ボタンを押す:アクションを追加します。](#addundoaction)|アクションのリストに新しいアクションを追加します。|
|[ボタン::クリーンアップ元に戻すリスト](#cleanupundolist)|アクション リスト (ドロップダウン リスト) をクリアします。|
|[ボタンを押します。](#getactionnumber)|ユーザーがドロップダウン リストから選択した項目の数を決定します。|
|[ボタンを押す](#hasmenu)|オブジェクトにメニューが含まれているかどうかを示します。|

## <a name="remarks"></a>解説

クラス`CMFCRibbonUndoButton`は、スタックを使用してドロップダウン リストを表します。

## <a name="example"></a>例

クラスのオブジェクトを構築し、アクションの`CMFCRibbonUndoButton`リストに新しいアクションを追加する方法を次の例に示します。 このコード スニペットは、[リボン ガジェットのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbonundobutton.h

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a>ボタンを押す:アクションを追加します。

アクションのリストに新しいアクションを追加します。

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ドロップダウン リストに表示されるアクション ラベル。

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a>ボタン::クリーンアップ元に戻すリスト

アクション リスト (ドロップダウン リスト) をクリアします。

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a>ボタンを押す

指定したコマンド`CMFCRibbonUndoButton`ID、テキスト ラベル、および親オブジェクトのイメージ リストのイメージを使用して、新しいオブジェクトを構築します。

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
[in]コマンド ID を指定します。

*lpszText*<br/>
[in]ボタンのテキスト ラベルを指定します。

*を使用します。*<br/>
[in]ボタンの小さいイメージの親オブジェクトのイメージ リスト内の 0 から始まるインデックス。

*インデックスを作成します。*<br/>
[in]ボタンの大きいイメージの親オブジェクトのイメージ リスト内の 0 から始まるインデックス。

*Hicon*<br/>
[in]ボタンのイメージとして使用できるアイコンへのハンドル。

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a>ボタンを押します。

ユーザーがドロップダウン リストから選択した項目の数を決定します。

```
int GetActionNumber() const;
```

### <a name="return-value"></a>戻り値

ユーザーが選択した項目の数。

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a>ボタンを押す

オブジェクトにメニューが含まれているかどうかを示します。

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)

---
title: CMFCRibbonUndoButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 233f37fc0ab31afcd8ba112677af8cd144d01c2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton クラス
`CMFCRibbonUndoButton`クラスは、最新のユーザー コマンドを含むドロップダウン リスト ボタンを実装します。 ユーザーは、1 つ以上の最新のコマンドを元に戻すかやり直すにドロップダウン リストから選択できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|新しい`CMFCRibbonUndoButton`を指定するコマンド ID、テキスト ラベルと親オブジェクトのイメージ リストのイメージを使用してオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|アクションの一覧に新しいアクションを追加します。|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|ドロップダウン リストであるアクションの一覧をクリアします。|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|ユーザーがドロップダウン リストから選択した項目の数を決定します。|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|オブジェクトにメニューが含まれるかどうかを示します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCRibbonUndoButton`クラスでは、スタックを使用して、ドロップダウン リストを表します。  
  
## <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCRibbonUndoButton`クラス、およびアクションの一覧に新しい動作を追加します。 このコード スニペットの一部である、[リボン ガジェット サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>  CMFCRibbonUndoButton::AddUndoAction  
 アクションの一覧に新しいアクションを追加します。  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ドロップダウン リストに表示されるアクション ラベルです。  
  
##  <a name="cleanupundolist"></a>  CMFCRibbonUndoButton::CleanUpUndoList  
 ドロップダウン リストであるアクションの一覧をクリアします。  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>  CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 新しい`CMFCRibbonUndoButton`を指定するコマンド ID、テキスト ラベルと親オブジェクトのイメージ リストのイメージを使用してオブジェクト。  
  
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
 [入力] `nID`  
 コマンド識別子を指定します。  
  
 [入力] `lpszText`  
 ボタンのテキスト ラベルを指定します。  
  
 [入力] `nSmallImageIndex`  
 イメージ リストには、ボタンの小さな画像の親オブジェクトの 0 から始まるインデックス。  
  
 [入力] `nLargeImageIndex`  
 イメージ リストには親オブジェクトの 0 から始まるインデックス、ボタンのイメージの大規模なのです。  
  
 [入力] `hIcon`  
 ボタンのイメージとして使用できるアイコンへのハンドル。  
  
##  <a name="getactionnumber"></a>  CMFCRibbonUndoButton::GetActionNumber  
 ユーザーがドロップダウン リストから選択した項目の数を決定します。  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが選択されている項目の数。  
  
##  <a name="hasmenu"></a>  CMFCRibbonUndoButton::HasMenu  
 オブジェクトにメニューが含まれるかどうかを示します。  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)

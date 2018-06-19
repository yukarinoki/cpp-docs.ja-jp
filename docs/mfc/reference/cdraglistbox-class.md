---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
dev_langs:
- C++
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34655c244f13cb721693208fa93353582de452e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367212"
---
# <a name="cdraglistbox-class"></a>関数クラス
Windows は、リスト ボックスの機能を提供するだけでなく、`CDragListBox`クラスにより、ユーザーをリスト ボックス内で、ファイル名などのリスト ボックス項目を移動します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|`CDragListBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|ドラッグ操作を開始するときに、フレームワークによって呼び出されます。|  
|[CDragListBox::CancelDrag](#canceldrag)|ドラッグ操作が取り消されたときに、フレームワークによって呼び出されます。|  
|[CDragListBox::Dragging](#dragging)|ドラッグ操作中に、フレームワークによって呼び出されます。|  
|[CDragListBox::DrawInsert](#drawinsert)|ドラッグのリスト ボックスの挿入ガイドを描画します。|  
|[CDragListBox::Dropped](#dropped)|項目がドロップされた後に、フレームワークによって呼び出されます。|  
|[CDragListBox::ItemFromPt](#itemfrompt)|ドラッグされている項目の座標を返します。|  
  
## <a name="remarks"></a>コメント  
 この機能を持つリスト ボックスでは、何らかの方法でそれらに最も役に立つの一覧で、アイテムを注文するようにします。 既定では、リスト ボックスは、リスト内の新しい場所にアイテムを移動することにします。 ただし、`CDragListBox`に移動することではなく項目をコピーするオブジェクトをカスタマイズすることができます。  
  
 リスト ボックス コントロールに関連付けられている、`CDragListBox`クラスが必要ない、 **LBS_SORT**または**LBS_MULTIPLESELECT**スタイル。 リスト ボックスのスタイルの説明は、次を参照してください。[リスト ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)です。  
  
 使用するには、アプリケーションの既存のダイアログ ボックスでのドラッグ リスト ボックス ダイアログ エディターを使用して、ダイアログ テンプレートをリスト ボックス コントロールを追加し、メンバー変数を割り当てる (カテゴリの`Control`と変数型`CDragListBox`)、リスト ボックスに対応します。ダイアログ テンプレート内の制御します。  
  
 コントロールをメンバー変数に割り当てる方法に関する詳細については、次を参照してください。[ダイアログ コントロールのメンバー変数を定義するためのショートカット](../../windows/defining-member-variables-for-dialog-controls.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="begindrag"></a>  CDragListBox::BeginDrag  
 によって呼び出される、イベントが発生したときに、フレームワークは、マウスの左ボタンを押すなどのドラッグ操作を開始できません。  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)ドラッグされている項目の座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ドラッグすることが許可された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 ドラッグ操作の開始時の動作を制御する場合は、この関数をオーバーライドします。 既定の実装では、マウスをキャプチャし、ユーザーが左または右マウス ボタンをクリックするか、ドラッグ操作が取り消された時点で、esc キーを押すまでドラッグ モードのままです。  
  
##  <a name="canceldrag"></a>  CDragListBox::CancelDrag  
 ドラッグ操作が取り消されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)ドラッグされている項目の座標を格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 リスト ボックス コントロールの特別な処理するには、この関数をオーバーライドします。  
  
##  <a name="cdraglistbox"></a>  CDragListBox::CDragListBox  
 `CDragListBox` オブジェクトを構築します。  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>  CDragListBox::Dragging  
 リスト ボックス項目内でドラッグされるときに、フレームワークによって呼び出されます、`CDragListBox`オブジェクト。  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) x と y を格納しているオブジェクト、カーソルの画面座標。  
  
### <a name="return-value"></a>戻り値  
 表示されるカーソルのリソース ID。 次の値が考えられます。  
  
- `DL_COPYCURSOR` 項目がコピーされることを示します。  
  
- `DL_MOVECURSOR` 項目が移動することを示します。  
  
- `DL_STOPCURSOR` 現在のドロップ先が許容されるがないことを示します。  
  
### <a name="remarks"></a>コメント  
 既定の動作を返します`DL_MOVECURSOR`です。 追加機能を提供する場合は、この関数をオーバーライドします。  
  
##  <a name="drawinsert"></a>  CDragListBox::DrawInsert  
 指定されたインデックスで項目の前に挿入ガイドを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 カーソル位置の 0 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 値 1 は、挿入ガイドをクリアします。 外観または挿入ガイドの動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="dropped"></a>  CDragListBox::Dropped  
 内の項目が削除されるときに、フレームワークによって呼び出されます、`CDragListBox`オブジェクト。  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSrcIndex*  
 破棄された文字列の 0 から始まるインデックスを指定します。  
  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)ドロップ サイトの座標を格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 既定の動作を新しい場所に、リスト ボックス項目とそのデータをコピーし、元の項目を削除します。 リスト内の他の場所にドラッグできるリスト ボックス項目のコピーを有効にするなど、既定の動作をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="itemfrompt"></a>  CDragListBox::ItemFromPt  
 リスト ボックス項目の 0 から始まるインデックスを取得するには、この関数にある呼び出し`pt`です。  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)リスト ボックス内のポイントの座標を持つオブジェクト。  
  
 *bAutoScroll*  
 スクロールが許可された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="return-value"></a>戻り値  
 ドラッグのリスト ボックス項目の 0 から始まるインデックス。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル TSTCON](../../visual-cpp-samples.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)

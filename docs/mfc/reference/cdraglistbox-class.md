---
title: CDragListBox クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
ms.openlocfilehash: b260d3a88fc8c3f2d341005c1e47cfd9ab668e1e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500352"
---
# <a name="cdraglistbox-class"></a>CDragListBox クラス

クラスを使用すると、Windows のリストボックスの機能を提供するだけでなく、ファイル名などのリスト `CDragListBox` ボックス項目をリストボックス内で移動することもできます。

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
|[CDragListBox:: BeginDrag](#begindrag)|ドラッグ操作の開始時にフレームワークによって呼び出されます。|
|[CDragListBox:: CancelDrag](#canceldrag)|ドラッグ操作が取り消されたときにフレームワークによって呼び出されます。|
|[CDragListBox::D ragging](#dragging)|ドラッグ操作中にフレームワークによって呼び出されます。|
|[CDragListBox::D rawInsert](#drawinsert)|ドラッグリストボックスの挿入ガイドを描画します。|
|[CDragListBox::D ropped](#dropped)|項目が削除された後に、フレームワークによって呼び出されます。|
|[CDragListBox:: ItemFromPt](#itemfrompt)|ドラッグされている項目の座標を返します。|

## <a name="remarks"></a>注釈

この機能を備えたリストボックスを使用すると、ユーザーが最も役に立つ方法でリスト内の項目を並べ替えることができます。 既定では、リストボックスはリスト内の新しい場所に項目を移動します。 ただし、 `CDragListBox` オブジェクトを移動するのではなく、項目をコピーするようにカスタマイズすることもできます。

クラスに関連付けられているリストボックスコントロールに、 `CDragListBox` LBS_SORT または LBS_MULTIPLESELECT スタイルを指定することはできません。 リストボックススタイルの説明については、「 [リストボックススタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)」を参照してください。

アプリケーションの既存のダイアログボックスでドラッグリストボックスを使用するには、ダイアログエディターを使用してダイアログテンプレートにリストボックスコントロールを追加し、 `Control` `CDragListBox` ダイアログテンプレートのリストボックスコントロールに対応するメンバー変数 (Category および variable Type) を割り当てます。

コントロールをメンバー変数に割り当てる方法の詳細については、「 [ダイアログコントロールのメンバー変数を定義するためのショートカット](../../windows/adding-editing-or-deleting-controls.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a> CDragListBox:: BeginDrag

マウスの左ボタンを押すなど、ドラッグ操作を開始できるイベントが発生したときにフレームワークによって呼び出されます。

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
ドラッグされている項目の座標を格納している [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

ドラッグが許可されている場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>注釈

ドラッグ操作が開始されたときの動作を制御する場合は、この関数をオーバーライドします。 既定の実装はマウスをキャプチャし、ユーザーがマウスの左ボタンまたは右ボタンをクリックするか ESC キーを押すと、ドラッグ操作はキャンセルされます。

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a> CDragListBox:: CancelDrag

ドラッグ操作が取り消されたときにフレームワークによって呼び出されます。

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
ドラッグされている項目の座標を格納している [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) オブジェクト。

### <a name="remarks"></a>注釈

リストボックスコントロールの特別な処理を処理するには、この関数をオーバーライドします。

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a> CDragListBox::CDragListBox

`CDragListBox` オブジェクトを構築します。

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a> CDragListBox::D ragging

リストボックス項目がオブジェクト内でドラッグされているときに、フレームワークによって呼び出され `CDragListBox` ます。

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
カーソルの x および y 画面座標を格納している [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

表示されるカーソルのリソース ID。 可能な値は次のとおりです。

- DL_COPYCURSOR 項目がコピーされることを示します。

- DL_MOVECURSOR は、項目が移動されることを示します。

- DL_STOPCURSOR は、現在のドロップ先が許容されないことを示します。

### <a name="remarks"></a>注釈

既定の動作では DL_MOVECURSOR が返されます。 追加の機能を提供する場合は、この関数をオーバーライドします。

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a> CDragListBox::D rawInsert

指定されたインデックスを持つ項目の前に挿入ガイドを描画するために、フレームワークによって呼び出されます。

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
挿入ポイントの0から始まるインデックス。

### <a name="remarks"></a>注釈

値を-1 にすると、挿入ガイドがクリアされます。 挿入ガイドの外観または動作を変更するには、この関数をオーバーライドします。

## <a name="cdraglistboxdropped"></a><a name="dropped"></a> CDragListBox::D ropped

オブジェクト内の項目がドロップされたときに、フレームワークによって呼び出され `CDragListBox` ます。

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>パラメーター

*nSrcIndex*<br/>
削除された文字列の0から始まるインデックスを指定します。

*pt*<br/>
ドロップサイトの座標を格納している [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) オブジェクト。

### <a name="remarks"></a>注釈

既定の動作では、リストボックスの項目とそのデータが新しい場所にコピーされ、元の項目が削除されます。 リストボックス項目のコピーをリスト内の他の場所にドラッグできるようにするなど、既定の動作をカスタマイズするには、この関数をオーバーライドします。

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a> CDragListBox:: ItemFromPt

この関数を呼び出して、 *pt*にあるリストボックス項目の0から始まるインデックスを取得します。

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
リストボックス内の点の座標を格納している [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) オブジェクト。

*bAutoScroll スクロール*<br/>
スクロールが許可されている場合は0以外。それ以外の場合は0。

### <a name="return-value"></a>戻り値

ドラッグリストボックス項目の0から始まるインデックス。

## <a name="see-also"></a>関連項目

[MFC のサンプル TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)

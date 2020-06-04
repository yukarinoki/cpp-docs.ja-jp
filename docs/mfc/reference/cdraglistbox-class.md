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
ms.openlocfilehash: 0d1ae94948e1143a5bac17985423c4bd1bfbaf65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374028"
---
# <a name="cdraglistbox-class"></a>CDragListBox クラス

この`CDragListBox`クラスでは、Windows リスト ボックスの機能を提供するだけでなく、ユーザーがリスト ボックス内でファイル名などのリスト ボックス項目を移動できます。

## <a name="syntax"></a>構文

```
class CDragListBox : public CListBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cドラグリストボックス::Cドラリストボックス](#cdraglistbox)|`CDragListBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDragリストボックス::開始ドラッグ](#begindrag)|ドラッグ操作の開始時にフレームワークによって呼び出されます。|
|[Cドラグリストボックス::キャンセルドラッグ](#canceldrag)|ドラッグ操作がキャンセルされたときに、フレームワークによって呼び出されます。|
|[CDragリストボックス::Dラギング](#dragging)|ドラッグ操作中にフレームワークによって呼び出されます。|
|[:Dロー挿入ボックス](#drawinsert)|ドラッグ リスト ボックスの挿入ガイドを描画します。|
|[CDragリストボックス::Dロップ](#dropped)|項目が削除された後にフレームワークによって呼び出されます。|
|[次の項目を使用します。](#itemfrompt)|ドラッグされている項目の座標を返します。|

## <a name="remarks"></a>解説

この機能を備えたリスト ボックスを使用すると、ユーザーは最も便利な方法でリスト内のアイテムを並べ替えられます。 既定では、リスト ボックスは、リスト内の新しい場所に項目を移動します。 ただし、`CDragListBox`オブジェクトをカスタマイズして、アイテムを移動する代わりにコピーできます。

`CDragListBox`クラスに関連付けられているリスト ボックス コントロールに、LBS_SORTまたはLBS_MULTIPLESELECTスタイルを含む必要があります。 リスト ボックススタイルの詳細については、「[リスト ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)」を参照してください。

アプリケーションの既存のダイアログ ボックスでドラッグ リスト ボックスを使用するには、ダイアログ エディターを使用してダイアログ テンプレートにリスト ボックス コントロールを追加し、ダイアログ`Control`テンプレートの`CDragListBox`リスト ボックス コントロールに対応するメンバー変数 ([カテゴリ] および [変数の種類]) を割り当てます。

メンバ変数へのコントロールの割り当ての詳細については、「[ダイアログ コントロールのメンバ変数を定義するためのショートカット](../../windows/defining-member-variables-for-dialog-controls.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a>CDragリストボックス::開始ドラッグ

マウスの左ボタンを押すなどのドラッグ操作を開始する可能性のあるイベントが発生したときに、フレームワークによって呼び出されます。

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
ドラッグされる項目の座標を格納する[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

ドラッグが許可されている場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

ドラッグ操作の開始時に何が起こるかを制御する場合は、この関数をオーバーライドします。 既定の実装では、マウスをキャプチャし、ユーザーがマウスの左または右ボタンをクリックするか、または Esc キーを押すまでドラッグ モードで、ドラッグ操作がキャンセルされるまでは、そのままです。

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a>Cドラグリストボックス::キャンセルドラッグ

ドラッグ操作がキャンセルされたときに、フレームワークによって呼び出されます。

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
ドラッグされる項目の座標を格納する[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

### <a name="remarks"></a>解説

リスト ボックス コントロールの特別な処理を処理するには、この関数をオーバーライドします。

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a>Cドラグリストボックス::Cドラリストボックス

`CDragListBox` オブジェクトを構築します。

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a>CDragリストボックス::Dラギング

リスト ボックス項目がオブジェクト内でドラッグされているときに、フレームワークによって`CDragListBox`呼び出されます。

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
カーソルの x および y 画面座標を含む[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

表示されるカーソルのリソース ID。 可能な値は次のとおりです。

- DL_COPYCURSOR アイテムがコピーされることを示します。

- DL_MOVECURSOR アイテムが移動されることを示します。

- DL_STOPCURSOR現在のドロップ ターゲットが許容されないことを示します。

### <a name="remarks"></a>解説

既定の動作はDL_MOVECURSORを返します。 追加機能を提供する場合は、この関数をオーバーライドします。

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a>:Dロー挿入ボックス

指定されたインデックスを持つ項目の前に挿入ガイドを描画するために、フレームワークによって呼び出されます。

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
挿入ポイントの 0 から始まるインデックス。

### <a name="remarks"></a>解説

値が - 1 の場合、挿入ガイドがクリアされます。 挿入ガイドの外観または動作を変更するには、この関数をオーバーライドします。

## <a name="cdraglistboxdropped"></a><a name="dropped"></a>CDragリストボックス::Dロップ

`CDragListBox`オブジェクト内で項目がドロップされたときに、フレームワークによって呼び出されます。

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
ドロップされた文字列の 0 から始まるインデックスを指定します。

*Pt*<br/>
ドロップ サイトの座標を格納する[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

### <a name="remarks"></a>解説

既定の動作では、リスト ボックスの項目とそのデータが新しい場所にコピーされ、元のアイテムが削除されます。 リスト ボックスの項目のコピーをリスト内の他の場所にドラッグできるようにするなどの既定の動作をカスタマイズするには、この関数をオーバーライドします。

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a>次の項目を使用します。

*pt*にあるリスト ボックス項目の 0 から始まるインデックスを取得します。

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
リスト ボックス内のポイントの座標を含む[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

*b自動スクロール*<br/>
スクロールが許可されている場合は 0 以外の値を返します。

### <a name="return-value"></a>戻り値

ドラッグ リスト ボックス項目の 0 から始まるインデックス。

## <a name="see-also"></a>関連項目

[MFC サンプル TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)

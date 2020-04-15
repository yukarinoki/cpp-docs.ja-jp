---
title: クラスを分割します。
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: d7952e3082bf68cff7ad9ba218073081ee522320
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363918"
---
# <a name="csplitterwndex-class"></a>クラスを分割します。

カスタマイズされた分割ウィンドウを表します。

## <a name="syntax"></a>構文

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|既定のコンストラクターです。|
|`CSplitterWndEx::~CSplitterWndEx`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[スプリッタスプリットンデックス::オンドロースプリッター](#ondrawsplitter)|分割ウィンドウを描画するためにフレームワークによって呼び出されます。 (オーバーライド[CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>解説

このメソッド`OnDrawSplitter`をオーバーライドして、分割ウィンドウのグラフィカル コンポーネントの外観をカスタマイズします。

クラス`CSplitterWndEx`は、ビジュアル マネージャーによって実装される[OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder) [、OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)、および[OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground)メソッドと共に使用されます。 ビジュアル マネージャーがアプリケーションで分割ウィンドウを描画するようにするには、クラスの宣言を`CSplitterWnd``CSplitterWndEx`クラスに置き換えます。 フレーム ウィンドウ アプリケーションの場合、分割ウィンドウ クラスは mainfrm.h にある CMainFrame クラスで宣言されます。 例については、Samples ディレクトリ`OutlookDemo`のサンプルを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsplitterwndex.h

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a>スプリッタスプリットンデックス::オンドロースプリッター

分割ウィンドウを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。 このパラメーターが NULL の場合、フレームワークはアクティブ ウィンドウを再描画します。

*nType*<br/>
[in]描画する`CSplitterWnd::ESplitType`分割ウィンドウ要素を指定する列挙値の 1 つ。 有効な値は `splitBox`、`splitBar`、`splitIntersection`、および `splitBorder` です。

*Rect*<br/>
[in]指定した分割ウィンドウ要素を描画するサイズと位置を指定する外接する四角形。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../hierarchy-chart.md)<br/>
[クラス](mfc-classes.md)<br/>
[クラスを分割する](csplitterwnd-class.md)<br/>
[クラス](cmfcvisualmanager-class.md)

---
description: '詳細情報: CSplitterWndEx クラス'
title: CSplitterWndEx クラス
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: 357f650551871cc9768c8e4e693bd62bb5e69bc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345096"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx クラス

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
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|スプリッターウィンドウを描画するためにフレームワークによって呼び出されます。 ( [CSplitterWnd:: OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter)をオーバーライドします。)|

## <a name="remarks"></a>解説

`OnDrawSplitter`分割ウィンドウのグラフィカルコンポーネントの外観をカスタマイズするには、メソッドをオーバーライドします。

クラスは、 `CSplitterWndEx` ビジュアルマネージャーによって実装される、 [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder)、 [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)、および [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) の各メソッドと共に使用されます。 ビジュアルマネージャーによってアプリケーションにスプリッターウィンドウが描画されるようにするには、クラスの宣言を `CSplitterWnd` クラスに置き換え `CSplitterWndEx` ます。 フレームウィンドウアプリケーションでは、mainfrm.cpp にある CMainFrame クラスで、スプリッターウィンドウクラスが宣言されます。 例については、サンプルディレクトリのサンプルを参照してください `OutlookDemo` 。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxsplitterwndex

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a> CSplitterWndEx::OnDrawSplitter

スプリッターウィンドウを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。 このパラメーターが NULL の場合、フレームワークはアクティブウィンドウを再描画します。

*nType*<br/>
から `CSplitterWnd::ESplitType` 描画する分割ウィンドウ要素を指定する列挙値の1つ。 有効な値は、`splitBox`、`splitBar`、`splitIntersection`、`splitBorder` です。

*rect*<br/>
から指定された分割ウィンドウ要素を描画するための寸法と位置を指定する外接する四角形。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../hierarchy-chart.md)<br/>
[Classes](mfc-classes.md)<br/>
[CSplitterWnd クラス](csplitterwnd-class.md)<br/>
[CMFCVisualManager クラス](cmfcvisualmanager-class.md)

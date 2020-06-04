---
title: COleIPFrameWnd クラス
ms.date: 11/04/2016
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
ms.openlocfilehash: 01e259cf01c42add26088b0cbd2f6dab311eb9b1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374957"
---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd クラス

アプリケーションの埋め込み先編集ウィンドウの基底クラスです。

## <a name="syntax"></a>構文

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を切り取る::コレップフレーム](#coleipframewnd)|`COleIPFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロールバーを作成します。](#oncreatecontrolbars)|アイテムがインプレース編集用にアクティブ化されたときに、フレームワークによって呼び出されます。|
|[コレクリップフレームオード::再配置フレーム](#repositionframe)|インプレース編集ウィンドウの位置を変更するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

このクラスは、コンテナー アプリケーションのドキュメント ウィンドウ内にコントロール バーを作成し、配置します。 また、埋め込み[COleResizeBar](../../mfc/reference/coleresizebar-class.md)オブジェクトによって生成される通知は、ユーザーが埋め込み場所の編集ウィンドウのサイズを変更したときにも処理されます。

の使用方法`COleIPFrameWnd`の詳細については、[記事「アクティベーション](../../mfc/activation-cpp.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a>を切り取る::コレップフレーム

オブジェクトを`COleIPFrameWnd`構築し、OLEINPLACEFRAMEINFO 型の構造体に格納されているインプレース状態情報を初期化します。

```
COleIPFrameWnd();
```

### <a name="remarks"></a>解説

詳細については、Windows SDK[の「OLEINPLACEFRAMEINFO」](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo)を参照してください。

## <a name="coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a>コントロールバーを作成します。

アイテムがインプレー`OnCreateControlBars`ス編集用にアクティブ化されると、フレームワークは関数を呼び出します。

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
コンテナー アプリケーションのフレーム ウィンドウへのポインター。

*ドク*<br/>
コンテナーのドキュメント レベルのウィンドウへのポインター。 コンテナが SDI アプリケーションの場合は NULL になります。

### <a name="return-value"></a>戻り値

成功時にゼロ以外の値。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。 コントロール バーの作成時に必要な特別な処理を実行するには、この関数をオーバーライドします。

## <a name="coleipframewndrepositionframe"></a><a name="repositionframe"></a>コレクリップフレームオード::再配置フレーム

フレームワークは、メンバー`RepositionFrame`関数を呼び出してコントロール バーをレイアウトし、インプレース編集ウィンドウの位置を変更して、そのすべてが表示されるようにします。

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
インプレイス`RECT`フレーム ウィンドウ`CRect`の現在位置座標を格納している構造体またはオブジェクトへのポインターです(ピクセル単位)。

*lp クリップレック*<br/>
インプレース`RECT`フレーム`CRect`ウィンドウの現在のクリッピング四角形座標を含む構造体またはオブジェクトへのポインターです(ピクセル単位)。

### <a name="remarks"></a>解説

コンテナー ウィンドウのコントロール バーのレイアウトは、OLE 以外のフレーム ウィンドウで実行されるコントロール バーとは異なります。 非 OLE フレーム ウィンドウは[、CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout)の呼び出しのように、指定されたフレーム ウィンドウ サイズからコントロール バーやその他のオブジェクトの位置を計算します。 クライアント領域は、コントロール バーなどのオブジェクトの領域を減算した後に残ります。 一`COleIPFrameWnd`方、ウィンドウは、特定のクライアント領域に応じてツールバーを配置します。 言い換えれば`CFrameWnd::RecalcLayout`、「外から」、作品は`COleIPFrameWnd::RepositionFrame`「内側から」動作します。

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)

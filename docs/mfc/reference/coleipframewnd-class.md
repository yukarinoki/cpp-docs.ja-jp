---
title: COleIPFrameWnd クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: debe4c271d2a6e6a82cde9acc75eaa28404ebb43
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443879"
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
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|`COleIPFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|一括編集するため、項目がアクティブになったときに、フレームワークによって呼び出されます。|
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|一括編集ウィンドウの位置を変更するためにフレームワークによって呼び出されます。|

## <a name="remarks"></a>Remarks

このクラスを作成し、コントロール コンテナー アプリケーションのドキュメント ウィンドウ内でバーの位置。 また、埋め込みで生成された通知を処理[COleResizeBar](../../mfc/reference/coleresizebar-class.md)オブジェクトのユーザーのインプレース編集ウィンドウのサイズ変更時にします。

使用しての詳細については`COleIPFrameWnd`、記事をご覧ください[アクティベーション](../../mfc/activation-cpp.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>要件

**ヘッダー:** afxole.h

##  <a name="coleipframewnd"></a>  COleIPFrameWnd::COleIPFrameWnd

構築、`COleIPFrameWnd`オブジェクトし、そのインプレース状態については、受け取る型の構造に格納されているを初期化します。

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。[受け取る](/windows/desktop/api/oleidl/ns-oleidl-tagoifi)Windows SDK に含まれています。

##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars

フレームワークによって、`OnCreateControlBars`で埋め込み先編集の項目がアクティブ化時に機能します。

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);


virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>パラメーター

*pWndFrame*<br/>
コンテナー アプリケーションのフレーム ウィンドウへのポインター。

*pWndDoc*<br/>
コンテナーのドキュメント レベルのウィンドウへのポインター。 コンテナーが SDI アプリケーションの場合、NULL を指定できます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合、0 を返します。

### <a name="remarks"></a>Remarks

既定の実装では、何も行われません。 コントロール バーが作成されたときに必要な特別な処理を実行するには、この関数をオーバーライドします。

##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame

フレームワークによって、`RepositionFrame`メンバー関数をコントロール バーをレイアウトし、すべてが表示されているため、インプレース編集ウィンドウの位置を指定します。

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
ポインターを`RECT`構造または`CRect`オブジェクトの場所を含むフレーム ウィンドウの現在位置座標をピクセル単位のクライアント領域を基準とします。

*lpClipRect*<br/>
ポインターを`RECT`構造または`CRect`オブジェクトの場所を含むフレーム ウィンドウの現在クリッピング四角形座標をピクセル単位のクライアント領域を基準とします。

### <a name="remarks"></a>Remarks

コンテナー ウィンドウで、コントロール バーのレイアウトとは異なります非 OLE フレーム ウィンドウで実行します。 非 OLE フレーム ウィンドウのコントロール バー、およびその他のオブジェクトへの呼び出しのように、特定のフレーム ウィンドウのサイズを位置を計算する[表示](../../mfc/reference/cframewnd-class.md#recalclayout)します。 クライアント領域は、残りのコントロール バー、およびその他のオブジェクト用の領域が減算されます。 A`COleIPFrameWnd`ウィンドウはその一方で、に従って、特定のクライアント領域ツールバーを配置します。 つまり、`CFrameWnd::RecalcLayout`一方で、外部"から"動作`COleIPFrameWnd::RepositionFrame`"から、徹底解剖"。

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)

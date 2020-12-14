---
description: '詳細情報: COleIPFrameWnd クラス'
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
ms.openlocfilehash: d89cfa9b3f6d610276c3c972ee48c943f753e36a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227014"
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
|[COleIPFrameWnd:: COleIPFrameWnd](#coleipframewnd)|`COleIPFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleIPFrameWnd:: OnCreateControlBars](#oncreatecontrolbars)|項目が埋め込み先編集のためにアクティブになったときに、フレームワークによって呼び出されます。|
|[COleIPFrameWnd:: RepositionFrame](#repositionframe)|埋め込み先編集ウィンドウの位置を変更するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

このクラスは、コントロールバーを作成し、コンテナーアプリケーションのドキュメントウィンドウ内に配置します。 また、埋め込み先編集ウィンドウのサイズをユーザーが変更したときに、埋め込み [Coleresizebar](../../mfc/reference/coleresizebar-class.md) オブジェクトによって生成される通知も処理します。

の使用方法の詳細については `COleIPFrameWnd` 、「 [アクティブ化](../../mfc/activation-cpp.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>要件

**ヘッダー:** afxole

## <a name="coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a> COleIPFrameWnd:: COleIPFrameWnd

オブジェクトを構築 `COleIPFrameWnd` し、そのインプレース状態情報を初期化します。この情報は、OLEINPLACE フレーム情報型の構造体に格納されます。

```
COleIPFrameWnd();
```

### <a name="remarks"></a>解説

詳細については、Windows SDK の「 [Oleinplace フレーム情報](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo) 」を参照してください。

## <a name="coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a> COleIPFrameWnd:: OnCreateControlBars

フレームワークは、 `OnCreateControlBars` 項目が埋め込み先編集のためにアクティブになったときに、関数を呼び出します。

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
コンテナーアプリケーションのフレームウィンドウへのポインター。

*pWndDoc*<br/>
コンテナーのドキュメントレベルウィンドウへのポインター。 コンテナーが SDI アプリケーションの場合は NULL を指定できます。

### <a name="return-value"></a>戻り値

成功した場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。 コントロールバーが作成されるときに必要な特別な処理を実行するには、この関数をオーバーライドします。

## <a name="coleipframewndrepositionframe"></a><a name="repositionframe"></a> COleIPFrameWnd:: RepositionFrame

フレームワークは、メンバー関数を呼び出して、 `RepositionFrame` コントロールバーをレイアウトし、埋め込み先編集ウィンドウの位置を変更して、すべてが表示されるようにします。

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
`RECT` `CRect` クライアント領域を基準とした、埋め込み先フレームウィンドウの現在の位置座標をピクセル単位で格納している構造体またはオブジェクトへのポインター。

*lpClipRect*<br/>
`RECT` `CRect` クライアント領域を基準とした、埋め込み先フレームウィンドウの現在のクリッピング四角形の座標 (ピクセル単位) を格納している構造体またはオブジェクトへのポインター。

### <a name="remarks"></a>解説

コンテナーウィンドウ内のコントロールバーのレイアウトは、非 OLE フレームウィンドウで実行されるものとは異なります。 非 OLE フレームウィンドウは、 [CFrameWnd:: RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout)の呼び出しのように、指定されたフレームウィンドウサイズからコントロールバーとその他のオブジェクトの位置を計算します。 クライアント領域は、コントロールバーとその他のオブジェクトの領域が減算された後に残っています。 一方、ウィンドウは、 `COleIPFrameWnd` 特定のクライアント領域に応じてツールバーを配置します。 つまり、は "外側の" から "処理中" に `CFrameWnd::RecalcLayout` `COleIPFrameWnd::RepositionFrame` なります。

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)

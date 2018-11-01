---
title: ATL_DRAWINFO 構造体
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: 3e332213ad8b2697445b13aded6bef605dab32de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442628"
---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO 構造体

プリンター、メタファイル、または ActiveX コントロールなどのさまざまなターゲットへのレンダリングに使用される情報が含まれています。

## <a name="syntax"></a>構文

```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```

## <a name="members"></a>メンバー

`cbSize`<br/>
(バイト単位)、構造体のサイズ。

`dwDrawAspect`<br/>
ターゲットが表示される方法を指定します。 表現には、コンテンツ、アイコン、縮小表示または印刷したドキュメントを含めることができます。 使用可能な値の一覧は、次を参照してください。[型](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect)と[DVASPECT2](/windows/desktop/api/ocidl/ne-ocidl-tagdvaspect2)します。

`lindex`<br/>
描画操作の対象となるターゲットの部分です。 その解釈は、値によって、`dwDrawAspect`メンバー。

`ptd`<br/>
ポインターを[DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice)指定されたアスペクトに応じて描画の最適化を有効する構造体。 新しいオブジェクトおよび最適化された描画インターフェイスをサポートするコンテナーがもこのメンバーをサポートすることに注意してください。 古いオブジェクトおよびコンテナーを常に最適化された描画インターフェイスをサポートしない、このメンバーの場合は NULL を指定します。

`hicTargetDev`<br/>
によって示される、ターゲット デバイスの情報コンテキスト`ptd`から、オブジェクトはデバイス メトリックを抽出し、デバイスの機能をテストします。 場合`ptd`が null の場合、オブジェクトの値は無視する必要があります、`hicTargetDev`メンバー。

`hdcDraw`<br/>
描画するためにデバイス コンテキスト。 ウィンドウなしのオブジェクト、`hdcDraw`メンバーが、`MM_TEXT`マッピング モードの論理座標が格納先ウィンドウのクライアント座標に一致するとします。 さらに、デバイス コンテキストが、通常 1 つと同じ状態にあります。、`WM_PAINT`メッセージ。

`prcBounds`<br/>
ポインターを[RECTL](https://msdn.microsoft.com/library/windows/desktop/dd162907)の四角形を指定する構造体`hdcDraw`オブジェクトを描画する必要があります。 このメンバーは、移動とオブジェクトの拡大を制御します。 このメンバーは、ウィンドウなしのインプレース アクティブなオブジェクトを描画するために NULL にする必要があります。 他のすべての状況で NULL が有効な値と発生する必要があります、`E_INVALIDARG`エラー コード。 ウィンドウなしのオブジェクトに、コンテナーが NULL 以外の値を渡すと、オブジェクトは、指定したデバイス コンテキストと四角形に要求された外観をレンダリングする必要があります。 コンテナーは、オブジェクトの 2 つ目の非アクティブなビューを表示するために、またはオブジェクトを印刷するウィンドウなしのオブジェクトからこれを要求できます。

`prcWBounds`<br/>
場合`hdcDraw`メタファイル デバイス コンテキストは、(を参照してください[調べるため](/windows/desktop/api/wingdi/nf-wingdi-getdevicecaps)Windows sdk) へのポインターは、これを`RECTL`基になるメタファイルに外接する四角形を指定する構造体。 四角形の構造には、ウィンドウのエクステントとウィンドウの原点が含まれています。 これらの値は、メタファイルに描画するために便利です。 によって示される四角形`prcBounds`内に入れ子になって`prcWBounds`を表す四角形が同じ座標領域。

`bOptimize`<br/>
コントロールの描画の最適化、それ以外の場合 0 場合 0 以外の値。 描画を最適化すると、デバイス コンテキストの状態は自動的に回復が完了したら表示します。

`bZoomed`<br/>
以外の場合、ターゲットは 0 それ以外の場合、ズームの倍率。 ズームの倍率に格納されている`ZoomNum`します。

`bRectInHimetric`<br/>
0 以外の値の大きさ`prcBounds`HIMETRIC、それ以外の場合 0 にします。

`ZoomNum`<br/>
幅と、オブジェクトを表示する先の四角形の高さ。 ターゲットの x 軸 (オブジェクトの現在の大きさの自然なサイズの比率) に倍率の値である`ZoomNum.cx`の値で除算`ZoomDen.cx`します。 Y 軸に沿った倍率は、同様の方法で実現されます。

`ZoomDen`<br/>
実際の幅とターゲットの高さ。

## <a name="remarks"></a>Remarks

この構造体の一般的な使用方法は、ターゲット オブジェクトのレンダリング中に情報の取得になります。 内のオーバー ロードなど ATL_DRAWINFO から値を取得する可能性があります[CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)します。

この構造体は、対象デバイスのオブジェクトの外観を表示するために使用される適切な情報を格納します。 提供される情報は、画面、プリンター、またはメタファイルに描画で使用できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)<br/>
[IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)

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
ms.openlocfilehash: 00d93b3dd8b060a21b6ff4083bb9880d8d836a19
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168619"
---
# <a name="atl_drawinfo-structure"></a>ATL_DRAWINFO 構造体

プリンター、メタファイル、ActiveX コントロールなどのさまざまなターゲットにレンダリングするために使用される情報を格納します。

## <a name="syntax"></a>構文

```cpp
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
構造体のサイズ (バイト単位)。

`dwDrawAspect`<br/>
ターゲットを表す方法を指定します。 表現には、コンテンツ、アイコン、サムネイル、または印刷ドキュメントを含めることができます。 使用可能な値の一覧については、「 [Dvaspect](/windows/win32/api/wtypes/ne-wtypes-dvaspect)と[DVASPECT2](/windows/win32/api/ocidl/ne-ocidl-dvaspect2)」を参照してください。

`lindex`<br/>
描画操作の対象となるターゲットの部分。 その解釈は、 `dwDrawAspect`メンバーの値によって異なります。

`ptd`<br/>
指定されたアスペクトに応じて描画の最適化を有効にする[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice)構造体へのポインター。 最適化された描画インターフェイスをサポートする新しいオブジェクトとコンテナーもこのメンバーをサポートしていることに注意してください。 最適化された描画インターフェイスをサポートしない古いオブジェクトおよびコンテナーは、このメンバーに対して常に NULL を指定します。

`hicTargetDev`<br/>
オブジェクトでデバイスメトリックを抽出し、デバイス`ptd`の機能をテストするためにが指すターゲットデバイスの情報コンテキスト。 が`ptd` NULL の場合、オブジェクトは`hicTargetDev`メンバーの値を無視する必要があります。

`hdcDraw`<br/>
描画するデバイスコンテキスト。 ウィンドウなしのオブジェクトの場合`hdcDraw` 、メンバーは、 `MM_TEXT`親ウィンドウのクライアント座標と一致する論理座標を持つマッピングモードになります。 また、デバイスコンテキストは、通常、 `WM_PAINT`メッセージによって渡されるものと同じ状態にする必要があります。

`prcBounds`<br/>
オブジェクトを描画[RECTL](/windows/win32/api/windef/ns-windef-rectl)する必要がある`hdcDraw`との四角形を指定する RECTL 構造体へのポインター。 このメンバーは、オブジェクトの配置と伸縮を制御します。 ウィンドウなしの組み込みのアクティブなオブジェクトを描画するには、このメンバーは NULL である必要があります。 他のすべての状況では、NULL は有効な値ではなく`E_INVALIDARG` 、エラーコードになります。 コンテナーが非ウィンドウオブジェクトに NULL 以外の値を渡した場合、オブジェクトは、要求されたアスペクトを指定されたデバイスコンテキストおよび四角形にレンダリングする必要があります。 コンテナーはこれをウィンドウなしのオブジェクトに要求して、オブジェクトの2番目の非アクティブなビューをレンダリングしたり、オブジェクトを印刷したりできます。

`prcWBounds`<br/>
が`hdcDraw`メタファイルデバイスコンテキスト (Windows SDK の「 [GetDeviceCaps](/windows/win32/api/wingdi/nf-wingdi-getdevicecaps) 」を参照) である場合、これは`RECTL` 、基になるメタファイル内の外接する四角形を指定する構造体へのポインターです。 四角形の構造体には、ウィンドウエクステントとウィンドウの原点が含まれます。 これらの値は、メタファイルの描画に役立ちます。 によって示さ`prcBounds`れる四角形は、 `prcWBounds`この四角形の内側に入れ子になっています。これらは同じ座標空間にあります。

`bOptimize`<br/>
コントロールの描画を最適化する場合は0以外。それ以外の場合は0。 描画が最適化されている場合、レンダリングが完了すると、デバイスコンテキストの状態が自動的に復元されます。

`bZoomed`<br/>
ターゲットにズームファクターがある場合は0以外の場合は0。それ以外の場合は0。 ズームファクターはに`ZoomNum`格納されます。

`bRectInHimetric`<br/>
の次元が HIMETRIC 内`prcBounds`にある場合は0以外。それ以外の場合は0。

`ZoomNum`<br/>
オブジェクトが描画される四角形の幅と高さ。 ターゲットの x 軸 (オブジェクトの自然サイズの割合) に沿ったズーム係数は、の値で`ZoomNum.cx`割った値になり`ZoomDen.cx`ます。 Y 軸に沿ったズームファクターは、同様の方法で実現されます。

`ZoomDen`<br/>
ターゲットの実際の幅と高さ。

## <a name="remarks"></a>解説

この構造体の一般的な使用方法は、対象オブジェクトのレンダリング中に情報を取得することです。 たとえば、 [CComControlBase:: OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)のオーバーロード内の ATL_DRAWINFO から値を取得できます。

この構造体には、ターゲットデバイスのオブジェクトの外観を表示するために使用される関連情報が格納されます。 指定された情報は、画面、プリンター、またはメタファイルに描画するときに使用できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)<br/>
[IViewObject::D raw](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)

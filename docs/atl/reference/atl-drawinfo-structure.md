---
title: ATL_DRAWINFO構造
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: fb50f49d387e8620f3d5bbb41263738adbd8b437
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748806"
---
# <a name="atl_drawinfo-structure"></a>ATL_DRAWINFO構造

プリンタ、メタファイル、ActiveX コントロールなど、さまざまなターゲットへのレンダリングに使用する情報を格納します。

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
構造体のサイズ (バイト単位)。

`dwDrawAspect`<br/>
ターゲットの表現方法を指定します。 リプレゼンテーションには、コンテンツ、アイコン、サムネイル、印刷ドキュメントなどがあります。 使用可能な値のリストについては[、DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)および[DVASPECT2](/windows/win32/api/ocidl/ne-ocidl-dvaspect2)を参照してください。

`lindex`<br/>
描画操作の対象となるターゲットの一部。 その解釈は`dwDrawAspect`、メンバーの値によって異なります。

`ptd`<br/>
指定されたアスペクトに応じて描画の最適化を可能にする[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice)構造体へのポインター。 最適化された描画インターフェイスをサポートする新しいオブジェクトとコンテナーもこのメンバーをサポートしています。 最適化された描画インターフェイスをサポートしない古いオブジェクトとコンテナーでは、常にこのメンバーに NULL が指定されます。

`hicTargetDev`<br/>
オブジェクトがデバイス メトリックを抽出し、`ptd`デバイスの機能をテストできるターゲット デバイスの情報コンテキスト。 NULL`ptd`の場合、オブジェクトはメンバー内の値を`hicTargetDev`無視する必要があります。

`hdcDraw`<br/>
描画するデバイス コンテキスト。 ウィンドウなしのオブジェクトの`hdcDraw`場合、メンバーは`MM_TEXT`、その論理座標が、含むウィンドウのクライアント座標と一致するマッピング モードです。 さらに、デバイス コンテキストは、通常はメッセージによって渡されるコンテキストと同じ状態にする`WM_PAINT`必要があります。

`prcBounds`<br/>
オブジェクトを描画する必要がある四角形`hdcDraw`を指定する[RECTL](/windows/win32/api/windef/ns-windef-rectl)構造体へのポインター。 このメンバーは、オブジェクトの位置と伸縮を制御します。 ウィンドウなしのインプレイス アクティブ オブジェクトを描画するには、このメンバを NULL にする必要があります。 それ以外の場合、NULL は有効な値ではないので、エラー`E_INVALIDARG`コードが発生する必要があります。 コンテナーがウィンドウなしのオブジェクトに NULL 以外の値を渡す場合、オブジェクトは、要求されたアスペクトを指定されたデバイス コンテキストと四角形にレンダリングする必要があります。 コンテナは、ウィンドウなしのオブジェクトからこれを要求して、オブジェクトの 2 つ目の非アクティブビューをレンダリングしたり、オブジェクトを印刷したりできます。

`prcWBounds`<br/>
メタ`hdcDraw`ファイル デバイス コンテキスト (Windows SDK の[GetDeviceCaps](/windows/win32/api/wingdi/nf-wingdi-getdevicecaps)を参照) の`RECTL`場合、これは、基になるメタファイル内の外接する四角形を指定する構造体へのポインターです。 四角形の構造体には、ウィンドウ範囲とウィンドウの原点が含まれています。 これらの値は、メタファイルを描画する場合に便利です。 で示される`prcBounds`四角形は、この`prcWBounds`四角形の中に入れ子になります。これらは同じ座標空間にあります。

`bOptimize`<br/>
コントロールの描画を最適化する場合は 0 以外の値を返します。 描画が最適化されている場合、レンダリングが終了すると、デバイス コンテキストの状態が自動的に復元されます。

`bZoomed`<br/>
ターゲットにズーム率がある場合は 0 以外、それ以外の場合は 0 以外の値を返します。 ズーム倍率は に`ZoomNum`格納されます。

`bRectInHimetric`<br/>
の次元が HIMETRIC`prcBounds`の場合は 0 以外、それ以外の場合は 0 を返します。

`ZoomNum`<br/>
オブジェクトの描画先となる四角形の幅と高さ。 ターゲットの x 軸に沿ったズーム率 (オブジェクトの自然サイズの現在の範囲に対する比率) は、値`ZoomNum.cx`を の値で`ZoomDen.cx`割った値です。 y 軸に沿ったズーム倍率は、同様の方法で達成されます。

`ZoomDen`<br/>
ターゲットの実際の幅と高さ。

## <a name="remarks"></a>解説

この構造体の一般的な使用方法は、ターゲット オブジェクトのレンダリング中に情報を取得することです。 たとえば[、CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)のオーバーロード内ATL_DRAWINFOから値を取得できます。

この構造体には、ターゲット デバイスのオブジェクトの外観をレンダリングするために使用される関連情報が格納されます。 提供される情報は、画面、プリンタ、またはメタファイルへの描画に使用できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)<br/>
[IView オブジェクト::Dロー](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[ココムコントロールベース::オンドローアドバンスド](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)

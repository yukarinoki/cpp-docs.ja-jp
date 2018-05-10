---
title: ATL_DRAWINFO 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
dev_langs:
- C++
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e04f5efae261a151489309e876298b56ec696db
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO 構造体
プリンター、メタファイル、ActiveX コントロールなど、さまざまな対象に表示するために使用する情報が含まれています。  
  
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
 `cbSize`  
 構造体のサイズ、(バイト単位)。  
  
 **dwDrawAspect**  
 ターゲットの表現方法を指定します。 表現には、コンテンツ、アイコン、サムネイル、または印刷したドキュメントを含めることができます。 使用可能な値の一覧は、次を参照してください。[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)と[DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644)です。  
  
 **lindex**  
 描画操作の対象は、ターゲットの部分です。 その解釈は、値によって、 **dwDrawAspect**メンバー。  
  
 **ptd**  
 ポインター、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)構造を指定されたアスペクトに応じて描画の最適化を有効にします。 新しいオブジェクトおよび最適化された描画インターフェイスをサポートするコンテナーがこのメンバーもをサポートすることに注意してください。 古いオブジェクトおよびコンテナーを常に最適化された描画インターフェイスをサポートしない指定**NULL**このメンバーにします。  
  
 **hicTargetDev**  
 ターゲット デバイスの情報コンテキストを指す**ptd**元となるオブジェクトはデバイス メトリックを抽出し、デバイスの機能をテストします。 場合**ptd**は**NULL**、オブジェクトの値を無視する必要があります、 **hicTargetDev**メンバー。  
  
 **hdcDraw**  
 描画するデバイス コンテキスト。 ウィンドウなしのオブジェクト、 **hdcDraw**メンバーが、`MM_TEXT`マッピング モードの論理座標が格納先ウィンドウのクライアント座標に一致するとします。 さらに、デバイス コンテキストは通常によって渡されたものと同じ状態にする必要があります、`WM_PAINT`メッセージ。  
  
 **prcBounds**  
 ポインター、 [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907)の四角形を指定する構造体**hdcDraw**オブジェクトを描画する必要があります。 このメンバーは、配置やオブジェクトの拡大を制御します。 このメンバーにする必要があります**NULL**ウィンドウなしのインプレース アクティブなオブジェクトを描画します。 その他のすべての状況で**NULL**有効な値をできないことになります、`E_INVALIDARG`エラー コード。 場合は、コンテナーを渡す以外**NULL**ウィンドウなしのオブジェクト、オブジェクトに値が指定したデバイス コンテキストおよび四角形に要求された外観を表示します。 コンテナーは、オブジェクトの 2 つ目、非アクティブなビューを表示するために、オブジェクトを印刷したり、ウィンドウなしのオブジェクトからこれを要求できます。  
  
 **prcWBounds**  
 場合**hdcDraw**メタファイル デバイス コンテキストは、(を参照してください[調べるため](http://msdn.microsoft.com/library/windows/desktop/dd144877)Windows SDK で)、これへのポインター、 **RECTL**外接する四角形を指定する構造体、基になるメタファイル。 四角形の構造には、ウィンドウのエクステントとウィンドウの原点が含まれています。 これらの値は、メタファイルを描画するために役立ちます。 によって示される四角形**prcBounds**この内で入れ子には、 **prcWBounds**四角形が同じ座標空間。  
  
 **bOptimize**  
 コントロールの描画の最適化、それ以外の場合 0 場合 0 以外の値。 描画を最適化すると、デバイス コンテキストの状態は自動的に回復が完了したらレンダリングします。  
  
 **bZoomed**  
 以外の場合は、ターゲットには 0 それ以外の場合、ズームの倍率。 ズームの倍率に格納されている**ZoomNum**です。  
  
 **bRectInHimetric**  
 0 以外の値の大きさ**prcBounds**に**HIMETRIC**, は 0 それ以外の場合。  
  
 **ZoomNum**  
 幅とオブジェクトの描画先の四角形の高さ。 ターゲットの x 軸 (現在の大きさにオブジェクトの自然なサイズの比率) に倍率の値は、 **ZoomNum.cx**の値で割った値**ZoomDen.cx**です。 Y 軸に沿って倍率は、同様の方法で実現されます。  
  
 **ZoomDen**  
 実際の幅とターゲットの高さ。  
  
## <a name="remarks"></a>コメント  
 この構造体の一般的な使用は、ターゲット オブジェクトの表示中に情報の取得になります。 たとえばから値を取得できません`ATL_DRAWINFO`、オーバー ロードの内部[CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)です。  
  
 この構造体は、ターゲット デバイスに対してオブジェクトの外観を表示するために使用される適切な情報を格納します。 提供された情報は、画面、プリンター、またはメタファイルに描画で使用できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)






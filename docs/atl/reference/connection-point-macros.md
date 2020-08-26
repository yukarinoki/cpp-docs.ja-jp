---
title: 接続ポイントのマクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: 6c716ad85ecb458b4be418a7e8554687dd19f3d8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833518"
---
# <a name="connection-point-macros"></a>接続ポイントのマクロ

これらのマクロは、接続ポイントマップとエントリを定義します。

|マクロ|説明|
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|接続ポイントのマップエントリの開始をマークします。|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|マップに接続ポイントを入力します。|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017)CONNECTION_POINT_ENTRY と似ていますが、iid へのポインターを受け取ります。|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|接続ポイントのマップエントリの終了をマークします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="begin_connection_point_map"></a><a name="begin_connection_point_map"></a> BEGIN_CONNECTION_POINT_MAP

接続ポイントのマップエントリの開始をマークします。

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からコネクションポイントを格納しているクラスの名前。

### <a name="remarks"></a>解説

BEGIN_CONNECTION_POINT_MAP マクロを使用して接続ポイントマップを開始し、 [CONNECTION_POINT_ENTRY](#connection_point_entry) マクロを使用して各接続ポイントのエントリを追加し、 [END_CONNECTION_POINT_MAP](#end_connection_point_map) マクロを使用してマップを完了します。

ATL のコネクションポイントの詳細については、「 [接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

## <a name="connection_point_entry-and-connection_point_entry_p"></a><a name="connection_point_entry"></a> CONNECTION_POINT_ENTRY と CONNECTION_POINT_ENTRY_P

指定したインターフェイスの接続ポイントを接続ポイントマップに入力して、そのインターフェイスにアクセスできるようにします。

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からコネクションポイントマップに追加されるインターフェイスの GUID。

*piid*<br/>
からAdde であるインターフェイスの GUID へのポインター。

### <a name="remarks"></a>解説

マップ内の接続ポイントエントリは、 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)によって使用されます。 コネクションポイントマップを含むクラスは、から継承する必要があり `IConnectionPointContainerImpl` ます。

[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロを使用して接続ポイントマップを開始し、CONNECTION_POINT_ENTRY マクロを使用して各接続ポイントのエントリを追加し、 [END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロを使用してマップを完了します。

ATL のコネクションポイントの詳細については、「 [接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

## <a name="end_connection_point_map"></a><a name="end_connection_point_map"></a> END_CONNECTION_POINT_MAP

接続ポイントのマップエントリの終了をマークします。

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>解説

[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロを使用して接続ポイントマップを開始し、 [CONNECTION_POINT_ENTRY](#connection_point_entry)マクロを使用して各接続ポイントのエントリを追加し、END_CONNECTION_POINT_MAP マクロを使用してマップを完了します。

ATL のコネクションポイントの詳細については、「 [接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)<br/>
[接続ポイントのグローバル関数](../../atl/reference/connection-point-global-functions.md)

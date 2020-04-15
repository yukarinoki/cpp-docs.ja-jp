---
title: 接続ポイント マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: 361cf6ab2c7af142c1d57c002681ccf6e4a87bda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331497"
---
# <a name="connection-point-macros"></a>接続ポイント マクロ

これらのマクロは、コネクション ポイント マップとエントリを定義します。

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|コネクション ポイント マップ エントリの先頭を示します。|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|マップに接続ポイントを入力します。|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (ビジュアルスタジオ2017)CONNECTION_POINT_ENTRYに似ていますが、iidへのポインタを受け取ります。|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|コネクション ポイント マップ エントリの終わりを示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="begin_connection_point_map"></a><a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP

コネクション ポイント マップ エントリの先頭を示します。

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]コネクション ポイントを含むクラスの名前。

### <a name="remarks"></a>解説

BEGIN_CONNECTION_POINT_MAP マクロでコネクション ポイント マップを開始し[、CONNECTION_POINT_ENTRY](#connection_point_entry)マクロを使用して各コネクション ポイントのエントリを追加し[、END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロを使用してマップを完成させます。

ATL の接続ポイントの詳細については、記事「[接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

## <a name="connection_point_entry-and-connection_point_entry_p"></a><a name="connection_point_entry"></a>CONNECTION_POINT_ENTRYとCONNECTION_POINT_ENTRY_P

指定したインターフェイスのコネクション ポイントを接続ポイント マップに入力し、アクセスできるようにします。

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]コネクション ポイント マップに追加されるインターフェイスの GUID。

*ピッド*<br/>
[in]追加されるインターフェイスの GUID へのポインター。

### <a name="remarks"></a>解説

マップ内の接続ポイント エントリは[、IConnectionPoint コンテナインプラジュレス](../../atl/reference/iconnectionpointcontainerimpl-class.md)によって使用されます。 コネクション ポイント マップを含むクラスは`IConnectionPointContainerImpl`、 から継承する必要があります。

コネクション ポイント マップを[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロで開始し、CONNECTION_POINT_ENTRY マクロを使用して各コネクション ポイントのエントリを追加し[、END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロを使用してマップを完成させます。

ATL の接続ポイントの詳細については、記事「[接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

## <a name="end_connection_point_map"></a><a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP

コネクション ポイント マップ エントリの終わりを示します。

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>解説

[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロでコネクション ポイント マップを開始し[、CONNECTION_POINT_ENTRY](#connection_point_entry)マクロを使用して各コネクション ポイントのエントリを追加し、END_CONNECTION_POINT_MAP マクロを使用してマップを完成させます。

ATL の接続ポイントの詳細については、記事「[接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)<br/>
[接続ポイントのグローバル関数](../../atl/reference/connection-point-global-functions.md)

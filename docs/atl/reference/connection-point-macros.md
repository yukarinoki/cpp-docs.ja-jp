---
title: コネクション ポイントに関するマクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a654f820d3c1dcdaa49ed8b3b3203d2c271b6880
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055484"
---
# <a name="connection-point-macros"></a>コネクション ポイントに関するマクロ

これらのマクロは、コネクション ポイントのマップとエントリを定義します。

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|接続ポイントのマップ エントリの先頭をマークします。|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|接続ポイントをマップに入力します。|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017)同様に CONNECTION_POINT_ENTRY では、iid へのポインターがかかります。|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|接続ポイントのマップ エントリの終了を示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="begin_connection_point_map"></a>  BEGIN_CONNECTION_POINT_MAP

接続ポイントのマップ エントリの先頭をマークします。

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>パラメーター

*x*<br/>
[in]接続ポイントを含むクラスの名前。

### <a name="remarks"></a>Remarks

BEGIN_CONNECTION_POINT_MAP マクロ、コネクション ポイントのマップを開始、各接続ポイントのエントリを追加、 [CONNECTION_POINT_ENTRY](#connection_point_entry)マクロを含むマップを完了して、 [END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロ。

ATL 接続ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

##  <a name="connection_point_entry"></a>  CONNECTION_POINT_ENTRY と CONNECTION_POINT_ENTRY_P

アクセスできるようにに接続ポイントのマップに指定されたインターフェイスの接続ポイントを入力します。

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
[in]コネクション ポイントのマップに追加されているインターフェイスの GUID です。

*piid*<br/>
[in]Adde をされているインターフェイスの GUID へのポインター。

### <a name="remarks"></a>Remarks

マップ内の接続ポイント エントリを使って[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)します。 コネクション ポイントのマップを含むクラスを継承する必要があります`IConnectionPointContainerImpl`します。

接続ポイントのマップを開始、 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロ、CONNECTION_POINT_ENTRY マクロでは、接続ポイントの各エントリの追加し、を対応付けを完了、 [END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロ。

ATL 接続ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

##  <a name="end_connection_point_map"></a>  END_CONNECTION_POINT_MAP

接続ポイントのマップ エントリの終了を示します。

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>Remarks

接続ポイントのマップを開始、 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロは、各接続ポイントのエントリを追加、 [CONNECTION_POINT_ENTRY](#connection_point_entry)マクロ、END_ でマップを完了してCONNECTION_POINT_MAP マクロです。

ATL 接続ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)<br/>
[コネクション ポイントに関するグローバル関数](../../atl/reference/connection-point-global-functions.md)

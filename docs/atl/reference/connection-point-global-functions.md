---
description: '詳細情報: 接続ポイントのグローバル関数'
title: 接続ポイントのグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 33a9f81b086b572bb31f730e4a6ce1bac0fb45d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141142"
---
# <a name="connection-point-global-functions"></a>接続ポイントのグローバル関数

これらの関数は、コネクションポイントとシンクマップのサポートを提供します。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|機能|説明|
|-|-|
|[AtlAdvise](#atladvise)|オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。|
|[AtlUnadvise](#atlunadvise)|を介して確立された接続を終了 `AtlAdvise` します。|
|[AtlAdviseSinkMap](#atladvisesinkmap)|イベントシンクマップ内のエントリをアドバイズまたはアンアドバイズします。|

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="atladvise"></a><a name="atladvise"></a> AtlAdvise

オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>パラメーター

*pUnkCP*<br/>
から `IUnknown` クライアントが接続を希望するオブジェクトのへのポインター。

*パンク*<br/>
からクライアントのへのポインター `IUnknown` 。

*iid*<br/>
からコネクションポイントの GUID。 通常、これは接続ポイントによって管理される送信インターフェイスと同じです。

*ウィザード*<br/>
入出力接続を一意に識別するクッキーへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

シンクは、コネクションポイントでサポートされている送信インターフェイスを実装します。 クライアントは、 *pdw* の cookie を使用して接続を削除します。これを [atlunadvise](#atlunadvise)に渡します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

## <a name="atlunadvise"></a><a name="atlunadvise"></a> AtlUnadvise

[AtlAdvise](#atladvise)を介して確立された接続を終了します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>パラメーター

*pUnkCP*<br/>
から `IUnknown` クライアントが接続されているオブジェクトのへのポインター。

*iid*<br/>
からコネクションポイントの GUID。 通常、これは接続ポイントによって管理される送信インターフェイスと同じです。

*dw*<br/>
から接続を一意に識別するクッキー。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

## <a name="atladvisesinkmap"></a><a name="atladvisesinkmap"></a> AtlAdviseSinkMap

オブジェクトのシンク イベント マップのすべてのエントリをアドバイズするか、アドバイズを中止します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>パラメーター

*未満*<br/>
からシンクマップを格納しているオブジェクトへのポインター。

*bAdvise*<br/>
からすべてのシンクエントリを推奨する場合は TRUE。すべてのシンクエントリをスキップする場合は FALSE。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[接続ポイントのマクロ](../../atl/reference/connection-point-macros.md)

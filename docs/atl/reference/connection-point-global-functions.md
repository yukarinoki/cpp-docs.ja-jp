---
title: 接続ポイントのグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 6474297f8b9adf04541f7d232fb88d5e52d4e88c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331528"
---
# <a name="connection-point-global-functions"></a>接続ポイントのグローバル関数

これらの関数は、コネクション ポイントとシンク マップをサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlAdvise](#atladvise)|オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。|
|[AtlUnadvise](#atlunadvise)|を使用して確立された接続`AtlAdvise`を終了します。|
|[AtlAdviseSinkMap](#atladvisesinkmap)|イベント シンク マップのエントリをアドバイスまたはアンアアドバイスします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atladvise"></a><a name="atladvise"></a>アトルアアドバイス

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

*pウンクCP*<br/>
[in]クライアントが接続する`IUnknown`オブジェクトへのポインター。

*パンク*<br/>
[in]クライアント`IUnknown`の .

*Iid*<br/>
[in]接続ポイントの GUID。 通常、これはコネクション ポイントによって管理される発信インターフェイスと同じです。

*Pdw*<br/>
[アウト]接続を一意に識別する Cookie へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

シンクは、コネクション ポイントでサポートされる発信インターフェイスを実装します。 クライアントは*pdw*クッキーを使用して[、AtlUnadvise](#atlunadvise)に渡すことによって接続を削除します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

## <a name="atlunadvise"></a><a name="atlunadvise"></a>アトルアンアアドバイス

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

*pウンクCP*<br/>
[in]クライアントが接続している`IUnknown`オブジェクトへのポインター。

*Iid*<br/>
[in]接続ポイントの GUID。 通常、これはコネクション ポイントによって管理される発信インターフェイスと同じです。

*dw*<br/>
[in]接続を一意に識別する Cookie。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

## <a name="atladvisesinkmap"></a><a name="atladvisesinkmap"></a>アトルアアドバイスシンクマップ

オブジェクトのシンク イベント マップのすべてのエントリをアドバイズするか、アドバイズを中止します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
[in]シンク マップを含むオブジェクトへのポインター。

*アドバイス*<br/>
[in]すべてのシンク エントリに対して推奨される場合は TRUE。すべてのシンク エントリが未確認の場合は FALSE。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[接続ポイント マクロ](../../atl/reference/connection-point-macros.md)

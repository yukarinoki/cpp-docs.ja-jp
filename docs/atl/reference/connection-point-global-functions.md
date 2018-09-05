---
title: コネクション ポイントに関するグローバル関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f68c22ff88ac92357dabfef8076c160271a76378
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756491"
---
# <a name="connection-point-global-functions"></a>コネクション ポイントに関するグローバル関数

これらの関数は、コネクション ポイントのサポートを提供し、シンク マップ。

> [!IMPORTANT]
>  Windows ランタイムで実行するアプリケーションでは、次の表に示す関数を使用できません。

|||
|-|-|
|[AtlAdvise](#atladvise)|オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。|
|[AtlUnadvise](#atlunadvise)|を通じて確立された接続を終了します`AtlAdvise`します。|
|[AtlAdviseSinkMap](#atladvisesinkmap)|アドバイズするか、イベント シンク マップ内のエントリ。|  

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

##  <a name="atladvise"></a>  AtlAdvise

オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。

> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>パラメーター

*pUnkCP*  
[in]ポインター、`IUnknown`オブジェクトのクライアントが使用して接続します。

*pUnk*  
[in]クライアントへのポインター`IUnknown`します。

*iid*  
[in]接続ポイントの GUID です。 通常、これは、接続ポイントによって管理するアウトゴーイング インターフェイスと同じです。

*pdw*  
[out]接続を一意に識別するクッキーへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

シンク接続ポイントでサポートされているアウトゴーイング インターフェイスを実装します。 クライアントを使用して、 *pdw*に渡すことによって、接続を削除するクッキー [AtlUnadvise](#atlunadvise)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

##  <a name="atlunadvise"></a>  AtlUnadvise

を通じて確立された接続を終了します[AtlAdvise](#atladvise)します。

> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>パラメーター

*pUnkCP*  
[in]ポインター、`IUnknown`オブジェクトで、クライアントが接続されているのです。

*iid*  
[in]接続ポイントの GUID です。 通常、これは、接続ポイントによって管理するアウトゴーイング インターフェイスと同じです。

*dw*  
[in]接続を一意に識別するクッキー。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

##  <a name="atladvisesinkmap"></a>  AtlAdviseSinkMap

オブジェクトのシンク イベント マップのすべてのエントリをアドバイズするか、アドバイズを中止します。

> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>パラメーター

*pT*  
[in]シンクのマップを格納するオブジェクトへのポインター。

*bAdvise*  
[in]TRUE の場合、シンクのすべてのエントリがあることをお勧めします。すべてのシンクのエントリがアドバイズを中止する場合は FALSE です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)   
[接続ポイントに関するマクロ](../../atl/reference/connection-point-macros.md)

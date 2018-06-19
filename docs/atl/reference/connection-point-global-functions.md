---
title: 接続ポイントのグローバル関数 |Microsoft ドキュメント
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
ms.openlocfilehash: 7dc6cd11cb1f04ba877524cd1ae6134a7dd93d09
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362792"
---
# <a name="connection-point-global-functions"></a>接続ポイントのグローバル関数
これらの関数は、接続ポイントのサポートを提供し、シンク マップ。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。|  
|[AtlUnadvise](#atlunadvise)|通じて確立された接続を終了する`AtlAdvise`です。|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|アドバイズするか、イベント シンク マップのエントリ。|  

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
 `pUnkCP`  
 [in]ポインター、 **IUnknown**オブジェクトのクライアントが接続ましょう。  
  
 *pUnk*  
 [in]クライアントへのポインター **IUnknown**です。  
  
 `iid`  
 [in]接続ポイントの GUID です。 通常、これは、接続ポイントによって管理されている着信インターフェイスと同じです。  
  
 `pdw`  
 [out]接続を一意に識別するクッキーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 シンクでは、接続ポイントでサポートされている着信インターフェイスを実装します。 クライアントを使用して、`pdw`に渡すことによって、接続を削除する cookie [AtlUnadvise](#atlunadvise)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>  AtlUnadvise  
 通じて確立された接続を終了する[AtlAdvise](#atladvise)です。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkCP`  
 [in]ポインター、 **IUnknown**のクライアントが接続しているオブジェクト。  
  
 `iid`  
 [in]接続ポイントの GUID です。 通常、これは、接続ポイントによって管理されている着信インターフェイスと同じです。  
  
 `dw`  
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
 [in]シンク マップを含むオブジェクトへのポインター。  
  
 `bAdvise`  
 [in]**true**シンクのすべてのエントリをアドバイズする場合**false**シンクのすべてのエントリは、アドバイズを中止する場合。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)   
 [接続ポイントに関するマクロ](../../atl/reference/connection-point-macros.md)

---
title: ティアオフ クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1072faed01033bec9fec127318334f8a61ac29e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362883"
---
# <a name="ccomcachedtearoffobject-class"></a>ティアオフ クラス
このクラスは実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)ティアオフ インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
template
 <class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
 ::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>パラメーター  
 `contained`  
 ティアオフ クラスから派生`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|コンストラクターです。|  
|[ティアオフ:: ~ ティアオフ](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|参照カウントをインクリメント、`CComCachedTearOffObject`オブジェクト。|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|呼び出し、 `m_contained::FinalConstruct` (ティアオフ クラスのメソッド)。|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|呼び出し、 `m_contained::FinalRelease` (ティアオフ クラスのメソッド)。|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|ポインターを返します、`IUnknown`の`CComCachedTearOffObject`オブジェクト、または、ティアオフ クラスで要求されたインターフェイス (クラス`contained`)。|  
|[CComCachedTearOffObject::Release](#release)|参照カウントをデクリメント、`CComCachedTearOffObject`オブジェクトおよび参照カウントが 0 の場合は、それを破棄します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|A`CComContainedObject`ティアオフ クラスから派生したオブジェクト (クラス`contained`)。|  
  
## <a name="remarks"></a>コメント  
 `CComCachedTearOffObject` 実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)ティアオフ インターフェイスです。 このクラスとは異なります`CComTearOffObject`で`CComCachedTearOffObject`独自**IUnknown**、所有者オブジェクトから別の**IUnknown** (ティアオフが作成される対象のオブジェクトが、所有者です)。 `CComCachedTearOffObject` 独自に保持の参照カウントの**IUnknown**し、その参照カウントが 0 と自体を削除します。 ただし、そのティアオフのいずれかのクエリを実行する場合は、インターフェイス、所有者オブジェクトの参照カウント**IUnknown**が増分されます。  
  
 場合、`CComCachedTearOffObject`オブジェクト ティアオフ実装が既にインスタンス化され、もう一度同じについてティアオフ インターフェイスが照会された`CComCachedTearOffObject`オブジェクトが再利用します。 これに対して、ティアオフ インターフェイス実装されている場合、 `CComTearOffObject` 、所有者オブジェクトをもう一度照会された別`CComTearOffObject`インスタンス化されます。  
  
 Owner クラスを実装する必要があります`FinalRelease`と呼び出し**リリース**でキャッシュされた**IUnknown**の`CComCachedTearOffObject`、参照カウントをデクリメントするされます。 これにより、`CComCachedTearOffObject`の`FinalRelease`を呼び出すし、ティアオフを削除します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComCachedTearOffObject::AddRef  
 参照カウントをインクリメント、`CComCachedTearOffObject`を 1 つのオブジェクト。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断やテストに使用する値。  
  
##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject  
 コンストラクターです。  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]ポインター、 **IUnknown**の`CComCachedTearOffObject`です。  
  
### <a name="remarks"></a>コメント  
 初期化、`CComContainedObject`メンバー、[で呼び出され](#m_contained)です。  
  
##  <a name="dtor"></a>  ティアオフ:: ~ ティアオフ  
 デストラクターです。  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)です。  
  
##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct  
 呼び出し**m_contained::FinalConstruct**を作成する`m_contained`、 `CComContainedObject` <  `contained`> ティアオフ クラスによって実装されるインターフェイスへのアクセスに使用されるオブジェクト。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease  
 呼び出し**m_contained::FinalRelease**を解放する`m_contained`、 `CComContainedObject` <  `contained`> オブジェクト。  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained  
 A[した](../../atl/reference/ccomcontainedobject-class.md)ティアオフ クラスから派生したオブジェクト。  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>パラメーター  
 `contained`  
 [in]ティアオフ クラスから派生`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。  
  
### <a name="remarks"></a>コメント  
 メソッド`m_contained`継承インターフェイスへのアクセス、ティアオフ ティアオフ クラス内で、キャッシュされたティアオフ オブジェクトの使用は`QueryInterface`、 `FinalConstruct`、および`FinalRelease`です。  
  
##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 要求されたインターフェイスがある場合**IUnknown**へのポインターを返します、`CComCachedTearOffObject`の独自**IUnknown**し、参照カウントをインクリメントします。 ティアオフ クラスを使用して、上のインターフェイスに対してそれ以外の場合、クエリ、 [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface)から継承されたメソッド`CComObjectRootEx`です。  

  
##  <a name="release"></a>  CComCachedTearOffObject::Release  
 1 つの参照カウントをデクリメントし、参照カウントが 0 の場合は、削除、`CComCachedTearOffObject`オブジェクト。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 非デバッグ ビルドでは、常に 0 を返します。 デバッグ ビルドで、診断に役に立たず、テスト可能な値を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComTearOffObject クラス](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

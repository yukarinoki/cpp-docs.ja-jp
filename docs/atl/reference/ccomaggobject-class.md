---
title: クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 426a01c1957b276174b8b36884605b69dd501de8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364220"
---
# <a name="ccomaggobject-class"></a>クラス
このクラスは、実装、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集約オブジェクトのインターフェイスです。 定義上、外部オブジェクトに集約オブジェクトが含まれています。 `CComAggObject`クラスがに似ていますが、 [CComObject クラス](../../atl/reference/ccomobject-class.md)は外部クライアントに直接アクセスできるインターフェイスを公開する点を除いて、します。  
  
## <a name="syntax"></a>構文  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>パラメーター  
 `contained`  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|コンストラクターです。|  
|[:: ~ すると](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|集約オブジェクトの参照カウントをインクリメントします。|  
|[CComAggObject::CreateInstance](#createinstance)|この静的関数では、新しいを作成することができます**すると <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)です。|  
|[CComAggObject::FinalConstruct](#finalconstruct)|最終初期化を実行`m_contained`です。|  
|[CComAggObject::FinalRelease](#finalrelease)|最終的な破棄を実行`m_contained`です。|  
|[CComAggObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComAggObject::Release](#release)|集約オブジェクトの参照カウントをデクリメントします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|デリゲート`IUnknown`外側の不明な呼び出しです。|  
  
## <a name="remarks"></a>コメント  
 `CComAggObject` 実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集約オブジェクト。 `CComAggObject` それぞれの**IUnknown**インターフェイスで、外部のオブジェクトとは別**IUnknown**インターフェイス、および参照カウントを保持します。  
  
 集計の詳細については、記事を参照してください。 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComAggObject::AddRef  
 集約オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たず、テスト可能な値です。  
  
##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject  
 コンストラクターです。  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]外部不明です。  
  
### <a name="remarks"></a>コメント  
 初期化します、`CComContainedObject`メンバー、[で呼び出され](#m_contained)、およびモジュールのロック カウントをインクリメントします。  
  
 デストラクター、モジュール ロック カウントをデクリメントします。  
  
##  <a name="dtor"></a>  :: ~ すると  
 デストラクターです。  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)、およびモジュールのロック カウントをデクリメントします。  
  
##  <a name="createinstance"></a>  CComAggObject::CreateInstance  
 この静的関数では、新しいを作成することができます**すると <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)です。  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 [out]ポインター、**すると\<* * * に含まれる* **>** ポインター。 場合`CreateInstance`は成功せず`pp`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 返されるオブジェクトが参照カウントは 0、ためコール`AddRef`、すぐに使用して**リリース**を完了するとオブジェクトへのポインターの参照を解放します。  
  
 必要な送信しないオブジェクトへのアクセスが、引き続きのオーバーヘッドがなく、新しいオブジェクトを作成する場合`CoCreateInstance`を使用して[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。  
  
##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct  
 オブジェクトの構築の最終段階で呼び出されると、このメソッドの最後の初期化を実行、[で呼び出され](#m_contained)メンバー。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="finalrelease"></a>  CComAggObject::FinalRelease  
 オブジェクトの破棄中に呼び出されると、このメソッドは、解放、[で呼び出され](#m_contained)メンバー。  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComAggObject::m_contained  
 A[した](../../atl/reference/ccomcontainedobject-class.md)クラスから派生したオブジェクト。  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>パラメーター  
 `contained`  
 [in]派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。  
  
### <a name="remarks"></a>コメント  
 すべて**IUnknown**を介して呼び出します`m_contained`外側の不明な種類に委任されます。  
  
##  <a name="queryinterface"></a>  CComAggObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの識別子。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター`iid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**です。  
  
 `pp`  
 [out]型で識別されるインターフェイス ポインターへのポインター`Q`です。 オブジェクトは、このインターフェイスをサポートしていない場合`pp`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 要求されたインターフェイスがある場合**IUnknown**、 `QueryInterface` 、集計されたオブジェクトの独自のポインターを返します**IUnknown**し、参照カウントをインクリメントします。 それ以外の場合、このメソッド クエリ インターフェイスを介して、`CComContainedObject`メンバー、[で呼び出され](#m_contained)です。  
  
##  <a name="release"></a>  CComAggObject::Release  
 集約オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たず、テスト可能な値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [集約](aggregation-and-class-factory-macros.md#declare_only_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [クラスの概要](../../atl/atl-class-overview.md)

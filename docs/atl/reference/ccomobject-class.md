---
title: CComObject クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37c8140d3579fc5d629b10c8e3ae5459e6492920
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198661"
---
# <a name="ccomobject-class"></a>CComObject クラス
このクラスは実装`IUnknown`非集約オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 *ベース*  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|コンストラクターです。|  
|[CComObject:: ~ CComObject](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|  
|[CComObject::CreateInstance](#createinstance)|(静的)新たに作成`CComObject`オブジェクト。|  
|[CComObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComObject::Release](#release)|オブジェクトの参照カウントをデクリメントします。|  
  
## <a name="remarks"></a>Remarks  
 `CComObject` 実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)非集約オブジェクト。 ただし、呼び出し`QueryInterface`、 `AddRef`、および`Release`に委任されます`CComObjectRootEx`します。  
  
 使用しての詳細については`CComObject`、記事をご覧ください[ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComObject::AddRef  
 オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 この関数は、オブジェクトの新しいインクリメントされた参照カウントを返します。 この値は、診断やテストに便利な可能性があります。  
  
##  <a name="ccomobject"></a>  CComObject::CComObject  
 コンス トラクターは、モジュールのロック カウントをインクリメントします。  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 <em>void\*</em>  
 [in]この名前のないパラメーターは使用されません。 他の対称性が存在する`CComXXXObjectXXX`コンス トラクター。  
  
### <a name="remarks"></a>Remarks  
 デストラクターをデクリメントこと。  
  
 場合、 `CComObject`-を使用して派生オブジェクトが正常に作成、**新しい**オペレーターは、初期の参照カウントが 0 です。 参照カウントを適切な値 (1) を設定するへの呼び出しを行い、 [AddRef](#addref)関数。  
  
##  <a name="dtor"></a>  CComObject:: ~ CComObject  
 デストラクターです。  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)、およびモジュールのロック カウントをデクリメントします。  

  
##  <a name="createinstance"></a>  CComObject::CreateInstance  
 この静的関数では、新たに作成することができます**CComObject <** `Base` **>** のオーバーヘッドがなく、オブジェクト[CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)します。  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 *pp*  
 [out]ポインターを**CComObject <** `Base` **>** ポインター。 場合`CreateInstance`が成功すると、 *pp* NULL に設定されます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 返されるオブジェクトが参照カウントを 0、ためコール`AddRef`しを使用して、すぐに`Release`完了すると、オブジェクトへのポインターの参照を解放します。  
  
 オブジェクトへのアクセスが直接必要ありませんが、引き続きのオーバーヘッドなしの新しいオブジェクトを作成する場合`CoCreateInstance`を使用して、[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="queryinterface"></a>  CComObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]要求されているインターフェイスの識別子。  
  
 *ppvObject*  
 [out]によって識別されるインターフェイス ポインターへのポインター *iid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObject* NULL に設定されます。  
  
 *pp*  
 [out]型によって識別されるインターフェイス ポインターへのポインター`Q`します。 オブジェクトは、このインターフェイスをサポートしていない場合*pp* NULL に設定されます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="release"></a>  CComObject::Release  
 オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 この関数は、オブジェクトの新しいデクリメントの参照カウントを返します。 デバッグ ビルドでは、戻り値は診断に役立ちますやテストを使用可能性があります。 非デバッグ ビルドで`Release`常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [クラスの概要](../../atl/atl-class-overview.md)

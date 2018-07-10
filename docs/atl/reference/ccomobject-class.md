---
title: CComObject クラス |Microsoft ドキュメント
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
ms.openlocfilehash: af84d64d326ed7746b76db39ef26181ab96ca88d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361487"
---
# <a name="ccomobject-class"></a>CComObject クラス
このクラスは実装**IUnknown**非集約オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
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
  
## <a name="remarks"></a>コメント  
 `CComObject` 実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)非集約オブジェクト。 ただし、呼び出し`QueryInterface`、 `AddRef`、および**リリース**に委任され`CComObjectRootEx`です。  
  
 使用しての詳細については`CComObject`、記事を参照して[ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)です。  
  
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
 この関数は、オブジェクトの新しいインクリメント参照カウントを返します。 この値は、診断やテストに役立つである可能性があります。  
  
##  <a name="ccomobject"></a>  CComObject::CComObject  
 コンス トラクターは、モジュールのロック カウントをインクリメントします。  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 **void\***  
 [in]この名前のないパラメーターは使用されません。 その他を含む対称に存在する場合 **ほか * * * XXX*`Object`*XXX*コンス トラクターです。  
  
### <a name="remarks"></a>コメント  
 デストラクターをデクリメントことです。  
  
 場合、 `CComObject`-派生オブジェクトが正常に作成されたを使用して、**新しい**演算子、初期の参照カウントが 0 です。 参照カウントを適切な値 (1) に設定するには、呼び出しを行う、 [AddRef](#addref)関数。  
  
##  <a name="dtor"></a>  CComObject:: ~ CComObject  
 デストラクターです。  
  
```
CComObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)、およびモジュールのロック カウントをデクリメントします。  

  
##  <a name="createinstance"></a>  CComObject::CreateInstance  
 この静的関数では、新しいを作成することができます**CComObject <** `Base` **>** のオーバーヘッドがなく、オブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)です。  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 [out]ポインター、 **CComObject <** `Base` **>** ポインター。 場合`CreateInstance`は成功せず`pp`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 返されるオブジェクトが参照カウントは 0、ためコール`AddRef`、すぐに使用して**リリース**を完了するとオブジェクトへのポインターの参照を解放します。  
  
 必要な送信しないオブジェクトへのアクセスが、引き続きのオーバーヘッドがなく、新しいオブジェクトを作成する場合`CoCreateInstance`を使用して[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。  
  
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
 `iid`  
 [in]要求されているインターフェイスの識別子。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター`iid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**です。  
  
 `pp`  
 [out]型で識別されるインターフェイス ポインターへのポインター`Q`です。 オブジェクトは、このインターフェイスをサポートしていない場合`pp`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="release"></a>  CComObject::Release  
 オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 この関数は、オブジェクトの新しいデクリメント参照カウントを返します。 デバッグ ビルドで、戻り値の値は、診断に役に立たず、テストを指定できます。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [クラスの概要](../../atl/atl-class-overview.md)

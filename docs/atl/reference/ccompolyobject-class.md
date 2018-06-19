---
title: CComPolyObject クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383a83a2e2b09c9652e7185592a5891179416e0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364103"
---
# <a name="ccompolyobject-class"></a>CComPolyObject クラス
このクラスは実装**IUnknown**集計または非集約オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template<class contained>  
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>パラメーター  
 `contained`  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComPolyObject::CComPolyObject](#ccompolyobject)|コンストラクターです。|  
|[CComPolyObject:: ~ CComPolyObject](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComPolyObject::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|  
|[CComPolyObject::CreateInstance](#createinstance)|(静的)新規作成することができます**CComPolyObject <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)です。|  
|[CComPolyObject::FinalConstruct](#finalconstruct)|最終初期化を実行`m_contained`です。|  
|[CComPolyObject::FinalRelease](#finalrelease)|最終的な破棄を実行`m_contained`です。|  
|[CComPolyObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComPolyObject::Release](#release)|オブジェクトの参照カウントをデクリメントします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComPolyObject::m_contained](#m_contained)|デリゲート**IUnknown**集約オブジェクトの場合、外側の不明なへの呼び出し、 **IUnknown**オブジェクトが集計されない場合は、オブジェクトの。|  
  
## <a name="remarks"></a>コメント  
 `CComPolyObject` 実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集計または非集約オブジェクト。  
  
 インスタンス`CComPolyObject`作成されると、外側の値が不明のチェックします。 場合は**NULL**、 **IUnknown**非集約オブジェクトには実装されています。 外側の unknown がない場合**NULL**、 **IUnknown**集約オブジェクトには実装されています。  
  
 使用する利点`CComPolyObject`両方を避けることが[すると](../../atl/reference/ccomaggobject-class.md)と[CComObject](../../atl/reference/ccomobject-class.md)モジュールに、集計と非集計のケースに対処します。 1 つ`CComPolyObject`オブジェクトは両方のケースを処理します。 つまり、モジュールに vtable の 1 つだけのコピーと、関数のうちの 1 つのコピーが存在します。 Vtable が大きい場合は、モジュールのサイズを大幅に縮小このできます。 ただし、vtable が小さい場合を使用して`CComPolyObject`には、集計または非集約オブジェクトは、最適化されていないために、わずかに大きくモジュールのサイズになりますが`CComAggObject`と`CComObject`です。  
  
 場合、`DECLARE_POLY_AGGREGATABLE`オブジェクトのクラス定義で指定されたマクロ`CComPolyObject`オブジェクトを作成するために使用されます。 `DECLARE_POLY_AGGREGATABLE` 自動的に宣言されますフル コントロールまたは Internet Explorer のコントロールを作成する、ATL プロジェクト ウィザードを使用するかどうか。  
  
 場合は、集計、`CComPolyObject`オブジェクトには、独自**IUnknown**、外側のオブジェクトから別の**IUnknown**、し、参照カウントを保持します。 `CComPolyObject` 使用して[した](../../atl/reference/ccomcontainedobject-class.md)を外側の不明な種類に委任します。  
  
 集計の詳細については、記事を参照してください。 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComPolyObject::AddRef  
 オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たず、テスト可能な値です。  
  
##  <a name="ccompolyobject"></a>  CComPolyObject::CComPolyObject  
 コンストラクターです。  
  
```
CComPolyObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]オブジェクトが集計される場合は、外側の unknown へのポインターまたは**NULL**場合、オブジェクトが集計されない場合は、オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 初期化します、`CComContainedObject`データ メンバー[で呼び出され](#m_contained)、およびモジュールのロック カウントをインクリメントします。  
  
 デストラクター、モジュール ロック カウントをデクリメントします。  
  
##  <a name="dtor"></a>  CComPolyObject:: ~ CComPolyObject  
 デストラクターです。  
  
```
~CComPolyObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)、およびモジュールのロック カウントをデクリメントします。  
  
##  <a name="createinstance"></a>  CComPolyObject::CreateInstance  
 新規作成することができます**CComPolyObject <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)です。  
  
```
static HRESULT WINAPI CreateInstance(  
    LPUNKNOWN pUnkOuter, 
    CComPolyObject<contained>** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 [out]ポインター、 **CComPolyObject <** `contained` **>** ポインター。 場合`CreateInstance`は成功せず`pp`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 返されるオブジェクトが参照カウントは 0、ためコール`AddRef`、すぐに使用して**リリース**を完了するとオブジェクトへのポインターの参照を解放します。  
  
 直接、オブジェクトへのアクセスが、引き続きのオーバーヘッドがなく、新しいオブジェクトを作成する場合`CoCreateInstance`を使用して[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。  
  
##  <a name="finalconstruct"></a>  CComPolyObject::FinalConstruct  
 オブジェクトの構築の最終段階で呼び出されると、このメソッドの最後の初期化を実行、[で呼び出され](#m_contained)データ メンバーです。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="finalrelease"></a>  CComPolyObject::FinalRelease  
 オブジェクトの破棄中に呼び出されると、このメソッドは、解放、[で呼び出され](#m_contained)データ メンバーです。  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComPolyObject::m_contained  
 A[した](../../atl/reference/ccomcontainedobject-class.md)クラスから派生したオブジェクト。  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>パラメーター  
 `contained`  
 [in]派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。  
  
### <a name="remarks"></a>コメント  
 **IUnknown**を介して呼び出します`m_contained`集約オブジェクトの場合、外側の不明なに委任され、 **IUnknown**オブジェクトが集計されない場合は、このオブジェクトの。  
  
##  <a name="queryinterface"></a>  CComPolyObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `Q`  
 COM インターフェイスです。  
  
 `iid`  
 [in]要求されているインターフェイスの識別子。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター`iid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**です。  
  
 `pp`  
 [out]識別されるインターフェイスへのポインター **__uuidof(Q)** です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 集約オブジェクトは、要求されたインターフェイスがある場合**IUnknown**、 `QueryInterface` 、集計されたオブジェクトの独自のポインターを返します**IUnknown**し、参照カウントをインクリメントします。 それ以外の場合、このメソッド クエリ インターフェイスを介して、`CComContainedObject`データ メンバー、[で呼び出され](#m_contained)です。  
  
##  <a name="release"></a>  CComPolyObject::Release  
 オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たず、テスト可能な値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)   
 [クラスの概要](../../atl/atl-class-overview.md)

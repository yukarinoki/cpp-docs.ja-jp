---
title: したクラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0d4b0a6491aaeb27e4a1d986db01c03d1c5314d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360176"
---
# <a name="ccomcontainedobject-class"></a>したクラス
このクラスは実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)所有者オブジェクトの委任することによって**IUnknown**です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>  
class CComContainedObject : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|コンストラクターです。 所有者オブジェクトのメンバーのポインターを初期化します`IUnknown`です。|  
|[した:: ~ しました。](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|所有者オブジェクトの参照カウントをインクリメントします。|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|所有者オブジェクトの取得`IUnknown`です。|  
|[CComContainedObject::QueryInterface](#queryinterface)|所有者オブジェクトの要求されたインターフェイスへのポインターを取得します。|  
|[CComContainedObject::Release](#release)|所有者オブジェクトの参照カウントをデクリメントします。|  
  
## <a name="remarks"></a>コメント  
 ATL を使用して`CComContainedObject`クラスに[すると](../../atl/reference/ccomaggobject-class.md)、 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)、および[ティアオフ](../../atl/reference/ccomcachedtearoffobject-class.md)です。 `CComContainedObject` 実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)所有者オブジェクトの委任することによって**IUnknown**です。 (所有者は、集計の外部オブジェクトまたはティアオフ インターフェイスの作成対象のオブジェクトのいずれか)。`CComContainedObject`呼び出し`CComObjectRootEx`の`OuterQueryInterface`、 `OuterAddRef`、および`OuterRelease`から継承されたすべて、`Base`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComContainedObject::AddRef  
 所有者オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たず、テスト可能な値です。  
  
##  <a name="ccomcontainedobject"></a>  CComContainedObject::CComContainedObject  
 コンストラクターです。  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]所有者オブジェクトの**IUnknown**です。  
  
### <a name="remarks"></a>コメント  
 セット、`m_pOuterUnknown`メンバー ポインター (を通じて継承、`Base`クラス) を`pv`です。  
  
##  <a name="dtor"></a>  した:: ~ しました。  
 デストラクターです。  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="getcontrollingunknown"></a>  CComContainedObject::GetControllingUnknown  
 返します、`m_pOuterUnknown`メンバー ポインター (を通じて継承、*ベース*クラス)、所有者オブジェクトの保持している**IUnknown**です。  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>戻り値  
 所有者オブジェクトの**IUnknown**です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを仮想にすることがある場合`Base`に宣言されている、 [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown)マクロです。  
  
##  <a name="queryinterface"></a>  CComContainedObject::QueryInterface  
 所有者オブジェクトの要求されたインターフェイスへのポインターを取得します。  
  
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
  
##  <a name="release"></a>  CComContainedObject::Release  
 所有者オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たず、テスト可能な値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

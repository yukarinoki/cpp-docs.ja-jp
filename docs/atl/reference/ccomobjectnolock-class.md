---
title: CComObjectNoLock クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd7f9fa0ac67592c5fca805eaa4bb4ec4b0ca153
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361480"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock クラス
このクラスは実装**IUnknown**の非集約オブジェクトは、コンス トラクターでのモジュールのロック カウント インクリメントされません。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>  
class CComObjectNoLock : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|コンストラクターです。|  
|[CComObjectNoLock:: ~ CComObjectNoLock](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|  
|[CComObjectNoLock::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを返します。|  
|[CComObjectNoLock::Release](#release)|オブジェクトの参照カウントをデクリメントします。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectNoLock` ような[CComObject](../../atl/reference/ccomobject-class.md)を実装することで[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)非集約オブジェクトです。 ただし、`CComObjectNoLock`は増分値はモジュールのロックは、コンス トラクターでカウントします。  
  
 ATL では、`CComObjectNoLock`クラス ファクトリの内部でします。 一般に、このクラスを直接使用するがありません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObjectNoLock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectNoLock::AddRef  
 オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たず、テスト可能な値です。  
  
##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock  
 コンストラクターです。 異なり[CComObject](../../atl/reference/ccomobject-class.md)モジュールのロック カウントをインクリメントしません。  
  
```
CComObjectNoLock(void* = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 **void\***  
 [in]この名前のないパラメーターは使用されません。 その他を含む対称に存在する場合 **ほか * * * XXX*`Object`*XXX*コンス トラクターです。  
  
##  <a name="dtor"></a>  CComObjectNoLock:: ~ CComObjectNoLock  
 デストラクターです。  
  
```
~CComObjectNoLock();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)です。  

  
##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの識別子。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター`iid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="release"></a>  CComObjectNoLock::Release  
 オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たず、テスト可能な値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

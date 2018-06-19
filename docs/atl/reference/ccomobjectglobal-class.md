---
title: CComObjectGlobal クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3614962d3bebada0c63b7fe804b52efaa965c6a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362444"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal クラス
このクラスを含むモジュールの参照カウントを管理する、`Base`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|コンストラクターです。|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|グローバル実装`AddRef`です。|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|グローバル実装`QueryInterface`です。|  
|[CComObjectGlobal::Release](#release)|グローバル実装**リリース**です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|含まれています、 **HRESULT**の構築時に返される、`CComObjectGlobal`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectGlobal` 含むモジュールの参照カウントを管理、`Base`オブジェクト。 `CComObjectGlobal` により、モジュールが解放されない限り、オブジェクトは削除されません。 オブジェクトは、全体のモジュールの参照カウントがゼロになったときにだけ削除されます。  
  
 たとえばを使用して`CComObjectGlobal`、クラス ファクトリは、すべてのクライアントで共有される共通のグローバル オブジェクトを保持できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectGlobal::AddRef  
 1 つずつ、オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断やテストに使用する値。  
  
### <a name="remarks"></a>コメント  
 既定では、`AddRef`呼び出し **_Module::Lock**ここで、 **_Module**のグローバル インスタンスは、 [CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラス。  
  
##  <a name="ccomobjectglobal"></a>  CComObjectGlobal::CComObjectGlobal  
 コンストラクターです。 呼び出し`FinalConstruct`し、設定[m_hResFinalConstruct](#m_hresfinalconstruct)を`HRESULT`によって返される`FinalConstruct`です。  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>コメント  
 基本クラスを派生していない場合[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)、独自に指定する必要があります`FinalConstruct`メソッドです。 このデストラクターは `FinalRelease` を呼び出します。  
  
##  <a name="dtor"></a>  CComObjectGlobal:: ~ CComObjectGlobal  
 デストラクターです。  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)です。  
  
##  <a name="m_hresfinalconstruct"></a>  CComObjectGlobal::m_hResFinalConstruct  
 含まれています、`HRESULT`呼び出し元から`FinalConstruct`の構築中に、`CComObjectGlobal`オブジェクト。  
  
```
HRESULT m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>  CComObjectGlobal::QueryInterface  
 要求されたインターフェイス ポインターへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]Iid にリンクで識別されるインターフェイス ポインターへのポインターまたは**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 `QueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。  
  
##  <a name="release"></a>  CComObjectGlobal::Release  
 1 つずつ、オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**とテスト、診断に役立つ可能性のある値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、**リリース**呼び出し **_Module::Unlock**ここで、 **_Module**のグローバル インスタンスは、 [CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラス。  
  
## <a name="see-also"></a>関連項目  
 [CComObjectStack クラス](../../atl/reference/ccomobjectstack-class.md)   
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

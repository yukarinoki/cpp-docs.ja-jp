---
title: CComTearOffObject クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be47c9525098cb3bd444cefff39dbbf25b88d396
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364990"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject クラス
このクラスは、ティアオフ インターフェイスを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 ティアオフ クラスから派生`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。  
  
 ATL ティアオフ インターフェイスを実装する 2 つのフェーズで —、`CComTearOffObjectBase`メソッドは、参照カウントを処理および`QueryInterface`、中に`CComTearOffObject`実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|コンストラクターです。|  
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|参照カウントをインクリメント、`CComTearOffObject`オブジェクト。|  
|[CComTearOffObject::QueryInterface](#queryinterface)|ティアオフ クラスまたは所有者クラスのいずれかで要求されたインターフェイスへのポインターを返します。|  
|[CComTearOffObject::Release](#release)|参照カウントをデクリメント、`CComTearOffObject`オブジェクトを破棄します。|  
  
### <a name="ccomtearoffobjectbase-methods"></a>ティアオフ メソッド  
  
|||  
|-|-|  
|[ティアオフ](#ccomtearoffobjectbase)|コンストラクターです。|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>ティアオフ データ メンバー  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|ポインター、`CComObject`所有者クラスから派生します。|  
  
## <a name="remarks"></a>コメント  
 `CComTearOffObject` ティアオフ インターフェイスを実装して、そのインターフェイスが照会されたときにのみインスタンス化される個別のオブジェクトとして。 ティアオフ、参照カウントがゼロになるとは削除されます。 通常、ほとんど使用される、ティアオフ使用して、主要なオブジェクトのすべてのインスタンスで vtable ポインターを保存するためのインターフェイスのティアオフ インターフェイスを構築します。  
  
 ティアオフから実装するクラスを派生させる必要があります`CComTearOffObjectBase`およびをどのインターフェイスをサポートするティアオフ オブジェクトを指定します。 `CComTearOffObjectBase` 所有者クラスおよびスレッド モデルにテンプレート化します。 所有者のクラスは、対象のティアオフは実装されているオブジェクトのクラスです。 スレッド モデルを指定しないと、既定のスレッド モデルが使用されます。  
  
 ティアオフ クラスの COM マップを作成する必要があります。 ATL は、ティアオフをインスタンス化と、が作成されます**CComTearOffObject\<CYourTearOffClass >** または**ティアオフ\<CYourTearOffClass >** です。  
  
 たとえば、サンプルでは、ポケットベル、`CBeeper2`クラスは、ティアオフ クラスおよび`CBeeper`クラスは、所有者クラス。  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>  CComTearOffObject::AddRef  
 参照カウントをインクリメント、`CComTearOffObject`によって 1 つのオブジェクト。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断やテストに使用する値。  
  
##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject  
 コンストラクターです。  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]ポインターへのポインターに変換されますが、 **CComObject\<所有者 >** オブジェクト。  
  
### <a name="remarks"></a>コメント  
 いずれかで、所有者の参照カウントをインクリメントします。  
  
##  <a name="dtor"></a>  CComTearOffObject:: ~ CComTearOffObject  
 デストラクターです。  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放、モジュールをデクリメントし、FinalRelease を呼び出してロック カウントします。  
  
##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase  
 コンストラクターです。  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>コメント  
 初期化、 [m_pOwner](#m_powner)メンバー **NULL**です。  
  
##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner  
 ポインター、 [CComObject](../../atl/reference/ccomobject-class.md)から派生したオブジェクト*所有者*です。  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>パラメーター  
 *所有者*  
 [in]ティアオフは実装されているクラスです。  
  
### <a name="remarks"></a>コメント  
 ポインターを初期化**NULL**構築時にします。  
  
##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの IID です。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ティアオフ クラスにインターフェイスを最初に照会します。 インターフェイスがない場合、所有者オブジェクトのインターフェイスをクエリします。 要求されたインターフェイスがある場合**IUnknown**を返します、 **IUnknown**所有者のです。  
  
##  <a name="release"></a>  CComTearOffObject::Release  
 参照カウントが 1 つデクリメントし、参照カウントが 0 の場合は、削除、`CComTearOffObject`です。  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>戻り値  
 非デバッグ ビルドでは、常に 0 を返します。 デバッグ ビルドで、診断に役に立たず、テスト可能な値を返します。  
  
## <a name="see-also"></a>関連項目  
 [ティアオフ クラス](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

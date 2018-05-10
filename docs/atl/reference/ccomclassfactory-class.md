---
title: CComClassFactory クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a144f4ff9902a633933ae556df872a9d55a5409
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ccomclassfactory-class"></a>CComClassFactory クラス
このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
class CComClassFactory 
   : public IClassFactory,  
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactory::CreateInstance](#createinstance)|指定された CLSID のオブジェクトを作成します。|  
|[CComClassFactory::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|  
  
## <a name="remarks"></a>コメント  
 `CComClassFactory` 実装する、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスで、特定の CLSID のオブジェクトを作成するだけでなく、クラス ファクトリをより迅速に作成する新しいオブジェクトを許可するメモリ内のロックのメソッドが含まれます。 **IClassFactory** CLSID 割り当てるして、システム レジストリを登録するすべてのクラスに実装する必要があります。  
  
 ATL オブジェクトから派生することで、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)です。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言`CComClassFactory`既定のクラス ファクトリとして。 この既定をオーバーライドするには、いずれかを指定、 `DECLARE_CLASSFACTORY` *XXX*クラスの定義でマクロです。 たとえば、 [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex)マクロは、クラス ファクトリの指定したクラスを使用します。  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 上記のクラス定義を指定する**CMyClassFactory**オブジェクトの既定のクラス ファクトリとして使用されます。 **CMyClassFactory**から派生する必要があります`CComClassFactory`オーバーライドと`CreateInstance`です。  
  
 ATL には、クラス ファクトリを宣言するその他の 3 つのマクロが用意されています。  
  
- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)使用[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)ライセンスを作成するコントロールします。  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)使用[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)、複数のアパートメント内でオブジェクトを作成します。  
  
- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton)使用[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)を構築する 1 つ[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactory::CreateInstance  
 指定された CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkOuter`  
 [in]オブジェクトが作成されるかどうか、集計の一部として、`pUnkOuter`外部不明にする必要があります。 それ以外の場合、`pUnkOuter`する必要があります**NULL**です。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。 場合`pUnkOuter`以外**NULL**、`riid`する必要があります**IID_IUnknown**です。  
  
 `ppvObj`  
 [out]によって識別されるインターフェイス ポインターへのポインター`riid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppvObj`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="lockserver"></a>  CComClassFactory::LockServer  
 インクリメントおよびデクリメントはモジュールのロックを呼び出すことによってカウント **_Module::Lock**と **_Module::Unlock**、それぞれします。  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>パラメーター  
 `fLock`  
 [in]場合**TRUE**ロック数がインクリメントされます。 それ以外の場合、ロック カウントがデクリメントします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **_Module**のグローバル インスタンスを指す[CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラス。  
  
 呼び出す`LockServer`クライアントを複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持できます。  
  
## <a name="see-also"></a>関連項目  
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)

---
title: CComClassFactorySingleton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 754a3abd02a4a09df3e36aa9aea75c400ef00761
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360382"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton クラス
このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を 1 つのオブジェクトを構築します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 作成したクラス。  
  
 `CComClassFactorySingleton` 派生した[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を 1 つのオブジェクトを構築します。 呼び出しごとに、`CreateInstance`メソッドは、インターフェイス ポインターをこのオブジェクトを単に照会します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](#createinstance)|クエリ`m_spObj`にインターフェイス ポインター。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)によって構築されたオブジェクト`CComClassFactorySingleton`です。|  
  
## <a name="remarks"></a>コメント  
 ATL オブジェクトから派生することで、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)です。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言`CComClassFactory`既定のクラス ファクトリとして。 使用する`CComClassFactorySingleton`を指定して、 [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton)オブジェクトのクラス定義でマクロです。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance  
 呼び出し`QueryInterface`を通じて[m_spObj](#m_spobj)インターフェイス ポインターを取得します。  
  
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
  
##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj  
 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)によって構築されたオブジェクト`CComClassFactorySingleton`です。  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>コメント  
 呼び出しごとに、 [CreateInstance](#createinstance)メソッドは、インターフェイス ポインターをこのオブジェクトを単に照会します。  
  
 なおの現在のフォーム`m_spObj`方法と、重大な変更を表示する`CComClassFactorySingleton`ATL の以前のバージョンで正常に実行 以前のバージョンで、`CComClassFactorySingleton`オブジェクトは、サーバーの初期化中にクラス ファクトリと同時に作成されました。 Visual c .NET 2003年では、最初の要求で、オブジェクトが遅れて、作成します。 この変更の初期化に依存するプログラムでエラーが発生する可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 クラス](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)

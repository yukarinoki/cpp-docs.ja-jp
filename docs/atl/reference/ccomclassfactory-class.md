---
title: CComClassFactory クラス |Microsoft Docs
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
ms.openlocfilehash: ebf8112650cf1908225d0fc2c79d61d26dd606fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051010"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory クラス

このクラスは、実装、 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイス。

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
|[CComClassFactory::CreateInstance](#createinstance)|指定した CLSID のオブジェクトを作成します。|
|[CComClassFactory::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|

## <a name="remarks"></a>Remarks

`CComClassFactory` 実装して、 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスより迅速に作成する新しいオブジェクトを許可するメモリ内のクラス ファクトリをロックするほか、CLSID が特定のオブジェクトを作成するためのメソッドが含まれています。 `IClassFactory` CLSID を割り当てることをシステム レジストリに登録するすべてのクラスを実装する必要があります。

ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言する`CComClassFactory`既定のクラス ファクトリとして。 この既定の設定を無効にするには、いずれかを指定、 `DECLARE_CLASSFACTORY` *XXX*クラスの定義でマクロ。 たとえば、 [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex)マクロは、クラス ファクトリの指定したクラスを使用します。

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

上記のクラス定義を指定する`CMyClassFactory`オブジェクトの既定のクラス ファクトリとして使用されます。 `CMyClassFactory` 派生する必要があります`CComClassFactory`オーバーライドと`CreateInstance`します。

ATL には、クラス ファクトリを宣言するその他の 3 つのマクロが用意されています。

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)使用[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)ライセンスでの作成を制御します。

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)使用[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)、複数のアパートメント オブジェクトを作成します。

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton)使用[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)、1 つを構築する[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory::CreateInstance

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
[in]かどうか、オブジェクトがの作成、集計の一部として、 *pUnkOuter*不明な外部にある必要があります。 それ以外の場合、 *pUnkOuter* NULL にする必要があります。

*riid*<br/>
[in]要求されたインターフェイスの IID。 場合*pUnkOuter* NULL 以外の場合は、 *riid*あります`IID_IUnknown`します。

*ppvObj*<br/>
[out]によって識別されるインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObj* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="lockserver"></a>  CComClassFactory::LockServer

インクリメントおよびデクリメントはモジュールのロックを呼び出すことによってカウント`_Module::Lock`と`_Module::Unlock`、それぞれします。

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*群れ*<br/>
[in]TRUE の場合、ロック数がインクリメントされます。それ以外の場合、ロック数は減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

`_Module` グローバル インスタンスを指す[CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラス。

呼び出す`LockServer`により、クライアントは複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持します。

## <a name="see-also"></a>関連項目

[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)

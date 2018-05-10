---
title: CComClassFactory2 クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da2b47290d3d0be525ca65b16733c9f42835d24e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 クラス
このクラスは、実装、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class license>  
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```  
  
#### <a name="parameters"></a>パラメーター  
 *ライセンス*  
 次の静的関数を実装するクラス。  
  
- **静的な BOOL VerifyLicenseKey (BSTR** `bstr` **) です。**  
  
- **静的な BOOL GetLicenseKey (DWORD** `dwReserved` **、BSTR\***  `pBstr` **) です。**  
  
- **静的な BOOL IsLicenseValid ();**  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|指定された CLSID のオブジェクトを作成します。|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|指定したライセンス キーでは、指定された CLSID のオブジェクトを作成します。|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|クラス ファクトリのライセンス機能に関する情報を取得します。|  
|[CComClassFactory2::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|作成し、ライセンス キーを返します。|  
  
## <a name="remarks"></a>コメント  
 `CComClassFactory2` 実装する、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)拡張機能であるインターフェイスの[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)です。 **IClassFactory2**コントロール オブジェクトを介して、ライセンスを作成します。 ライセンスされたコンピューターで実行するクラス ファクトリと、実行時ライセンス キーを入力できます。 このライセンス キーには、コンピューターのフル ライセンスが存在しないときに、オブジェクトをインスタンス化するアプリケーションができます。  
  
 ATL オブジェクトから派生することで、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)です。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactory2`を指定して、 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)オブジェクトのクラス定義でマクロです。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**、テンプレート パラメーターを`CComClassFactory2`、静的関数を実装する必要があります`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`です。 単純なライセンス クラスの例を次に示します。  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2` 両方の派生**CComClassFactory2Base**と*ライセンス*です。 **CComClassFactory2Base**から派生、 **IClassFactory2**と**CComObjectRootEx\< CComGlobalsThreadModel >** です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance  
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
  
### <a name="remarks"></a>コメント  
 完全にライセンスを取得するマシンが必要です。 フル マシン ライセンスが存在しない場合は、呼び出し[取得していない](#createinstancelic)です。  
  
##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic  
 ような[CreateInstance](#createinstance)する点を除いて、`CreateInstanceLic`ライセンス キーが必要です。  
  
```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
 */,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkOuter`  
 [in]オブジェクトが作成されるかどうか、集計の一部として、`pUnkOuter`外部不明にする必要があります。 それ以外の場合、`pUnkOuter`する必要があります**NULL**です。  
  
 *pUnkReserved*  
 [in]使用しません。 必要があります**NULL**です。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。 場合`pUnkOuter`以外**NULL**、`riid`する必要があります**IID_IUnknown**です。  
  
 `bstrKey`  
 [in]ランタイム ライセンス キーが以前に取得する呼び出しから`RequestLicKey`です。 オブジェクトを作成するには、このキーが必要です。  
  
 `ppvObject`  
 [out]指定されたインターフェイス ポインターへのポインター`riid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ライセンス キーを使用して、取得することができます[RequestLicKey](#requestlickey)です。 ライセンス許諾されていないコンピューターでオブジェクトを作成するために呼び出す必要があります`CreateInstanceLic`です。  
  
##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo  
 入力、 [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590)クラス ファクトリを記述する情報を含む構造体の機能のライセンスします。  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLicInfo*  
 [out]ポインター、 **LICINFO**構造体。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 `fRuntimeKeyAvail`この構造体のメンバーができるかどうか、ライセンス キーを指定するには、クラス ファクトリ オブジェクトをライセンス許諾されていないコンピューターで作成できることを示します。 *FLicVerified*メンバーは、コンピューターのフル ライセンスが存在するかどうかを示します。  
  
##  <a name="lockserver"></a>  CComClassFactory2::LockServer  
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
  
##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey  
 作成している、ライセンス キーを返します、`fRuntimeKeyAvail`のメンバー、 [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590)構造体は、 **TRUE**です。  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwReserved`  
 [in]使用しません。 ゼロを指定してください。  
  
 `pbstrKey`  
 [out]ライセンス キーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のライセンス キーが必要[取得していない](#createinstancelic)ライセンス許諾されていないコンピューターでオブジェクトを作成します。 場合`fRuntimeKeyAvail`は**FALSE**オブジェクトが正規ライセンス版のコンピューターでのみ作成できます。  
  
 呼び出す[GetLicInfo](#getlicinfo)の値を取得する`fRuntimeKeyAvail`です。  
  
## <a name="see-also"></a>関連項目  
 [CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)

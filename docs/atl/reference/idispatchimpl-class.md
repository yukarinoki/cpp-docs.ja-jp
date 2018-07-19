---
title: IDispatchImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c30f65701aa42c3fb73a5ef544f4b4126468a29d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962580"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl クラス
既定の実装を提供します、`IDispatch`デュアル インターフェイスの一部です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0, 
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```  
  
#### <a name="parameters"></a>パラメーター  
 [in]*T*  
 デュアル インターフェイスです。  
  
 [in]*piid*  
 ポインターの IID を*T*します。  
  
 [in]*plibid*  
 インターフェイスに関する情報を格納するタイプ ライブラリの LIBID へのポインター。 既定では、サーバー レベルのタイプ ライブラリが渡されます。  
  
 [in]*wMajor*  
 タイプ ライブラリのメジャー バージョンです。 既定では、値は 1 です。  
  
 [in]*wMinor*  
 タイプ ライブラリのマイナー バージョンです。 既定では、値は 0 です。  
  
 [in]*tihclass*  
 型情報を管理するために使用するクラス*T*します。既定では、値は `CComTypeInfoHolder` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|コンストラクターです。 呼び出し`AddRef`デュアル インターフェイスの型情報を管理する、プロテクト メンバー変数にします。 このデストラクターは `Release` を呼び出します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|一連の名前を対応する一連のディスパッチ識別子に割り当てます。|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|デュアル インターフェイスの型情報を取得します。|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|デュアル インターフェイスの使用可能な型情報があるかどうかを判断します。|  
|[IDispatchImpl::Invoke](#invoke)|メソッドとデュアル インターフェイスによって公開されるプロパティへのアクセスを提供します。|  
  
## <a name="remarks"></a>Remarks  
 `IDispatchImpl` 既定の実装を提供します、`IDispatch`オブジェクトのデュアル インターフェイスの一部です。 デュアル インターフェイスから派生`IDispatch`Automation と互換性のある型のみを使用しています。 ディスパッチのようなデュアル インターフェイスには事前バインディングと遅延バインディングをサポートしていますただし、デュアル インターフェイスには、vtable のバインドもサポートしています。  
  
 次の例は、の一般的な実装を示しています。`IDispatchImpl`します。  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 既定で、`IDispatchImpl`クラスの型情報を調べ*T*レジストリにします。 未登録のインターフェイスを実装するために使用することができます、`IDispatchImpl`定義済みのバージョン番号を使用して、レジストリにアクセスしなくてもクラス。 作成する場合、`IDispatchImpl`オブジェクトの値として 0 xffff を含む*wMajor*しの値として 0 xffff *wMinor*、`IDispatchImpl`クラスの代わりに、.dll ファイルからタイプ ライブラリを取得する、レジストリ。  
  
 `IDispatchImpl` 型の静的メンバーを含む`CComTypeInfoHolder`デュアル インターフェイスの型情報を管理します。 同じデュアルを実装する複数のオブジェクトがある場合のインターフェイスを 1 つだけ`CComTypeInfoHolder`使用されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `T`  
  
 `IDispatchImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getidsofnames"></a>  IDispatchImpl::GetIDsOfNames  
 一連の名前を対応する一連のディスパッチ識別子に割り当てます。  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDispatch::GetIDsOfNames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK にします。  
  
##  <a name="gettypeinfo"></a>  IDispatchImpl::GetTypeInfo  
 デュアル インターフェイスの型情報を取得します。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[が](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfo)Windows SDK にします。  
  
##  <a name="gettypeinfocount"></a>  IDispatchImpl::GetTypeInfoCount  
 デュアル インターフェイスの使用可能な型情報があるかどうかを判断します。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください`IDispatch::GetTypeInfoCount`Windows SDK にします。  
  
##  <a name="idispatchimpl"></a>  IDispatchImpl::IDispatchImpl  
 コンストラクターです。 呼び出し`AddRef`デュアル インターフェイスの型情報を管理する、プロテクト メンバー変数にします。 このデストラクターは `Release` を呼び出します。  
  
```
IDispatchImpl();
```  
  
##  <a name="invoke"></a>  IDispatchImpl::Invoke  
 メソッドとデュアル インターフェイスによって公開されるプロパティへのアクセスを提供します。  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[idispatch::invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

---
title: IDispatchImpl クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 7fddf556eba07264f6ea0b01edea3e3d1e8a3a7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364367"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl クラス
既定の実装を提供、`IDispatch`デュアル インターフェイスの一部です。  
  
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
 [入力] `T`  
 デュアル インターフェイスです。  
  
 [入力] `piid`  
 IID へのポインター`T`です。  
  
 [入力] `plibid`  
 インターフェイスに関する情報を格納するタイプ ライブラリの LIBID へのポインター。 既定では、サーバー レベルのタイプ ライブラリが渡されます。  
  
 [入力] `wMajor`  
 タイプ ライブラリのメジャー バージョンです。 既定では、値は 1 です。  
  
 [入力] `wMinor`  
 タイプ ライブラリのマイナー バージョンです。 既定では、値は 0 です。  
  
 [入力] `tihclass`  
 型情報の管理に使用するクラス`T`です。 既定では、値は `CComTypeInfoHolder` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|コンストラクターです。 呼び出し`AddRef`デュアル インターフェイスの型情報を管理するプロテクト メンバー変数にします。 このデストラクターは `Release` を呼び出します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|一連の名前を対応する一連のディスパッチ識別子に割り当てます。|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|デュアル インターフェイスの型情報を取得します。|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|デュアル インターフェイスの使用可能な型情報があるかどうかを判断します。|  
|[IDispatchImpl::Invoke](#invoke)|デュアル インターフェイスによって公開されるプロパティおよびメソッドへのアクセスを提供します。|  
  
## <a name="remarks"></a>コメント  
 `IDispatchImpl` 既定の実装を提供、`IDispatch`オブジェクトのデュアル インターフェイスの一部です。 デュアル インターフェイス`IDispatch`オートメーションと互換性のある型のみを使用しています。 ディスパッチと同様に、デュアル インターフェイスでは、事前バインディングと遅延バインディング; がサポートしていますただし、デュアル インターフェイスは、vtable バインドもサポートします。  
  
 次の例は、の一般的な実装を示しています。`IDispatchImpl`です。  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 既定では、`IDispatchImpl`クラスの型情報を検索`T`レジストリにします。 登録されていないインターフェイスを実装するのに使用することができます、`IDispatchImpl`クラス定義済みのバージョン番号を使用して、レジストリへのアクセスがない場合。 作成する場合、`IDispatchImpl`の値として 0 xffff を持つオブジェクト`wMajor`しの値として 0 xffff `wMinor`、`IDispatchImpl`クラスは、レジストリではなく、.dll ファイルからタイプ ライブラリを取得します。  
  
 `IDispatchImpl` 型の静的メンバーを含む`CComTypeInfoHolder`デュアル インターフェイスの型情報を管理します。 同じデュアルを実装する複数のオブジェクトがある場合、インターフェイスの 1 つだけインスタンス`CComTypeInfoHolder`を使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `T`  
  
 `IDispatchImpl`  
  
## <a name="requirements"></a>要件  
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
  
### <a name="remarks"></a>コメント  
 参照してください[::getidsofnames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) Windows SDK にします。  
  
##  <a name="gettypeinfo"></a>  IDispatchImpl::GetTypeInfo  
 デュアル インターフェイスの型情報を取得します。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[が](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99)Windows SDK にします。  
  
##  <a name="gettypeinfocount"></a>  IDispatchImpl::GetTypeInfoCount  
 デュアル インターフェイスの使用可能な型情報があるかどうかを判断します。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>コメント  
 参照してください`IDispatch::GetTypeInfoCount`Windows SDK にします。  
  
##  <a name="idispatchimpl"></a>  IDispatchImpl::IDispatchImpl  
 コンストラクターです。 呼び出し`AddRef`デュアル インターフェイスの型情報を管理するプロテクト メンバー変数にします。 デストラクター**リリース**です。  
  
```
IDispatchImpl();
```  
  
##  <a name="invoke"></a>  IDispatchImpl::Invoke  
 デュアル インターフェイスによって公開されるプロパティおよびメソッドへのアクセスを提供します。  
  
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
  
### <a name="remarks"></a>コメント  
 参照してください[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

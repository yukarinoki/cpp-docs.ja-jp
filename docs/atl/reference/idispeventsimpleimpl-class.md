---
title: IDispEventSimpleImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7793262b60adbbacb2cf7b10245340790b26e805
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "42575531"
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl クラス
このクラスの実装を提供する、`IDispatch`メソッドは、タイプ ライブラリから型情報を取得せずします。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>パラメーター  
 *nID*  
 ソース オブジェクトの一意の識別子。 ときに`IDispEventSimpleImpl`基底クラスは、複合コントロールの場合は、このパラメーターの適切な包含コントロールのリソース ID を使用します。 それ以外の場合は、任意の正の整数を使用します。  
  
 *T*  
 ユーザーのクラスから派生した`IDispEventSimpleImpl`します。  
  
 *pdiid*  
 このクラスによって実装されるイベントのディスパッチ インターフェイスの IID へのポインター。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|既定のイベント ソースとの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|イベント ソースとの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|イベント ソースとの接続が中断されます。|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|E_NOTIMPL を返します。|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|E_NOTIMPL を返します。|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|E_NOTIMPL を返します。|  
|[IDispEventSimpleImpl::Invoke](#invoke)|イベント ハンドラーを呼び出しますが、イベント シンク マップに一覧表示されます。|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|既定のイベント ソースとの接続が中断されます。|  
  
## <a name="remarks"></a>Remarks  
 `IDispEventSimpleImpl` そのインターフェイスのメソッドとイベントは、すべての実装コードを指定することがなく、イベントのディスパッチ インターフェイスを実装する方法を提供します。 `IDispEventSimpleImpl` 実装を提供、`IDispatch`メソッド。 のみで処理する必要がそのイベントの実装を指定する必要があります。  
  
 `IDispEventSimpleImpl` 適切なハンドラー関数にイベントをルーティングするクラスでイベント シンク マップと連携します。 このクラスを使用します。  
  
-   追加、 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)マクロを各イベントを処理する各オブジェクトのイベント シンク マップします。  
  
-   ポインターを渡すことによって各イベントの種類の情報を指定する[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)の各エントリにパラメーターとして構造体。 X86 で、プラットフォーム、`_ATL_FUNC_INFO.cc`値は CC_CDECL を _ _stdcall のメソッドを呼び出すコールバック関数を使用する必要があります。  
  
-   呼び出す[DispEventAdvise](#dispeventadvise)をソース オブジェクトと、基底クラス間の接続を確立します。  
  
-   呼び出す[DispEventUnadvise](#dispeventunadvise)結合を解除します。  
  
 派生する必要があります`IDispEventSimpleImpl`(一意の値を使用して*nID*) の各オブジェクトのイベントを処理する必要があります。 別のソース オブジェクトに対してアドバイスを行って、1 つのソース オブジェクトに対してアドバイズで基本クラスを再利用できますが、一度に 1 つのオブジェクトで処理できるソース オブジェクトの最大数の数によって制限されます`IDispEventSimpleImpl`基本クラス。  
  
 `IDispEventSimplImpl` 同じ機能を提供します[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)を除き、型情報インターフェイスの詳細については、タイプ ライブラリから取得しません。 のみに基づいたコードが生成`IDispEventImpl`を使用することができますが、`IDispEventSimpleImpl`のコードを手動で追加しています。 使用`IDispEventSimpleImpl`ときに、イベント インターフェイスを記述するタイプ ライブラリがあるまたはタイプ ライブラリの使用に関連するオーバーヘッドを回避するしません。  
  
> [!NOTE]
> `IDispEventImpl` `IDispEventSimpleImpl`の独自の実装を提供`IUnknown::QueryInterface`それぞれを有効にする`IDispEventImpl`または`IDispEventSimpleImpl`基本クラスは、メインの COM オブジェクトのクラス メンバーへの直接アクセスを許可する一方、個別の COM id として機能します。  
  
 ActiveX イベント シンクのみサポートの戻り値の HRESULT 型または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
 詳細については、次を参照してください。 [IDispEventImpl のサポート](../../atl/supporting-idispeventimpl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="advise"></a>  IDispEventSimpleImpl::Advise  
 によって表される、イベント ソースと接続を確立するには、このメソッドを呼び出す*pUnk*します。  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、`IUnknown`イベント ソース オブジェクトのインターフェイス。  
  
### <a name="return-value"></a>戻り値  
 S_OK または任意の失敗 HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 イベントが発生した接続が確立されると、 *pUnk*イベント シンク マップを使用して、クラス内のハンドラーにルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスを使用して、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `Advise` 接続を確立によって決定されるオブジェクトの既定のイベント ソースの IID を取得する既定のイベント ソースが[AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)します。  
  
##  <a name="dispeventadvise"></a>  IDispEventSimpleImpl::DispEventAdvise  
 によって表される、イベント ソースと接続を確立するには、このメソッドを呼び出す*pUnk*します。  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、`IUnknown`イベント ソース オブジェクトのインターフェイス。  
  
 *piid*  
 イベント ソース オブジェクトの IID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 S_OK または任意の失敗 HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 イベントの発生後、 *pUnk*イベント シンク マップを使用して、クラス内のハンドラーにルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスを使用して、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `DispEventAdvise` 指定されたイベント ソースとの接続を確立`pdiid`します。  
  
##  <a name="dispeventunadvise"></a>  IDispEventSimpleImpl::DispEventUnadvise  
 によって表される、イベント ソースとの接続を解除*pUnk*します。  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、`IUnknown`イベント ソース オブジェクトのインターフェイス。  
  
 *piid*  
 イベント ソース オブジェクトの IID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 S_OK または任意の失敗 HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 接続が壊れていると、イベントは不要になったイベント シンク マップのハンドラー関数にルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスを使用して、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `DispEventAdvise` 指定されたイベント ソースによって確立された接続が切断`pdiid`します。  
  
##  <a name="getidsofnames"></a>  IDispEventSimpleImpl::GetIDsOfNames  
 この実装の`IDispatch::GetIDsOfNames`E_NOTIMPL を返します。  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDispatch::GetIDsOfNames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK にします。  
  
##  <a name="gettypeinfo"></a>  IDispEventSimpleImpl::GetTypeInfo  
 この実装の`IDispatch::GetTypeInfo`E_NOTIMPL を返します。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[が](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfo)Windows SDK にします。  
  
##  <a name="gettypeinfocount"></a>  IDispEventSimpleImpl::GetTypeInfoCount  
 この実装の`IDispatch::GetTypeInfoCount`E_NOTIMPL を返します。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDispatch::GetTypeInfoCount](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK にします。  
  
##  <a name="invoke"></a>  IDispEventSimpleImpl::Invoke  
 この実装の`IDispatch::Invoke`イベント シンク マップに一覧表示、イベント ハンドラーの呼び出し。  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[idispatch::invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)します。  
  
##  <a name="unadvise"></a>  IDispEventSimpleImpl::Unadvise  
 によって表される、イベント ソースとの接続を解除*pUnk*します。  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、`IUnknown`イベント ソース オブジェクトのインターフェイス。  
  
### <a name="return-value"></a>戻り値  
 S_OK または任意の失敗 HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 接続が壊れていると、イベントは不要になったイベント シンク マップのハンドラー関数にルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスを使用して、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `Unadvise` 指定された既定のイベント ソースによって確立された接続が切断`pdiid`します。  
  
 `Unavise` によって決定されるオブジェクトの既定のイベント ソースの IID を取得、既定のイベント ソースとの接続を区切り、 [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_FUNC_INFO 構造体](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl クラス](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [クラスの概要](../../atl/atl-class-overview.md)

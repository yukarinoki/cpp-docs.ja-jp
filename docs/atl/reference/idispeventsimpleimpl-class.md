---
title: されますクラス |Microsoft ドキュメント
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
ms.openlocfilehash: 89f565c1e32f1208fbb039321d26b9175596d57e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365995"
---
# <a name="idispeventsimpleimpl-class"></a>されますクラス
このクラスの実装を提供する、`IDispatch`メソッド、せず、タイプ ライブラリから型情報を取得します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>パラメーター  
 `nID`  
 ソース オブジェクトの一意の識別子。 ときに`IDispEventSimpleImpl`基底クラスは、複合コントロールの場合は、このパラメーターに、目的のコンテナー内のコントロールのリソース ID を使用します。 それ以外の場合では、任意の正の整数を使用します。  
  
 `T`  
 派生したユーザーのクラスは、`IDispEventSimpleImpl`です。  
  
 `pdiid`  
 このクラスで実装するイベントのディスパッチ インターフェイスの IID へのポインター。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|既定のイベント ソースとの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|イベント ソースとの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|イベント ソースとの接続が中断されます。|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|返します**E_NOTIMPL**です。|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|返します**E_NOTIMPL**です。|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|返します**E_NOTIMPL**です。|  
|[IDispEventSimpleImpl::Invoke](#invoke)|イベント ハンドラーを呼び出しますが、イベント シンク マップに一覧表示されます。|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|既定のイベント ソースとの接続が中断されます。|  
  
## <a name="remarks"></a>コメント  
 `IDispEventSimpleImpl` そのインターフェイスのメソッドとイベントは、すべての実装コードを指定しなくても、イベントのディスパッチ インターフェイスを実装する方法を提供します。 `IDispEventSimpleImpl` 実装を提供、`IDispatch`メソッドです。 ある処理の対象イベントの実装を指定する必要があるだけです。  
  
 `IDispEventSimpleImpl` 適切なハンドラー関数にイベントをルーティングするクラスでイベント シンク マップと連携して動作します。 このクラスを使用します。  
  
-   追加、 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)マクロを処理する各オブジェクト上の各イベントのイベント シンク マップします。  
  
-   ポインターを渡すことによって各イベントの種類の情報を指定、 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)の各エントリにパラメーターとして構造体。 X86 で、プラットフォーム、`_ATL_FUNC_INFO.cc`値は CC_CDECL を _ _stdcall のメソッドを呼び出すと、コールバック関数である必要があります。  
  
-   呼び出す[DispEventAdvise](#dispeventadvise)基本クラスとソース オブジェクトの間の接続を確立するためにします。  
  
-   呼び出す[DispEventUnadvise](#dispeventunadvise)への接続を切断します。  
  
 派生する必要があります`IDispEventSimpleImpl`(に一意の値を使用して`nID`) の各オブジェクトのイベントを処理する必要があります。 によって、別のソース オブジェクトに対して通知し、1 つのソース オブジェクトに対してアドバイズ基底クラスを再利用できますが、一度に 1 つのオブジェクトを処理するソース オブジェクトの最大数が数によって制限される`IDispEventSimpleImpl`基本クラスです。  
  
 **IDispEventSimplImpl**と同じ機能を提供[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)、タイプ ライブラリからインターフェイスに関する型情報を取得しません。 のみに基づいたコードが生成`IDispEventImpl`、使用することができますが、`IDispEventSimpleImpl`コードを手動で追加することで。 使用する`IDispEventSimpleImpl`としないイベント インターフェイスを記述するタイプ ライブラリがあるかをタイプ ライブラリの使用に関連するオーバーヘッドを回避します。  
  
> [!NOTE]
> `IDispEventImpl` および`IDispEventSimpleImpl`の独自の実装を提供**iunknown::queryinterface**それぞれを有効にする`IDispEventImpl`または`IDispEventSimpleImpl`基底クラスのメンバーに直接アクセスを許可する一方、個別の COM id として機能するクラスメインの COM オブジェクト。  
  
 ActiveX イベント シンクのみサポートしている戻り値の型 HRESULT または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
 詳細については、次を参照してください。[サポート IDispEventImpl](../../atl/supporting-idispeventimpl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="advise"></a>  IDispEventSimpleImpl::Advise  
 によって表されるイベント ソースに接続を確立するには、このメソッドを呼び出す*pUnk*です。  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` または、エラーをすべて`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 イベントが発生した接続が確立されると、 *pUnk*イベント シンク マップを使用して、クラス内のハンドラーにルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスと、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `Advise` 接続を確立の既定のイベント ソースに定めるところによるオブジェクトの既定のイベント ソースの IID を取得[AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)です。  
  
##  <a name="dispeventadvise"></a>  IDispEventSimpleImpl::DispEventAdvise  
 によって表されるイベント ソースに接続を確立するには、このメソッドを呼び出す*pUnk*です。  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
 `piid`  
 イベント ソース オブジェクトの IID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` または、エラーをすべて`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 イベントが発生した後で、 *pUnk*イベント シンク マップを使用して、クラス内のハンドラーにルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスと、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `DispEventAdvise` 指定されたイベント ソースとの接続を確立`pdiid`です。  
  
##  <a name="dispeventunadvise"></a>  IDispEventSimpleImpl::DispEventUnadvise  
 によって表されるイベント ソースに、接続が切断*pUnk*です。  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
 `piid`  
 イベント ソース オブジェクトの IID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` または、エラーをすべて`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 接続が壊れていると、イベントはイベント シンク マップされているハンドラー関数にはルーティング不要になった。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスと、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `DispEventAdvise` 指定されたイベント ソースによって確立された接続が切断`pdiid`です。  
  
##  <a name="getidsofnames"></a>  IDispEventSimpleImpl::GetIDsOfNames  
 この実装 **::getidsofnames**返します**E_NOTIMPL**です。  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[::getidsofnames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) Windows SDK にします。  
  
##  <a name="gettypeinfo"></a>  IDispEventSimpleImpl::GetTypeInfo  
 この実装**が**返します**E_NOTIMPL**です。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[が](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99)Windows SDK にします。  
  
##  <a name="gettypeinfocount"></a>  IDispEventSimpleImpl::GetTypeInfoCount  
 この実装**IDispatch::GetTypeInfoCount**返します**E_NOTIMPL**です。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) Windows SDK にします。  
  
##  <a name="invoke"></a>  IDispEventSimpleImpl::Invoke  
 この実装**idispatch::invoke**イベント シンク マップに一覧表示、イベント ハンドラーの呼び出しです。  
  
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
  
### <a name="remarks"></a>コメント  
 参照してください[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)です。  
  
##  <a name="unadvise"></a>  IDispEventSimpleImpl::Unadvise  
 によって表されるイベント ソースに、接続が切断*pUnk*です。  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` または、エラーをすべて`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 接続が壊れていると、イベントはイベント シンク マップされているハンドラー関数にはルーティング不要になった。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスと、呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `Unadvise` 指定された既定のイベント ソースによって確立された接続が切断`pdiid`です。  
  
 **Unavise**によって決定されるオブジェクトの既定のイベント ソースの IID を取得、既定のイベント ソースとの接続を区切り、 [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)です。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_FUNC_INFO 構造体](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl クラス](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [クラスの概要](../../atl/atl-class-overview.md)

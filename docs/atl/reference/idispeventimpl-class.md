---
title: IDispEventImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7809a61fe39a4b4b913531de29e03c3eb440c418
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="idispeventimpl-class"></a>IDispEventImpl クラス
このクラスの実装を提供する、`IDispatch`メソッドです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```  
  
#### <a name="parameters"></a>パラメーター  
 `nID`  
 ソース オブジェクトの一意の識別子。 ときに`IDispEventImpl`基底クラスは、複合コントロールの場合は、このパラメーターに、目的のコンテナー内のコントロールのリソース ID を使用します。 それ以外の場合では、任意の正の整数を使用します。  
  
 `T`  
 派生したユーザーのクラスは、`IDispEventImpl`です。  
  
 `pdiid`  
 このクラスで実装するイベントのディスパッチ インターフェイスの IID へのポインター。 示されるタイプ ライブラリのこのインターフェイスを定義する必要があります`plibid`、 `wMajor`、および`wMinor`です。  
  
 `plibid`  
 ディスパッチ インターフェイスを定義するタイプ ライブラリへのポインターが指す`pdiid`です。 場合 **& GUID_** イベントのソース オブジェクトから、タイプ ライブラリが読み込まれます。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョンです。 既定値は 0 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。  
  
 `tihclass`  
 型情報の管理に使用するクラス`T`です。 既定値は型のクラス`CComTypeInfoHolder`。 ただし、このテンプレート パラメーターを上書きするには、以外の値の型のクラスを提供して`CComTypeInfoHolder`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|型情報の管理に使用するクラス。 既定では、`CComTypeInfoHolder`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|指定したディスパッチ識別子に関数のインデックスを検索します。|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|対応する一連の整数 Dispid を 1 つのメンバーとオプションの引数名のセットをマップします。|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|オブジェクトの型情報を取得します。|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|型情報インターフェイスの数を取得します。|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|ユーザー定義型の基本の種類を取得します。|  
  
## <a name="remarks"></a>コメント  
 `IDispEventImpl` そのインターフェイスのメソッドとイベントは、すべての実装コードを指定しなくても、イベントのディスパッチ インターフェイスを実装する方法を提供します。 `IDispEventImpl` 実装を提供、`IDispatch`メソッドです。 ある処理の対象イベントの実装を指定する必要があるだけです。  
  
 `IDispEventImpl` 適切なハンドラー関数にイベントをルーティングするクラスでイベント シンク マップと連携して動作します。 このクラスを使用します。  
  

 追加、 [SINK_ENTRY](composite-control-macros.md#sink_entry)または[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)マクロを処理する各オブジェクト上の各イベントのイベント シンク マップします。 使用する場合`IDispEventImpl`複合コントロールの基底クラスとして呼び出すことができます[AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap)を確立し、イベント シンク マップのすべてのエントリのイベント ソースとの接続を解除します。 その他の場合、またはより細かく制御には、呼び出す[DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise)基本クラスとソース オブジェクトの間の接続を確立するためにします。 呼び出す[DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)への接続を切断します。  

  
 派生する必要があります`IDispEventImpl`(に一意の値を使用して`nID`) の各オブジェクトのイベントを処理する必要があります。 によって、別のソース オブジェクトに対して通知し、1 つのソース オブジェクトに対してアドバイズ基底クラスを再利用できますが、一度に 1 つのオブジェクトを処理するソース オブジェクトの最大数が数によって制限される`IDispEventImpl`基本クラスです。  
  
 `IDispEventImpl` 同じ機能を提供します[されます](../../atl/reference/idispeventsimpleimpl-class.md)インターフェイスに関する型情報へのポインターとして指定されたことをことのではなく、タイプ ライブラリから取得を除き、 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)構造体。 使用して`IDispEventSimpleImpl`ときに、イベント インターフェイスを記述するタイプ ライブラリがあるまたはしないタイプ ライブラリの使用に関連するオーバーヘッドを回避します。  
  
> [!NOTE]
> `IDispEventImpl` および`IDispEventSimpleImpl`の独自の実装を提供**iunknown::queryinterface**それぞれを有効にする`IDispEventImpl`と`IDispEventSimpleImpl`基底クラスのメンバーに直接アクセスを許可する一方、個別の COM id として機能するクラスメインの COM オブジェクト。  
  
 ActiveX イベント シンクのみサポートしている戻り値の型 HRESULT または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
 詳細については、次を参照してください。[サポート IDispEventImpl](../../atl/supporting-idispeventimpl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getfuncinfofromid"></a>  IDispEventImpl::GetFuncInfoFromId  
 指定したディスパッチ識別子に関数のインデックスを検索します。  
  
```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]関数の ID への参照。  
  
 *dispidMember*  
 [in]関数のディスパッチ ID。  
  
 `lcid`  
 [in]関数の ID のロケール コンテキスト  
  
 `info`  
 [in]関数を呼び出す方法を示す構造体。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="getidsofnames"></a>  IDispEventImpl::GetIDsOfNames  
 対応する一連の整数への後続の呼び出しで使用できる Dispid を 1 つのメンバーとオプションの引数名のセットをマップ[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)です。  
  
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
  
##  <a name="gettypeinfo"></a>  IDispEventImpl::GetTypeInfo  
 オブジェクトの型情報を取得します。この型情報を使用して、インターフェイスの型情報を取得できます。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettypeinfocount"></a>  IDispEventImpl::GetTypeInfoCount  
 オブジェクトが提供する型情報インターフェイスの数 (0 または 1) を取得します。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) Windows SDK にします。  
  
##  <a name="getuserdefinedtype"></a>  IDispEventImpl::GetUserDefinedType  
 ユーザー定義型の基本の種類を取得します。  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTI`  
 [in]ポインター、 [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680)ユーザー定義型を含むインターフェイス。  
  
 *hrt*  
 [in]取得する型の説明へのハンドル。  
  
### <a name="return-value"></a>戻り値  
 バリアント型の型。  
  
### <a name="remarks"></a>コメント  
 参照してください[ITypeInfo::GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00)です。  
  
##  <a name="idispeventimpl"></a>  IDispEventImpl::IDispEventImpl  
 コンストラクターです。 クラス テンプレート パラメーターの値を格納`plibid`、 `pdiid`、 `wMajor`、および`wMinor`です。  
  
```
IDispEventImpl();
```  
  
##  <a name="tihclass"></a>  IDispEventImpl::tihclass  
 この typedef は、クラス テンプレート パラメーターのインスタンスを`tihclass`です。  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>コメント  
 クラスは、既定では、`CComTypeInfoHolder`です。 `CComTypeInfoHolder` クラスの型情報を管理します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_FUNC_INFO 構造体](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)   
 [されますクラス](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](composite-control-macros.md#sink_entry)   
 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [クラスの概要](../../atl/atl-class-overview.md)
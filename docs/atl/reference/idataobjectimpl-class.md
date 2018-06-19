---
title: IDataObjectImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3ffcdd8cc8320b2534d928171fe75619062b300
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365482"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl クラス
このクラスは、汎用データ転送をサポートして、接続を管理するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IDataObjectImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|データ オブジェクトとアドバイズ シンク間の接続を確立します。 これにより、オブジェクトの変更の通知を受信するアドバイズ シンク。|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|以前に確立された接続が終了した`DAdvise`です。|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|現在のアドバイザリ コネクションを反復処理する列挙子を作成します。|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|反復処理する列挙子を作成、 **FORMATETC**データ オブジェクトでサポートされている構造体。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|各アドバイズ シンクに戻るには、変更通知を送信します。|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|論理的に等しい**FORMATETC**はより複雑な構造です。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IDataObjectImpl::GetData](#getdata)|データ オブジェクトからクライアントにデータを転送します。 データについては、「、 **FORMATETC**構造体し、を介して転送、 **STGMEDIUM**構造体。|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|ような`GetData`を除き、クライアントを割り当てる必要があります、 **STGMEDIUM**構造体。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|データ オブジェクトが、特定をサポートするかどうかを決定**FORMATETC**データを転送するための構造体。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IDataObjectImpl::SetData](#setdata)|クライアントからのデータ オブジェクトにデータを転送します。 ATL の実装を返します**E_NOTIMPL**です。|  
  
## <a name="remarks"></a>コメント  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)インターフェイスには、汎用データ転送をサポートするメソッドが用意されています。 `IDataObject` 標準の形式構造を使用して[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)と[STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を取得し、データを格納します。  
  
 `IDataObject` また、アドバイズ シンク データ変更の通知を処理するへの接続を管理します。 クライアントがデータ オブジェクトからデータ変更の通知を受信するためには、クライアントを実装する必要があります、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)アドバイズ シンクと呼ばれるオブジェクトのインターフェイスです。 ときに、クライアントは、 **IDataObject::DAdvise**、データ オブジェクトとアドバイズ シンク間の接続が確立します。  
  
 クラス`IDataObjectImpl`の既定の実装を提供`IDataObject`を実装して**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise  
 データ オブジェクトとアドバイズ シンク間の接続を確立します。  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>コメント  
 これにより、オブジェクトの変更の通知を受信するアドバイズ シンク。  
  
 接続を終了するには、呼び出す[に](#dunadvise)です。  
  
 参照してください[IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) Windows SDK にします。  
  
##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise  
 以前に確立された接続が終了した[DAdvise](#dadvise)です。  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) Windows SDK にします。  
  
##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise  
 現在のアドバイザリ コネクションを反復処理する列挙子を作成します。  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) Windows SDK にします。  
  
##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc  
 反復処理する列挙子を作成、 **FORMATETC**データ オブジェクトでサポートされている構造体。  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange  
 現在管理されている各アドバイズ シンクに戻るには、変更通知を送信します。  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc  
 論理的に等しい**FORMATETC**はより複雑な構造です。  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) Windows SDK にします。  
  
##  <a name="getdata"></a>  IDataObjectImpl::GetData  
 データ オブジェクトからクライアントにデータを転送します。  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>コメント  
 *PformatetcIn*パラメーターがのストレージ メディアの種類を指定する必要があります**TYMED_MFPICT**です。  
  
 参照してください[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK にします。  
  
##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere  
 ような`GetData`を除き、クライアントを割り当てる必要があります、 **STGMEDIUM**構造体。  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) Windows SDK にします。  
  
##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData  
 データ オブジェクトが、特定をサポートするかどうかを決定**FORMATETC**データを転送するための構造体。  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) Windows SDK にします。  
  
##  <a name="setdata"></a>  IDataObjectImpl::SetData  
 クライアントからのデータ オブジェクトにデータを転送します。  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

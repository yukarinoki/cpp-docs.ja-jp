---
title: IDataObjectImpl クラス |Microsoft Docs
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
ms.openlocfilehash: ef7db05e8e8eb0a723354bcd6f53fb283aebe0c8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880886"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl クラス
このクラスは、汎用データ転送をサポートしていると、接続を管理するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IDataObjectImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|データ オブジェクトとアドバイズ シンク間の接続を確立します。 これにより、オブジェクトの変更の通知を受信するアドバイズ シンクができます。|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|以前に確立した接続が終了した`DAdvise`します。|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|現在のアドバイザリ コネクションを反復処理する列挙子を作成します。|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|反復処理する列挙子を作成、`FORMATETC`データ オブジェクトでサポートされている構造体。 ATL の実装では、E_NOTIMPL を返します。|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|各アドバイズ シンクに戻るには、変更通知を送信します。|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|論理的に等価な取得`FORMATETC`はより複雑な構造体。 ATL の実装では、E_NOTIMPL を返します。|  
|[IDataObjectImpl::GetData](#getdata)|データ オブジェクトからクライアントにデータを転送します。 データが記載されて、`FORMATETC`を介して転送は、構造体であり、`STGMEDIUM`構造体。|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|ような`GetData`を除き、クライアントを割り当てる必要があります、`STGMEDIUM`構造体。 ATL の実装では、E_NOTIMPL を返します。|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|データ オブジェクトが特定をサポートするかどうかを決定`FORMATETC`データを転送するための構造体。 ATL の実装では、E_NOTIMPL を返します。|  
|[IDataObjectImpl::SetData](#setdata)|データ オブジェクトに、クライアントからのデータを転送します。 ATL の実装では、E_NOTIMPL を返します。|  
  
## <a name="remarks"></a>Remarks  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)インターフェイスには、汎用データ転送をサポートするメソッドが用意されています。 `IDataObject` 標準の形式の構造を使用して[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)と[STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を取得し、データを格納します。  
  
 `IDataObject` アドバイズ シンクがデータ変更の通知を処理するためにへの接続を管理します。 クライアントがデータ オブジェクトからデータ変更の通知を受信するためには、クライアントを実装する必要があります、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)アドバイズ シンクと呼ばれるオブジェクトのインターフェイス。 クライアントが、呼び出すと`IDataObject::DAdvise`、データ オブジェクトとアドバイズ シンクの間の接続が確立されています。  
  
 クラス`IDataObjectImpl`の既定の実装を提供します。`IDataObject`実装と`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>必要条件  
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
  
### <a name="remarks"></a>Remarks  
 これにより、オブジェクトの変更の通知を受信するアドバイズ シンクができます。  
  
 接続を終了するには、呼び出す[に](#dunadvise)します。  
  
 参照してください[IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) Windows SDK にします。  
  
##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise  
 以前に確立した接続が終了した[DAdvise](#dadvise)します。  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Remarks  
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
  
### <a name="remarks"></a>Remarks  
 参照してください[IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) Windows SDK にします。  
  
##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc  
 反復処理する列挙子を作成、`FORMATETC`データ オブジェクトでサポートされている構造体。  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange  
 現在管理されている各アドバイズ シンクに戻るには、変更通知を送信します。  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc  
 論理的に等価な取得`FORMATETC`はより複雑な構造体。  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) Windows SDK にします。  
  
##  <a name="getdata"></a>  IDataObjectImpl::GetData  
 データ オブジェクトからクライアントにデータを転送します。  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Remarks  
 *PformatetcIn*パラメーター TYMED_MFPICT のストレージ メディアの種類を指定する必要があります。  
  
 参照してください[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK にします。  
  
##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere  
 ような`GetData`を除き、クライアントを割り当てる必要があります、`STGMEDIUM`構造体。  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) Windows SDK にします。  
  
##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData  
 データ オブジェクトが特定をサポートするかどうかを決定`FORMATETC`データを転送するための構造体。  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) Windows SDK にします。  
  
##  <a name="setdata"></a>  IDataObjectImpl::SetData  
 データ オブジェクトに、クライアントからのデータを転送します。  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

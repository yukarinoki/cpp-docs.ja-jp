---
title: IErrorRecordsImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
- IErrorRecordsImpl::GetErrorParameters
- ATL.IErrorRecordsImpl.GetErrorParameters
- IErrorRecordsImpl.GetErrorParameters
- GetErrorParameters
- ATL::IErrorRecordsImpl::GetErrorParameters
- IErrorRecordsImpl::GetRecordCount
- ATL::IErrorRecordsImpl::GetRecordCount
- IErrorRecordsImpl.GetRecordCount
- ATL.IErrorRecordsImpl.GetRecordCount
- IErrorRecordsImpl::m_rgErrors
- IErrorRecordsImpl.m_rgErrors
- ATL.IErrorRecordsImpl.m_rgErrors
- m_rgErrors
- ATL::IErrorRecordsImpl::m_rgErrors
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
- GetErrorDescriptionString method
- GetErrorGUID method
- GetErrorHelpContext method
- GetErrorHelpFile method
- GetErrorSource method
- AddErrorRecord method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetRecordCount method
- m_rgErrors
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26d443aaa5a160968a461bbdb81444f5a9f097c9
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084088"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl クラス

OLE DB 実装[IErrorRecords](/previous-versions/windows/desktop/ms718112)インターフェイスにレコードを追加して、データ メンバーからレコードを取得する ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) 型の**CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
### <a name="parameters"></a>パラメーター  

*T*<br/>
派生したクラス`IErrorRecordsImpl`します。  
  
*RecordClass*<br/>
OLE DB エラー オブジェクトを表すクラス。  

## <a name="requirements"></a>要件  

**ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetErrorDescriptionString](#geterrordescriptionstring)|エラー レコードからエラーを説明する文字列を取得します。|  
|[GetErrorGUID](#geterrorguid)|エラー レコードからエラー GUID を取得します。|  
|[GetErrorHelpContext](#geterrorhelpcontext)|エラー レコードからのヘルプ コンテキスト ID を取得します。|  
|[GetErrorHelpFile](#geterrorhelpfile)|エラー レコードからヘルプ ファイルの完全なパス名を取得します。|  
|[GetErrorSource](#geterrorsource)|エラー レコードからのエラーのソース コードを取得します。|  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[AddErrorRecord](#adderrorrecord)|OLE DB エラー オブジェクトには、レコードを追加します。|  
|[GetBasicErrorInfo](#getbasicerrorinfo)|リターン コードとプロバイダー固有のエラー数など、エラーに関する基本情報を返します。|  
|[GetCustomErrorObject](#getcustomerrorobject)|カスタム エラー オブジェクトのインターフェイスへのポインターを返します。|  
|[GetErrorInfo](#geterrorinfo)|返します、 [IErrorInfo](/previous-versions/windows/desktop/ms718112)指定されたレコードのインターフェイス ポインター。|  
|[GetErrorParameters](#geterrorparameters)|エラー パラメーターを返します。|  
|[GetRecordCount](#getrecordcount)|OLE DB レコード オブジェクト内のレコードの数を返します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_rgErrors](#rgerrors)|エラー レコードの配列。|  

## <a name="geterrordescriptionstring"></a> Ierrorrecordsimpl::geterrordescriptionstring

エラー レコードからエラーを説明する文字列を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>パラメーター  

*rCurError*<br/>
`ERRORINFO`でレコードを`IErrorInfo`インターフェイス。  
  
### <a name="return-value"></a>戻り値  

エラーを説明する文字列へのポインター。  
  
## <a name="geterrorguid"></a> Ierrorrecordsimpl::geterrorguid

エラー レコードからエラー GUID を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>パラメーター  

*rCurError*<br/>
`ERRORINFO`でレコードを`IErrorInfo`インターフェイス。  
  
### <a name="return-value"></a>戻り値  

エラーの GUID への参照。  

## <a name="geterrorhelpcontext"></a> Ierrorrecordsimpl::geterrorhelpcontext

エラー レコードからのヘルプ コンテキスト ID を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>パラメーター  

*rCurError*<br/>
`ERRORINFO`でレコードを`IErrorInfo`インターフェイス。  
  
### <a name="return-value"></a>戻り値  

エラーのヘルプ コンテキスト ID。  

## <a name="geterrorhelpfile"></a> Ierrorrecordsimpl::geterrorhelpfile

エラー レコードからヘルプ ファイルのパス名を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>パラメーター  

*rCurError*<br/>
`ERRORINFO`でレコードを`IErrorInfo`インターフェイス。  
  
### <a name="return-value"></a>戻り値  

エラーのヘルプ ファイルのパス名を含む文字列へのポインター。

## <a name="geterrorsource"></a> Ierrorrecordsimpl::geterrorsource

エラー レコードから、エラーの原因となったソース コードを取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>パラメーター  

*rCurError*<br/>
`ERRORINFO`でレコードを`IErrorInfo`インターフェイス。  
  
### <a name="return-value"></a>戻り値  

エラーのソース コードを含む文字列へのポインター。 

## <a name="adderrorrecord"></a> Ierrorrecordsimpl::adderrorrecord

OLE DB エラー オブジェクトには、レコードを追加します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID);  
```  
  
#### <a name="parameters"></a>パラメーター  

参照してください[IErrorRecords::AddErrorRecord](/previous-versions/windows/desktop/ms725362)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="getbasicerrorinfo"></a> Ierrorrecordsimpl::getbasicerrorinfo

リターン コードとプロバイダー固有のエラー数など、エラーに関する基本情報を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo);  
```  
  
#### <a name="parameters"></a>パラメーター  

参照してください[IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907)で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="getcustomerrorobject"></a> Ierrorrecordsimpl::getcustomerrorobject

カスタム エラー オブジェクトのインターフェイスへのポインターを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>パラメーター  

参照してください[IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="geterrorinfo"></a> Ierrorrecordsimpl::geterrorinfo

返します、 [IErrorInfo](/previous-versions/windows/desktop/ms718112)指定されたレコードのインターフェイス ポインター。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,  
   LCID lcid,  
   IErrorInfo **ppErrorInfo);  
```  
  
#### <a name="parameters"></a>パラメーター  

参照してください[IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230)で、 *OLE DB プログラマーズ リファレンス*します。

## <a name="geterrorparameters"></a> Ierrorrecordsimpl::geterrorparameters

エラー パラメーターを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,  
   DISPPARAMS *pdispparams);  
```  
  
#### <a name="parameters"></a>パラメーター  

参照してください[IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="getrecordcount"></a> Ierrorrecordsimpl::getrecordcount

OLE DB レコード オブジェクト内のレコードの数を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);  
```  
  
#### <a name="parameters"></a>パラメーター  

参照してください[IErrorRecords::GetRecordCount](/previous-versions/windows/desktop/ms722724)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="rgerrors"></a> Ierrorrecordsimpl::m_rgerrors

エラー レコードの配列。  
  
### <a name="syntax"></a>構文  
  
```cpp
CAtlArray< RecordClass > m_rgErrors;  
```  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
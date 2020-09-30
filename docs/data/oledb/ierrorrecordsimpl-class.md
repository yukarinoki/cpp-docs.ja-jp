---
title: IErrorRecordsImpl クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: cb0e236a31846e3465d76b6904a7b4c57a2b8cf4
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508994"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl クラス

OLE DB [Ierrorrecords](/previous-versions/windows/desktop/ms718112(v=vs.85))インターフェイスを実装し、 **CAtlArray<** 型のデータメンバー ([m_rgErrors](#rgerrors)) にレコードを追加して、レコードを取得し `RecordClass` **>** ます。

## <a name="syntax"></a>構文

```cpp
template <class T, class RecordClass = ATLERRORINFO>
class IErrorRecordsImpl : public IErrorRecords
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IErrorRecordsImpl` 。

*RecordClass*<br/>
OLE DB エラーオブジェクトを表すクラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[GetErrorDescriptionString](#geterrordescriptionstring)|エラーレコードからエラー説明文字列を取得します。|
|[GetErrorGUID](#geterrorguid)|エラーの GUID をエラーレコードから取得します。|
|[GetErrorHelpContext](#geterrorhelpcontext)|エラーレコードからヘルプコンテキスト ID を取得します。|
|[GetErrorHelpFile](#geterrorhelpfile)|エラーレコードからヘルプファイルの完全なパス名を取得します。|
|[GetErrorSource](#geterrorsource)|エラーレコードからエラーソースコードを取得します。|

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[AddErrorRecord](#adderrorrecord)|OLE DB error オブジェクトにレコードを追加します。|
|[GetBasicErrorInfo](#getbasicerrorinfo)|リターンコードやプロバイダー固有のエラー番号など、エラーに関する基本的な情報を返します。|
|[GetCustomErrorObject](#getcustomerrorobject)|カスタムエラーオブジェクトのインターフェイスへのポインターを返します。|
|[GetErrorInfo](#geterrorinfo)|指定されたレコードの [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) インターフェイスポインターを返します。|
|[GetErrorParameters](#geterrorparameters)|エラーパラメーターを返します。|
|[GetRecordCount](#getrecordcount)|OLE DB レコードオブジェクト内のレコードの数を返します。|

### <a name="data-members"></a>データ メンバー

| 名前 | 説明 |
|-|-|
|[m_rgErrors](#rgerrors)|エラーレコードの配列。|

## <a name="ierrorrecordsimplgeterrordescriptionstring"></a><a name="geterrordescriptionstring"></a> Ierrorrecordシム Pl:: GetErrorDescriptionString

エラーレコードからエラー説明文字列を取得します。

### <a name="syntax"></a>構文

```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>パラメーター

*rCurError*<br/>
`ERRORINFO`インターフェイス内のレコード `IErrorInfo` 。

### <a name="return-value"></a>戻り値

エラーを説明する文字列へのポインター。

## <a name="ierrorrecordsimplgeterrorguid"></a><a name="geterrorguid"></a> Ierrorrecordシム Pl:: GetErrorGUID

エラーの GUID をエラーレコードから取得します。

### <a name="syntax"></a>構文

```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>パラメーター

*rCurError*<br/>
`ERRORINFO`インターフェイス内のレコード `IErrorInfo` 。

### <a name="return-value"></a>戻り値

エラーの GUID への参照。

## <a name="ierrorrecordsimplgeterrorhelpcontext"></a><a name="geterrorhelpcontext"></a> Ierrorrecordシム Pl:: GetErrorHelpContext

エラーレコードからヘルプコンテキスト ID を取得します。

### <a name="syntax"></a>構文

```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>パラメーター

*rCurError*<br/>
`ERRORINFO`インターフェイス内のレコード `IErrorInfo` 。

### <a name="return-value"></a>戻り値

エラーのヘルプコンテキスト ID。

## <a name="ierrorrecordsimplgeterrorhelpfile"></a><a name="geterrorhelpfile"></a> Ierrorrecordシム Pl:: GetErrorHelpFile

エラーレコードからヘルプファイルのパス名を取得します。

### <a name="syntax"></a>構文

```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>パラメーター

*rCurError*<br/>
`ERRORINFO`インターフェイス内のレコード `IErrorInfo` 。

### <a name="return-value"></a>戻り値

エラーのヘルプファイルのパス名を含む文字列へのポインター。

## <a name="ierrorrecordsimplgeterrorsource"></a><a name="geterrorsource"></a> Ierrorrecordシム Pl:: GetErrorSource

エラーレコードからのエラーの原因となったソースコードを取得します。

### <a name="syntax"></a>構文

```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>パラメーター

*rCurError*<br/>
`ERRORINFO`インターフェイス内のレコード `IErrorInfo` 。

### <a name="return-value"></a>戻り値

エラーのソースコードを格納している文字列へのポインター。

## <a name="ierrorrecordsimpladderrorrecord"></a><a name="adderrorrecord"></a> Ierrorrecordシム Pl:: AddErrorRecord

OLE DB error オブジェクトにレコードを追加します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,
   DWORD dwLookupID,
   DISPPARAMS *pdispparams,
   IUnknown *punkCustomError,
   DWORD dwDynamicErrorID);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: adderrorrecord](/previous-versions/windows/desktop/ms725362(v=vs.85)) 」を参照してください。

## <a name="ierrorrecordsimplgetbasicerrorinfo"></a><a name="getbasicerrorinfo"></a> Ierrorrecordシム Pl:: GetBasicErrorInfo

リターンコードやプロバイダー固有のエラー番号など、エラーに関する基本的な情報を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,
   ERRORINFO *pErrorInfo);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: getbasicerrorinfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) 」を参照してください。

## <a name="ierrorrecordsimplgetcustomerrorobject"></a><a name="getcustomerrorobject"></a> Ierrorrecordシム Pl:: GetCustomErrorObject

カスタムエラーオブジェクトのインターフェイスへのポインターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,
   REFIID riid,
   IUnknown **ppObject);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) 」を参照してください。

## <a name="ierrorrecordsimplgeterrorinfo"></a><a name="geterrorinfo"></a> Ierrorrecordシム Pl:: GetErrorInfo

指定されたレコードの [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) インターフェイスポインターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,
   LCID lcid,
   IErrorInfo **ppErrorInfo);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 」を参照してください。

## <a name="ierrorrecordsimplgeterrorparameters"></a><a name="geterrorparameters"></a> Ierrorrecordシム Pl:: GetErrorParameters

エラーパラメーターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,
   DISPPARAMS *pdispparams);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) 」を参照してください。

## <a name="ierrorrecordsimplgetrecordcount"></a><a name="getrecordcount"></a> Ierrorrecordシム Pl:: GetRecordCount

OLE DB レコードオブジェクト内のレコードの数を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetRecordCount](/previous-versions/windows/desktop/ms722724(v=vs.85)) 」を参照してください。

## <a name="ierrorrecordsimplm_rgerrors"></a><a name="rgerrors"></a> Ierrorrecordシム Pl:: m_rgErrors

エラーレコードの配列。

### <a name="syntax"></a>構文

```cpp
CAtlArray< RecordClass > m_rgErrors;
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)

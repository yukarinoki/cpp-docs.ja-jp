---
title: CDBErrorInfo クラス
ms.date: 11/04/2016
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- CDBErrorInfo::GetErrorRecords
helpviewer_keywords:
- CDBErrorInfo class
- GetAllErrorInfo method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetErrorRecords method
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
ms.openlocfilehash: 5c26a3f1e8b5589afebd72c7b722ab9ed9e4229d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838309"
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo クラス

OLE DB [Ierrorrecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) インターフェイスを使用した OLE DB エラー処理のサポートを提供します。

## <a name="syntax"></a>構文

```cpp
class CDBErrorInfo
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[GetAllErrorInfo](#getallerrorinfo)|エラーレコードに含まれるすべてのエラー情報を返します。|
|[GetBasicErrorInfo](#getbasicerrorinfo)|[Ierrorrecords:: GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85))を呼び出して、指定されたエラーに関する基本情報を返します。|
|[GetCustomErrorObject](#getcustomerrorobject)|[Ierrorrecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85))を呼び出して、カスタムエラーオブジェクトのインターフェイスへのポインターを返します。|
|[GetErrorInfo](#geterrorinfo)|[Ierrorrecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85))を呼び出し `IErrorInfo` て、指定されたレコードへのインターフェイスポインターを返します。|
|[GetErrorParameters](#geterrorparameters)|[Ierrorrecords:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85))を呼び出して、エラーパラメーターを返します。|
|[GetErrorRecords](#geterrorrecords)|指定したオブジェクトのエラーレコードを取得します。|

## <a name="remarks"></a>解説

このインターフェイスは、1つまたは複数のエラーレコードをユーザーに返します。 エラーレコードの数を取得するには、最初に [CDBErrorInfo:: GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) を呼び出します。 次に、いずれかのアクセス関数 ( [CDBErrorInfo:: GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)など) を呼び出して、各レコードのエラー情報を取得します。

## <a name="cdberrorinfogetallerrorinfo"></a><a name="getallerrorinfo"></a> CDBErrorInfo:: GetAllErrorInfo

エラーレコードに含まれるエラー情報のすべての型を返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetAllErrorInfo(ULONG ulRecordNum,
   LCID lcid,  BSTR* pbstrDescription,
   BSTR* pbstrSource = NULL,
   GUID* pguid = NULL,
   DWORD* pdwHelpContext = NULL,
   BSTR* pbstrHelpFile = NULL) const throw();
```

#### <a name="parameters"></a>パラメーター

*ulRecordNum*<br/>
からエラー情報を返すレコードの、0から始まる番号。

*lcid*<br/>
から返されるエラー情報のロケール ID。

*pbstrDescription*<br/>
入出力エラーの説明テキストへのポインター。ロケールがサポートされていない場合は NULL。 「解説」を参照してください。

*pbstrSource*<br/>
入出力エラーを生成したコンポーネントの名前を格納している文字列へのポインター。

*pguid*<br/>
入出力エラーを定義したインターフェイスの GUID へのポインター。

*pdwHelpContext*<br/>
入出力エラーのヘルプコンテキスト ID へのポインター。

*pbstrHelpFile*<br/>
入出力エラーを説明するヘルプファイルへのパスを含む文字列へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。 他の戻り値については、 *OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

*Pbstrdescription*の出力値は、を呼び出すことによって内部的に取得されます `IErrorInfo::GetDescription` 。これは、ロケールがサポートされていない場合、または次の両方の条件に該当する場合に、値を NULL に設定します。

1. *lcid*の値が米国英語および

1. *lcid*の値が、GetUserDefaultLCID によって返された値と等しくありません。

## <a name="cdberrorinfogetbasicerrorinfo"></a><a name="getbasicerrorinfo"></a> CDBErrorInfo:: GetBasicErrorInfo

[Ierrorrecords:: GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85))を呼び出して、リターンコードやプロバイダー固有のエラー番号など、エラーに関する基本的な情報を返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,
   ERRORINFO* pErrorInfo) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: getbasicerrorinfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdberrorinfogetcustomerrorobject"></a><a name="getcustomerrorobject"></a> CDBErrorInfo:: GetCustomErrorObject

[Ierrorrecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85))を呼び出して、カスタムエラーオブジェクトのインターフェイスへのポインターを返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,
   REFIID riid,IUnknown** ppObject) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdberrorinfogeterrorinfo"></a><a name="geterrorinfo"></a> CDBErrorInfo:: GetErrorInfo

指定されたレコードへの[IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85))インターフェイスポインターを返すために、 [Ierrorrecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85))を呼び出します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdberrorinfogeterrorparameters"></a><a name="geterrorparameters"></a> CDBErrorInfo:: GetErrorParameters

[Ierrorrecords:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85))を呼び出して、エラーパラメーターを返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,
   DISPPARAMS* pdispparams) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Ierrorrecords:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdberrorinfogeterrorrecords"></a><a name="geterrorrecords"></a> CDBErrorInfo:: GetErrorRecords

指定したオブジェクトのエラーレコードを取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,
   const IID& iid,
   ULONG* pcRecords) throw();

HRESULT GetErrorRecords(ULONG* pcRecords) throw();
```

#### <a name="parameters"></a>パラメーター

*パンク*<br/>
からエラーレコードを取得する対象のオブジェクトへのインターフェイス。

*iid*<br/>
からエラーに関連付けられているインターフェイスの IID。

*pcRecords*<br/>
入出力(1 から始まる) エラーレコードの数へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

エラー情報を取得するインターフェイスを確認する場合は、関数の最初の形式を使用します。 それ以外の場合は、2番目の形式を使用します。

## <a name="see-also"></a>関連項目

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)

---
title: CDynamicParameterAccessor クラス
ms.date: 02/14/2018
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
- ATL::CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor.GetParamCount
- GetParamCount
- ATL.CDynamicParameterAccessor.GetParamCount
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
- CDynamicParameterAccessor::GetParamName
- ATL.CDynamicParameterAccessor.GetParamName
- GetParamName
- CDynamicParameterAccessor.GetParamName
- ATL::CDynamicParameterAccessor::GetParamName
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
helpviewer_keywords:
- CDynamicParameterAccessor class
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
- GetParam method
- GetParamCount method
- GetParamIO method
- GetParamLength method
- GetParamName method
- GetParamStatus method
- GetParamString method
- GetParamType method
- SetParam method
- SetParamLength method
- SetParamStatus method
- SetParamString method
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
ms.openlocfilehash: de9aafe5b04b949112c44be09ac36bede7e7f660
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838179"
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor クラス

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) と類似していますが、 [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) インターフェイスを呼び出すことで設定されるパラメーター情報を取得します。

## <a name="syntax"></a>構文

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>必要条件

**ヘッダー**: atldbcli. h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|コンストラクターです。|
|[GetParam](#getparam)|バッファーからパラメーター データを取得します。|
|[GetParamCount](#getparamcount)|アクセサー内のパラメーターの数を取得します。|
|[GetParamIO](#getparamio)|指定されたパラメーターが入力または出力パラメーターであるかどうかを判断します。|
|[GetParamLength](#getparamlength)|バッファーに格納され、指定されたパラメーターの長さを取得します。|
|[GetParamName](#getparamname)|指定されたパラメーターの名前を取得します。|
|[GetParamStatus](#getparamstatus)|バッファーに格納され、指定されたパラメーターのステータスを取得します。|
|[GetParamString](#getparamstring)|バッファーに格納され、指定されたパラメーターの文字列データを取得します。|
|[GetParamType](#getparamtype)|指定されたパラメーターのデータ型を取得します。|
|[SetParam](#setparam)|パラメーター データを使用してバッファーを設定します。|
|[SetParamLength](#setparamlength)|バッファーに格納され、指定されたパラメーターの長さを設定します。|
|[SetParamStatus](#setparamstatus)|バッファーに格納され、指定されたパラメーターのステータスを設定します。|
|[SetParamString](#setparamstring)|バッファーに格納され、指定されたパラメーターの文字列データを設定します。|

## <a name="remarks"></a>解説

コンシューマーがこのクラスを使用するには、プロバイダーで `ICommandWithParameters` がサポートされている必要があります。

パラメーター情報は、このクラスによって作成および管理されるバッファーに格納されます。 [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) と [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)を使用してバッファーからパラメーター データを取得します。

このクラスを使用して SQL Server のストアドプロシージャを実行し、出力パラメーターの値を取得する方法を示す例については、GitHub の[Microsoft VCSamples](https://github.com/Microsoft/VCSamples)リポジトリにある[dynamicconsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)サンプルコードを参照してください。

## <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a><a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor:: CDynamicParameterAccessor

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
typedef CDynamicParameterAccessor _ParamClass;
CDynamicParameterAccessor(
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000 )
   : CDynamicAccessor(eBlobHandling, nBlobSize )
```

#### <a name="parameters"></a>パラメーター

*eBlobHandling*<br/>
BLOB データを処理する方法を指定します。 既定値は DBBLOBHANDLING_DEFAULT です。 DBBLOBCDYNAMICACCESSOR LINGENUM 値の説明については、「 [:: SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) 」を参照してください。

*nBlobSize*<br/>
BLOB の最大サイズ (バイト単位)。この値に対する列データは、BLOB として扱われます。 既定値は8000です。 詳細については、「 [CDynamicAccessor:: SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) 」を参照してください。

### <a name="remarks"></a>解説

BLOB 処理の詳細については、 [CDynamicAccessor:: CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) コンストラクターを参照してください。

## <a name="cdynamicparameteraccessorgetparam"></a><a name="getparam"></a> CDynamicParameterAccessor:: GetParam

パラメーターバッファーから、指定したパラメーターの文字列以外のデータを取得します。

### <a name="syntax"></a>構文

```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,
   ctype* pData) const throw();

template <class ctype> bool GetParam(TCHAR* pParamName,
   ctype* pData) const throw();

void* GetParam(DBORDINAL nParam) const throw();

void* GetParam(TCHAR* pParamName) const throw();
```

#### <a name="parameters"></a>パラメーター

*ctype*<br/>
データ型であるテンプレート化されたパラメーター。

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*pParamName*<br/>
からパラメーター名。

*pData*<br/>
入出力バッファーから取得されたデータを格納しているメモリへのポインター。

### <a name="return-value"></a>戻り値

テンプレートが使用されていないバージョンでは、はバッファーから取得したデータを格納しているメモリを指します。 テンプレート化されたバージョンの場合、成功した場合は、失敗した場合はを返し **`true`** **`false`** ます。

`GetParam`バッファーから文字列以外のパラメーターデータを取得するには、を使用します。 [Getparamstring](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)を使用して、バッファーから文字列パラメーターデータを取得します。

## <a name="cdynamicparameteraccessorgetparamcount"></a><a name="getparamcount"></a> CDynamicParameterAccessor:: GetParamCount

バッファーに格納されているパラメーターの数を取得します。

### <a name="syntax"></a>構文

```cpp
DB_UPARAMS GetParamCount() const throw();
```

### <a name="return-value"></a>戻り値

パラメーターの数。

## <a name="cdynamicparameteraccessorgetparamio"></a><a name="getparamio"></a> CDynamicParameterAccessor:: GetParamIO

指定されたパラメーターが入力または出力パラメーターであるかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
bool GetParamIO(DBORDINAL nParam,
   DBPARAMIO* pParamIO) const throw();
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*pParamIO*<br/>
`DBPARAMIO`指定されたパラメーターの型 (入力または出力) を格納している変数へのポインター。 次のように定義します。

```cpp
typedef DWORD DBPARAMIO;

enum DBPARAMIOENUM {
    DBPARAMIO_NOTPARAM   = 0,
    DBPARAMIO_INPUT      = 0x1,
    DBPARAMIO_OUTPUT     = 0x2
};
```

### <a name="return-value"></a>戻り値

**`true`** 成功した場合、または失敗した場合はを返し **`false`** ます。

## <a name="cdynamicparameteraccessorgetparamlength"></a><a name="getparamlength"></a> CDynamicParameterAccessor:: GetParamLength

バッファーに格納され、指定されたパラメーターの長さを取得します。

### <a name="syntax"></a>構文

```cpp
bool GetParamLength(DBORDINAL nParam,
   DBLENGTH* pLength);

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*pLength*<br/>
入出力指定されたパラメーターの長さ (バイト単位) を格納している変数へのポインター。

### <a name="remarks"></a>解説

最初のオーバーライドは、成功した場合はを返し、失敗した場合はを返し **`true`** **`false`** ます。 2番目のオーバーライドは、パラメーターの長さを格納しているメモリを指します。

## <a name="cdynamicparameteraccessorgetparamname"></a><a name="getparamname"></a> CDynamicParameterAccessor:: GetParamName

指定したパラメーターの名前を取得します。

### <a name="syntax"></a>構文

```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

### <a name="return-value"></a>戻り値

指定したパラメーターの名前。

## <a name="cdynamicparameteraccessorgetparamstatus"></a><a name="getparamstatus"></a> CDynamicParameterAccessor:: GetParamStatus

バッファーに格納され、指定されたパラメーターのステータスを取得します。

### <a name="syntax"></a>構文

```cpp
bool GetParamStatus(DBORDINAL nParam,
   DBSTATUS* pStatus);

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*pStatus*<br/>
入出力指定されたパラメーターの DBSTATUS status を格納している変数へのポインター。 DBSTATUS 値の詳細については、 *OLE DB プログラマーリファレンス*の「 [Status](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照するか、DBSTATUS の「」を検索してください。

### <a name="remarks"></a>解説

最初のオーバーライドは、成功した場合はを返し、失敗した場合はを返し **`true`** **`false`** ます。 2番目のオーバーライドは、指定されたパラメーターの状態を格納しているメモリを指します。

## <a name="cdynamicparameteraccessorgetparamstring"></a><a name="getparamstring"></a> CDynamicParameterAccessor:: GetParamString

バッファーに格納され、指定されたパラメーターの文字列データを取得します。

### <a name="syntax"></a>構文

```cpp
bool GetParamString(DBORDINAL nParam,
   CSimpleStringA& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CSimpleStringW& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CHAR* pBuffer,
   size_t* pMaxLen) throw();

bool GetParamString(DBORDINAL nParam,
   WCHAR* pBuffer,
   size_t* pMaxLen) throw();
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*strOutput*<br/>
入出力`CSimpleStringA`指定されたパラメーターの ANSI () 文字列データまたは Unicode ( `CSimpleStringW` ) 文字列データ。 型のパラメーターを渡す必要があり `CString` ます。次に例を示します。

[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]

*pBuffer*<br/>
入出力指定されたパラメーターの ANSI (**CHAR**) または Unicode (**WCHAR**) 文字列データへのポインター。

*pMaxLen*<br/>
入出力 *Pbuffer* によってポイントされるバッファーのサイズへのポインター (終端の NULL を含む文字数)。

### <a name="remarks"></a>解説

**`true`** 成功した場合、または失敗した場合はを返し **`false`** ます。

*Pbuffer*が NULL の場合、このメソッドは、 *pbuffer*が指すメモリ内の必要なバッファーサイズを設定し、 **`true`** データをコピーせずにを返します。

バッファーの *Pbuffer* が文字列全体を格納するのに十分な大きさでない場合、このメソッドは失敗します。

`GetParamString`バッファーから文字列パラメーターデータを取得するには、を使用します。 [Getparam](../../data/oledb/cdynamicparameteraccessor-getparam.md)を使用して、バッファーから文字列以外のパラメーターデータを取得します。

## <a name="cdynamicparameteraccessorgetparamtype"></a><a name="getparamtype"></a> CDynamicParameterAccessor:: GetParamType

指定されたパラメーターのデータ型を取得します。

### <a name="syntax"></a>構文

```cpp
bool GetParamType(DBORDINAL nParam,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*pType*<br/>
入出力指定されたパラメーターのデータ型を格納している変数へのポインター。

### <a name="return-value"></a>戻り値

**`true`** 成功した場合、または失敗した場合はを返し **`false`** ます。

## <a name="cdynamicparameteraccessorsetparam"></a><a name="setparam"></a> CDynamicParameterAccessor:: SetParam

指定した (文字列ではない) データを使用して、パラメーターバッファーを設定します。

### <a name="syntax"></a>構文

```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,
   constctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();

template <class ctype>
bool SetParam(TCHAR* pParamName,
   const ctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>パラメーター

*ctype*<br/>
データ型であるテンプレート化されたパラメーター。

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 次に例を示します。

[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]

*pParamName*<br/>
からパラメーター名。

*pData*<br/>
からバッファーに書き込まれるデータを格納しているメモリへのポインター。

*status*<br/>
からDBSTATUS 列の状態です。 DBSTATUS 値の詳細については、 *OLE DB プログラマーリファレンス*の「 [Status](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照するか、DBSTATUS の「」を検索してください。

### <a name="return-value"></a>戻り値

**`true`** 成功した場合、または失敗した場合はを返し **`false`** ます。

`SetParam`バッファーに文字列以外のパラメーターデータを設定するには、を使用します。 [Setparamstring](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)を使用して、バッファー内の文字列パラメーターデータを設定します。

## <a name="cdynamicparameteraccessorsetparamlength"></a><a name="setparamlength"></a> CDynamicParameterAccessor:: SetParamLength

バッファーに格納され、指定されたパラメーターの長さを設定します。

### <a name="syntax"></a>構文

```cpp
bool SetParamLength(DBORDINAL nParam,
   DBLENGTH length);
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*length*<br/>
から指定されたパラメーターの長さ (バイト単位)。

### <a name="remarks"></a>解説

**`true`** 成功した場合、または失敗した場合はを返し **`false`** ます。

## <a name="cdynamicparameteraccessorsetparamstatus"></a><a name="setparamstatus"></a> CDynamicParameterAccessor:: SetParamStatus

バッファーに格納され、指定されたパラメーターのステータスを設定します。

### <a name="syntax"></a>構文

```cpp
bool SetParamStatus(DBORDINAL nParam,
   DBSTATUS status);
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*status*<br/>
から指定されたパラメーターの DBSTATUS の状態。 DBSTATUS 値の詳細については、 *OLE DB プログラマーリファレンス*の「 [Status](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照するか、DBSTATUS の「」を検索してください。

### <a name="remarks"></a>解説

**`true`** 成功した場合、または失敗した場合はを返し **`false`** ます。

## <a name="cdynamicparameteraccessorsetparamstring"></a><a name="setparamstring"></a> CDynamicParameterAccessor:: SetParamString

バッファーに格納され、指定されたパラメーターの文字列データを設定します。

### <a name="syntax"></a>構文

```cpp
bool SetParamString(DBORDINAL nParam,
   constCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,
   constWCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>パラメーター

*nParam*<br/>
からパラメーターの数 (1 からのオフセット)。 パラメーター0は戻り値用に予約されています。 パラメーター番号は、SQL またはストアドプロシージャの呼び出しの順序に基づいてパラメーターのインデックスを指定します。 例については、「 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 」を参照してください。

*pString*<br/>
から指定されたパラメーターの ANSI (**CHAR**) または Unicode (**WCHAR**) 文字列データへのポインター。 「DBSTATUS in oledb」を参照してください。

*status*<br/>
から指定されたパラメーターの DBSTATUS の状態。 DBSTATUS 値の詳細については、 *OLE DB プログラマーリファレンス*の「 [Status](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照するか、DBSTATUS の「」を検索してください。

### <a name="remarks"></a>解説

**`true`** 成功した場合、または失敗した場合はを返し **`false`** ます。

`SetParamString` は、 *pstring*に指定された最大サイズを超える文字列を設定しようとすると失敗します。

`SetParamString`バッファーに文字列パラメーターデータを設定するには、を使用します。 バッファーに文字列以外のパラメーターデータを設定するには、 [Setparam](../../data/oledb/cdynamicparameteraccessor-setparam.md) を使用します。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor クラス](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)

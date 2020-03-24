---
title: CDynamicAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
- ATL::CDynamicAccessor::AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
- ATL::CDynamicAccessor::Close
- ATL.CDynamicAccessor.Close
- CDynamicAccessor.Close
- CDynamicAccessor::Close
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
- ATL::CDynamicAccessor::GetBlobSizeLimit
- CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor::GetBlobSizeLimit
- GetBlobSizeLimit
- ATL.CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetColumnCount
- ATL::CDynamicAccessor::GetColumnCount
- CDynamicAccessor::GetColumnCount
- CDynamicAccessor.GetColumnCount
- GetColumnCount
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
helpviewer_keywords:
- CDynamicAccessor class
- AddBindEntry method
- CDynamicAccessor class, constructor
- Close method
- GetBlobHandling method
- GetBlobSizeLimit method
- GetBookmark method
- GetColumnCount method
- GetColumnFlags method
- GetColumnInfo method
- GetColumnName method
- GetColumnType method
- GetLength method
- GetOrdinal method
- GetStatus method
- GetValue method
- SetBlobHandling method
- SetBlobSizeLimit method
- SetLength method
- SetStatus method
- SetValue method
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
ms.openlocfilehash: 160e5b6d8eb4b45850dc071299413d9ad2cfcee9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212064"
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor クラス

データベーススキーマ (データベースの基になる構造) に関する知識がない場合に、データソースにアクセスできるようにします。

## <a name="syntax"></a>構文

```cpp
class CDynamicAccessor : public CAccessorBase
```

## <a name="requirements"></a>必要条件

**ヘッダー**: atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddBindEntry](#addbindentry)|既定のアクセサーをオーバーライドするときに、出力列にバインドエントリを追加します。|
|[CDynamicAccessor](#cdynamicaccessor)|`CDynamicAccessor` オブジェクトをインスタンス化し、初期化します。|
|[[閉じる]](#close)|すべての列のバインドを解除し、割り当てられたメモリを解放して、クラス内の[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))インターフェイスポインターを解放します。|
|[GetBlobHandling](#getblobhandling)|現在の行の BLOB 処理値を取得します。|
|[GetBlobSizeLimit](#getblobsizelimit)|BLOB の最大サイズをバイト単位で取得します。|
|[GetBookmark](#getbookmark)|現在の行のブックマークを取得します。|
|[GetColumnCount](#getcolumncount)|行セット内の列の数を取得します。|
|[GetColumnFlags](#getcolumnflags)|列の特性を取得します。|
|[GetColumnInfo](#getcolumninfo)|列のメタデータを取得します。|
|[GetColumnName](#getcolumnname)|指定された列の名前を取得します。|
|[GetColumnType](#getcolumntype)|指定された列のデータ型を取得します。|
|[GetLength](#getlength)|列の可能な最大長をバイト単位で取得します。|
|[GetOrdinal](#getordinal)|列名が指定された列インデックスを取得します。|
|[GetStatus](#getstatus)|指定された列の状態を取得します。|
|[GetValue](#getvalue)|バッファーからデータを取得します。|
|[SetBlobHandling](#setblobhandling)|現在の行の BLOB 処理値を設定します。|
|[SetBlobSizeLimit](#setblobsizelimit)|BLOB の最大サイズをバイト単位で設定します。|
|[SetLength](#setlength)|列の長さをバイト単位で設定します。|
|[SetStatus](#setstatus)|指定された列の状態を設定します。|
|[SetValue](#setvalue)|データをバッファーに格納します。|

## <a name="remarks"></a>解説

`CDynamicAccessor` メソッドを使用して、列名、列数、データ型などの列情報を取得します。 次に、この列情報を使用して、実行時にアクセサーを動的に作成します。

列情報は、このクラスによって作成および管理されるバッファーに格納されます。 [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)を使用してバッファーからデータを取得します。

動的アクセサークラスの使用例については、「[動的アクセサーの使用](../../data/oledb/using-dynamic-accessors.md)」を参照してください。

## <a name="cdynamicaccessoraddbindentry"></a><a name="addbindentry"></a>CDynamicAccessor:: AddBindEntry

出力列にバインドエントリを追加します。

### <a name="syntax"></a>構文

```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();
```

#### <a name="parameters"></a>パラメーター

*info*<br/>
から列情報を格納している `DBCOLUMNINFO` 構造体。 *OLE DB プログラマーリファレンス*の「 [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 」の「DBCOLUMNINFO 構造体」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

`CDynamicAccessor` で作成された既定のアクセサーをオーバーライドする場合は、このメソッドを使用します (「[データをフェッチする方法](../../data/oledb/fetching-data.md)」を参照してください)。

## <a name="cdynamicaccessorcdynamicaccessor"></a><a name="cdynamicaccessor"></a>CDynamicAccessor:: CDynamicAccessor

`CDynamicAccessor` オブジェクトをインスタンス化し、初期化します。

### <a name="syntax"></a>構文

```cpp
CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000);
```

#### <a name="parameters"></a>パラメーター

*eBlobHandling*<br/>
バイナリラージオブジェクト (BLOB) データを処理する方法を指定します。 既定値は DBBLOBHANDLING_DEFAULT です。 DBBLOBの LINGENUM 値の説明については、「 [Setblobhandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) 」を参照してください。

*nBlobSize*<br/>
BLOB の最大サイズ (バイト単位)。この値に対する列データは、BLOB として扱われます。 既定値は8000です。 詳細については、「 [Setblobsizelimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) 」を参照してください。

### <a name="remarks"></a>解説

コンストラクターを使用して `CDynamicAccessor` オブジェクトを初期化する場合は、Blob のバインド方法を指定できます。 Blob には、グラフィックス、サウンド、コンパイル済みコードなどのバイナリデータを含めることができます。 既定の動作では、8000バイトを超える列を Blob として扱い、`ISequentialStream` オブジェクトにバインドしようとします。 ただし、BLOB サイズとして別の値を指定することもできます。

BLOB データとして使用できる列データを `CDynamicAccessor` が処理する方法を指定することもできます。これは、BLOB データを既定の方法で処理できます。BLOB データをスキップする (バインドしない) ことができます。または、プロバイダーによって割り当てられたメモリ内の BLOB データをバインドすることもできます。

## <a name="cdynamicaccessorclose"></a><a name="close"></a>CDynamicAccessor:: Close

すべての列のバインドを解除し、割り当てられたメモリを解放して、クラス内の[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))インターフェイスポインターを解放します。

### <a name="syntax"></a>構文

```cpp
void Close() throw();
```

## <a name="cdynamicaccessorgetblobhandling"></a><a name="getblobhandling"></a>CDynamicAccessor:: GetBlobHandling

現在の行の BLOB 処理値を取得します。

### <a name="syntax"></a>構文

```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;
```

### <a name="remarks"></a>解説

[Setblobhandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)によって設定された、BLOB 処理値*eblobhandling*を返します。

## <a name="cdynamicaccessorgetblobsizelimit"></a><a name="getblobsizelimit"></a>CDynamicAccessor:: GetBlobSizeLimit

BLOB の最大サイズをバイト単位で取得します。

### <a name="syntax"></a>構文

```cpp
const DBLENGTH GetBlobSizeLimit() const;
```

### <a name="remarks"></a>解説

[Setblobsizelimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)によって設定された、BLOB 処理の値*nblobsize*を返します。

## <a name="cdynamicaccessorgetbookmark"></a><a name="getbookmark"></a>CDynamicAccessor:: GetBookmark

現在の行のブックマークを取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();
```

#### <a name="parameters"></a>パラメーター

*pBookmark*<br/>
入出力[CBookmark](../../data/oledb/cbookmark-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

ブックマークを取得するには、`DBPROP_IRowsetLocate` を VARIANT_TRUE に設定する必要があります。

## <a name="cdynamicaccessorgetcolumncount"></a><a name="getcolumncount"></a>CDynamicAccessor:: GetColumnCount

列の数を取得します。

### <a name="syntax"></a>構文

```cpp
DBORDINAL GetColumnCount() const throw();
```

### <a name="return-value"></a>戻り値

取得する列の数。

## <a name="cdynamicaccessorgetcolumnflags"></a><a name="getcolumnflags"></a>CDynamicAccessor:: GetColumnFlags

列の特性を取得します。

### <a name="syntax"></a>構文

```cpp
bool GetColumnFlags(DBORDINAL nColumn,
   DBCOLUMNFLAGS* pFlags) const throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*pFlags*<br/>
入出力列の特性を記述するビットマスクへのポインター。 *OLE DB プログラマーリファレンス*の「 [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 」の「Dbcolumnflags 列挙型」を参照してください。

### <a name="return-value"></a>戻り値

列の特性が正常に取得された場合は**true**を返します。 それ以外の場合は **false**を返します。

### <a name="remarks"></a>解説

列番号は1からのオフセットです。 列0は特殊なケースです。使用可能な場合はブックマークです。

## <a name="cdynamicaccessorgetcolumninfo"></a><a name="getcolumninfo"></a>CDynamicAccessor:: GetColumnInfo

ほとんどのコンシューマーが必要とする列のメタデータを返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetColumnInfo(IRowset* pRowset,
   DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo,
   OLECHAR** ppStringsBuffer) throw();
```

#### <a name="parameters"></a>パラメーター

*pRowset*<br/>
から[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))インターフェイスへのポインター。

*pColumns*<br/>
入出力行セット内の列数を返すメモリへのポインター。この数値には、ブックマーク列 (存在する場合) が含まれます。

*ppColumnInfo*<br/>
入出力`DBCOLUMNINFO` 構造体の配列を返すメモリへのポインター。 *OLE DB プログラマーリファレンス*の「 [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 」の「DBCOLUMNINFO 構造体」を参照してください。

*ppStringsBuffer*<br/>
入出力1つの割り当てブロック内で、すべての文字列値 ( *columnid*または for *pwszName*内で使用される名前) のストレージへのポインターを返すメモリへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

データ型 `DBORDINAL`、`DBCOLUMNINFO`、および `OLECHAR`の詳細については、 *OLE DB プログラマーリファレンス*の「 [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 」を参照してください。

## <a name="cdynamicaccessorgetcolumnname"></a><a name="getcolumnname"></a>CDynamicAccessor:: GetColumnName

指定された列の名前を取得します。

### <a name="syntax"></a>構文

```cpp
LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

### <a name="return-value"></a>戻り値

指定された列の名前。

## <a name="cdynamicaccessorgetcolumntype"></a><a name="getcolumntype"></a>CDynamicAccessor:: GetColumnType

指定された列のデータ型を取得します。

### <a name="syntax"></a>構文

```cpp
bool GetColumnType(DBORDINAL nColumn,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*pType*<br/>
入出力指定された列のデータ型へのポインター。

### <a name="return-value"></a>戻り値

成功した**場合は true** 、失敗した場合は**false**を返します。

## <a name="cdynamicaccessorgetlength"></a><a name="getlength"></a>CDynamicAccessor:: GetLength

指定された列の長さを取得します。

### <a name="syntax"></a>構文

```cpp
bool GetLength(DBORDINAL nColumn,
   DBLENGTH* pLength) const throw();

bool GetLength(const CHAR* pColumnName,
   DBLENGTH* pLength) const throw();

bool GetLength(const WCHAR* pColumnName,
   DBLENGTH* pLength) const throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*pColumnName*<br/>
から列名を含む文字列へのポインター。

*pLength*<br/>
入出力列の長さ (バイト単位) を格納している整数へのポインター。

### <a name="return-value"></a>戻り値

指定された列が見つかった場合は**true**を返します。 それ以外の場合、この関数は**false**を返します。

### <a name="remarks"></a>解説

最初のオーバーライドは列番号を受け取り、2番目と3番目のオーバーライドは、それぞれ ANSI 形式または Unicode 形式で列名を取得します。

## <a name="cdynamicaccessorgetordinal"></a><a name="getordinal"></a>CDynamicAccessor:: GetOrdinal

列名を指定して列番号を取得します。

### <a name="syntax"></a>構文

```cpp
bool GetOrdinal(const CHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();

bool GetOrdinal(const WCHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();
```

#### <a name="parameters"></a>パラメーター

*pColumnName*<br/>
から列名を含む文字列へのポインター。

*pOrdinal*<br/>
入出力列番号へのポインター。

### <a name="return-value"></a>戻り値

指定された名前の列が見つかった場合に**true**を返します。 それ以外の場合、この関数は**false**を返します。

## <a name="cdynamicaccessorgetstatus"></a><a name="getstatus"></a>CDynamicAccessor:: GetStatus

指定された列の状態を取得します。

### <a name="syntax"></a>構文

```cpp
bool GetStatus(DBORDINAL nColumn,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const CHAR* pColumnName,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const WCHAR* pColumnName,
   DBSTATUS* pStatus) const throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*pColumnName*<br/>
から列名を含む文字列へのポインター。

*pStatus*<br/>
入出力列の状態を格納している変数へのポインター。 詳細については、 *OLE DB プログラマーリファレンス*の「 [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

指定された列が見つかった場合は**true**を返します。 それ以外の場合、この関数は**false**を返します。

## <a name="cdynamicaccessorgetvalue"></a><a name="getvalue"></a>CDynamicAccessor:: GetValue

指定された列のデータを取得します。

### <a name="syntax"></a>構文

```cpp
void* GetValue(DBORDINAL nColumn) const throw();

void* GetValue(const CHAR* pColumnName) const throw();

void* GetValue(const WCHAR* pColumnName) const throw();

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();

template < class ctype >
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();

template < class ctype >
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();
```

#### <a name="parameters"></a>パラメーター

*ctype*<br/>
から特別な処理を必要とする文字列型 (`CHAR*`、`WCHAR*`) を除く任意のデータ型を処理する、テンプレート化されたパラメーター。 `GetValue` は、ここで指定した内容に基づいて適切なデータ型を使用します。

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*pColumnName*<br/>
から列名。

*pData*<br/>
入出力指定された列のコンテンツへのポインター。

### <a name="return-value"></a>戻り値

文字列データを渡す場合は、`GetValue`の非テンプレートバージョンを使用します。 このメソッドの非テンプレート化バージョンは `void*`を返します。これは、指定された列データを格納するバッファーの部分を指します。 列が見つからない場合は NULL を返します。

他のすべてのデータ型については、テンプレート化されたバージョンの `GetValue`を使用する方が簡単です。 テンプレート化されたバージョンは、成功した**場合は true** 、失敗した場合は**false**を返します。

### <a name="remarks"></a>解説

非テンプレートバージョンを使用すると、文字列を含む列と、他のデータ型を含む列のテンプレート化されたバージョンを返すことができます。

デバッグモードでは、 *pData*のサイズがそれが指す列のサイズと等しくない場合、アサーションが発生します。

## <a name="cdynamicaccessorsetblobhandling"></a><a name="setblobhandling"></a>CDynamicAccessor:: SetBlobHandling

現在の行の BLOB 処理値を設定します。

### <a name="syntax"></a>構文

```cpp
bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);
```

#### <a name="parameters"></a>パラメーター

*eBlobHandling*<br/>
BLOB データを処理する方法を指定します。 次の値を使用できます。

- DBBLOBHANDLING_DEFAULT: `SetBlobSizeLimit`によって設定された、 *Nblobsize*を超える列データを BLOB データとして処理し、`ISequentialStream` または `IStream` オブジェクトを使用して取得します。 このオプションは、 *Nblobsize*より大きいデータを含むすべての列をバインドするか、BLOB データとして DBTYPE_IUNKNOWN として表示します。

- DBBLOBHANDLING_NOSTREAMS: *Nblobsize* (`SetBlobSizeLimit`によって設定される) よりも大きい列データを BLOB データとして処理し、プロバイダーが割り当てたコンシューマー所有のメモリ内の参照を使用して取得します。 このオプションは、複数の BLOB 列を含むテーブルで、プロバイダーがアクセサーごとに1つの `ISequentialStream` オブジェクトのみをサポートする場合に便利です。

- DBBLOBHANDLING_SKIP: Blob を含んでいる列として修飾された列をスキップします (バインドしないでください) (アクセサーは列の値をバインドまたは取得しませんが、列の状態と長さを取得します)。

### <a name="remarks"></a>解説

`SetBlobHandling` を呼び出してから `Open` を呼び出す必要があります。

コンストラクターメソッド[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)は、BLOB 処理の値を DBBLOBHANDLING_DEFAULT に設定します。

## <a name="cdynamicaccessorsetblobsizelimit"></a><a name="setblobsizelimit"></a>CDynamicAccessor:: SetBlobSizeLimit

BLOB の最大サイズをバイト単位で設定します。

### <a name="syntax"></a>構文

```cpp
void SetBlobSizeLimit(DBLENGTH nBlobSize);
```

#### <a name="parameters"></a>パラメーター

*nBlobSize*<br/>
BLOB サイズの制限を指定します。

### <a name="remarks"></a>解説

BLOB の最大サイズをバイト単位で設定します。この値より大きい列データは、BLOB として扱われます。 プロバイダーによっては、列のサイズが非常に大きくなる場合があります (2 GB など)。 このサイズの列にメモリを割り当てるのではなく、通常、これらの列を Blob としてバインドしようとします。 この方法では、すべてのメモリを割り当てる必要はありませんが、切り捨てをしなくてもすべてのデータを読み取ることができます。 ただし、ネイティブデータ型の大きな列をバインドする `CDynamicAccessor` を強制することが必要になる場合もあります。 これを行うには、`Open`を呼び出す前に `SetBlobSizeLimit` を呼び出します。

コンストラクターメソッド[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)は、BLOB の最大サイズを8000バイトの既定値に設定します。

## <a name="cdynamicaccessorsetlength"></a><a name="setlength"></a>CDynamicAccessor:: SetLength

指定された列の長さを設定します。

### <a name="syntax"></a>構文

```cpp
bool SetLength(DBORDINAL nColumn,
   DBLENGTH nLength)throw();

bool SetLength(const CHAR* pColumnName,
   DBLENGTH nLength) throw();

bool SetLength(const WCHAR* pColumnName,
   DBLENGTH nLength) throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*nLength*<br/>
から列の長さ (バイト単位)。

*pColumnName*<br/>
から列名を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

指定した列の長さが正常に設定されている場合は**true**を返します。 それ以外の場合、この関数は**false**を返します。

## <a name="cdynamicaccessorsetstatus"></a><a name="setstatus"></a>CDynamicAccessor:: SetStatus

指定された列の状態を設定します。

### <a name="syntax"></a>構文

```cpp
bool SetStatus(DBORDINAL nColumn,
   DBSTATUS status)throw();

bool SetStatus(const CHAR* pColumnName,
   DBSTATUS status) throw();

bool SetStatus(const WCHAR* pColumnName,
   DBSTATUS status) throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*status*<br/>
から列の状態です。 詳細については、 *OLE DB プログラマーリファレンス*の「 [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照してください。

*pColumnName*<br/>
から列名を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

指定された列の状態が正常に設定されている場合に**true**を返します。 それ以外の場合、この関数は**false**を返します。

## <a name="cdynamicaccessorsetvalue"></a><a name="setvalue"></a>CDynamicAccessor:: SetValue

指定された列にデータを格納します。

### <a name="syntax"></a>構文

```cpp
template <class ctype>
bool SetValue(
   DBORDINAL nColumn,
   constctype& data) throw( );

template <class ctype>
bool SetValue(
   const CHAR * pColumnName,
   const ctype& data) throw( );

template <class ctype>
bool SetValue(
   const WCHAR *pColumnName,
   const ctype& data) throw( );
```

#### <a name="parameters"></a>パラメーター

*ctype*<br/>
から特別な処理を必要とする文字列型 (`CHAR*`、`WCHAR*`) を除く任意のデータ型を処理する、テンプレート化されたパラメーター。 `GetValue` は、ここで指定した内容に基づいて適切なデータ型を使用します。

*pColumnName*<br/>
から列名を含む文字列へのポインター。

*data*<br/>
からデータを格納しているメモリへのポインター。

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

### <a name="return-value"></a>戻り値

文字列データを設定する場合は、`GetValue`の非テンプレートバージョンを使用します。 このメソッドの非テンプレート化バージョンは `void*`を返します。これは、指定された列データを格納するバッファーの部分を指します。 列が見つからない場合は NULL を返します。

他のすべてのデータ型については、テンプレート化されたバージョンの `GetValue`を使用する方が簡単です。 テンプレート化されたバージョンは、成功した**場合は true** 、失敗した場合は**false**を返します。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor クラス](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)

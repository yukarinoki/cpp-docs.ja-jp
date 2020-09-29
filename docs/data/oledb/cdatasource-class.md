---
title: CDataSource クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
- ATL::CDataSource::Close
- ATL.CDataSource.Close
- CDataSource::Close
- CDataSource.Close
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
helpviewer_keywords:
- CDataSource class
- Close method
- GetInitializationString method
- GetProperties method
- GetProperty method
- Open method
- OpenFromFileName method
- OpenFromInitializationString method
- OpenWithPromptFileName method
- OpenWithServiceComponents method
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
ms.openlocfilehash: f94cd631f1c6febdc07d53f84803b1203f4116bc
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502542"
---
# <a name="cdatasource-class"></a>CDataSource クラス

データソースへのプロバイダーによる接続を表す OLE DB データソースオブジェクトに対応します。

## <a name="syntax"></a>構文

```cpp
class CDataSource
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[閉じる](#close)|接続を閉じます。|
|[GetInitializationString](#getinitializationstring)|現在開いているデータソースの初期化文字列を取得します。|
|[GetProperties](#getproperties)|接続されたデータソースに対して現在設定されているプロパティの値を取得します。|
|[GetProperty](#getproperty)|接続されたデータソースに対して現在設定されている単一のプロパティの値を取得します。|
|[[ファイル]](#open)|`CLSID`、、 `ProgID` または `CEnumerator` 呼び出し元によって提供されるモニカーを使用して、プロバイダー (データソース) への接続を作成します。|
|[OpenFromFileName](#openfromfilename)|ユーザー指定のファイル名で指定されたファイルからデータ ソースを開きます。|
|[OpenFromInitializationString](#openfrominitializationstring)|初期化文字列で指定されたデータソースを開きます。|
|[OpenWithPromptFileName](#openwithpromptfilename)|ユーザーは、以前に作成したデータリンクファイルを選択して、対応するデータソースを開くことができます。|
|[OpenWithServiceComponents](#openwithservicecomponents)|[データリンク] ダイアログボックスを使用して、データソースオブジェクトを開きます。|

## <a name="remarks"></a>注釈

1つの接続に対して1つ以上のデータベースセッションを作成できます。 これらのセッションは、によって表され `CSession` ます。 でセッションを作成する前に、 [CDataSource:: Open](#open) を呼び出して接続を開く必要があり `CSession::Open` ます。

の使用例については `CDataSource` 、 [CatDB](../../overview/visual-cpp-samples.md) サンプルを参照してください。

## <a name="cdatasourceclose"></a><a name="close"></a> CDataSource:: Close

ポインターを解放して接続を閉じ `m_spInit` ます。

### <a name="syntax"></a>構文

```cpp
void Close() throw();
```

## <a name="cdatasourcegetinitializationstring"></a><a name="getinitializationstring"></a> CDataSource:: GetInitializationString

現在開いているデータソースの初期化文字列を取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,
   bool bIncludePassword = false) throw();
```

#### <a name="parameters"></a>パラメーター

*pInitializationString*<br/>
入出力初期化文字列へのポインター。

*bIncludePassword*<br/>
[入力] **`true`** string にパスワードが含まれている場合は、それ以外の場合は **`false`** 。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

結果の初期化文字列を使用して、後でこのデータソース接続を再び開くことができます。

## <a name="cdatasourcegetproperties"></a><a name="getproperties"></a> CDataSource:: GetProperties

接続されたデータソースオブジェクトに対して要求されたプロパティ情報を返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetProperties(ULONG ulPropIDSets,
   constDBPROPIDSET* pPropIDSet,
   ULONG* pulPropertySets,
   DBPROPSET** ppPropsets) const throw();
```

#### <a name="parameters"></a>パラメーター

Windows SDK の*OLE DB プログラマーリファレンス*の「 [IDBProperties:: GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

1つのプロパティを取得するには、 [GetProperty](#getproperty)を使用します。

## <a name="cdatasourcegetproperty"></a><a name="getproperty"></a> CDataSource:: GetProperty

接続されているデータソースオブジェクトの指定されたプロパティの値を返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetProperty(const GUID& guid,
   DBPROPID propid,
   VARIANT* pVariant) const throw();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
からプロパティを返す対象のプロパティセットを識別する GUID。

*propid*<br/>
から返されるプロパティのプロパティ ID。

*pVariant*<br/>
入出力が `GetProperty` プロパティの値を返す variant へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

複数のプロパティを取得するには、 [GetProperties](#getproperties)を使用します。

## <a name="cdatasourceopen"></a><a name="open"></a> CDataSource:: Open

、、またはモニカーを使用してデータソースへの接続を開き `CLSID` `ProgID` `CEnumerator` ます。または、ユーザーにロケーターダイアログボックスを表示させることもできます。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(const CLSID& clsid,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CLSID& clsid,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,
   LPCTSTR pName,  LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(const CEnumerator& enumerator,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CEnumerator& enumerator,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(HWND hWnd = GetActiveWindow(),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,
   LPCTSTR pName,LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();
```

#### <a name="parameters"></a>パラメーター

*clsid*<br/>
から `CLSID` データプロバイダーの。

*pPropSet*<br/>
から設定するプロパティと値を格納している [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体の配列へのポインター。 Windows SDK の*OLE DB プログラマーリファレンス*の「[プロパティセットとプロパティグループ](/previous-versions/windows/desktop/ms713696(v=vs.85))」を参照してください。

*nPropertySets*<br/>
から*PPropSet*引数で渡される[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の数。

*pName*<br/>
[入力] 接続先のデータベース名。

*pUserName*<br/>
[入力] ユーザーの名前。

*pPassword*<br/>
[入力] ユーザーのパスワード。

*nInitMode*<br/>
[入力] データベースの初期化モード。 有効な初期化モードの一覧については、Windows SDK の*OLE DB プログラマーリファレンス*の[初期化プロパティ](/previous-versions/windows/desktop/ms723127(v=vs.85))を参照してください。 *Ninitmode*が0の場合、接続を開くために使用されるプロパティセットに初期化モードは含まれません。

*szProgID*<br/>
[入力] プログラム ID。

*子*<br/>
から呼び出し元がを指定していない場合に、接続を開くためのモニカーを取得するために使用される [CEnumerator](../../data/oledb/cenumerator-class.md) オブジェクト `CLSID` 。

*hWnd*<br/>
[入力] ダイアログ ボックスの親であるウィンドウへのハンドル。 *HWnd*パラメーターを使用する関数オーバーロードを使用すると、サービスコンポーネントが自動的に呼び出されます。詳細については、「解説」を参照してください。

*dwPromptOptions*<br/>
[入力] 表示するロケーター ダイアログ ボックスのスタイルを指定します。 使用できる値については、Msdasc.h を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

*HWnd*パラメーターを使用するメソッドオーバーロードは、oledb32.dll 内のサービスコンポーネントを持つデータソースオブジェクトを開きます。この DLL には、リソースプーリング、自動トランザクション参加などのサービスコンポーネント機能の実装が含まれています。 詳細については、『 [OLE DB プログラマーズガイド』](/previous-versions/windows/desktop/ms713643(v=vs.85))の OLE DB リファレンスを参照してください。

*HWnd*パラメーターを使用しないメソッドオーバーロードは、oledb32.dll のサービスコンポーネントを使用せずに、データソースオブジェクトを開きます。 これらの関数オーバーロードで開かれた [CDataSource](../../data/oledb/cdatasource-class.md) オブジェクトは、サービスコンポーネントの機能を使用できなくなります。

### <a name="example"></a>例

次のコードは、OLE DB テンプレートを使用して Jet 4.0 データ ソースを開く方法を示します。 Jet データ ソースは、OLE DB データ ソースとして扱います。 ただし、の呼び出しには、 `Open` DBPROPSET_DBINIT 用と DBPROPSET_JETOLEDB_DBINIT 用の2つのプロパティセットが必要であるため、DBPROP_JETOLEDB_DATABASEPASSWORD を設定できます。

[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]

## <a name="cdatasourceopenfromfilename"></a><a name="openfromfilename"></a> CDataSource:: OpenFromFileName

ユーザー指定のファイル名で指定されたファイルからデータ ソースを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();
```

#### <a name="parameters"></a>パラメーター

*szFileName*<br/>
[in] ファイル名、通常はデータ ソース接続 (.UDL) ファイル。

データリンクファイル (.udl ファイル) の詳細については、Windows SDK の「 [データリンク API の概要](/previous-versions/windows/desktop/ms718102(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。 詳細については、『 [OLE DB プログラマーズガイド』](/previous-versions/windows/desktop/ms713643(v=vs.85))の OLE DB リファレンスを参照してください。

## <a name="cdatasourceopenfrominitializationstring"></a><a name="openfrominitializationstring"></a> CDataSource:: OpenFromInitializationString

ユーザー指定の初期化文字列によって指定されたデータソースを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,
   bool fPromptForInfo= false) throw();
```

#### <a name="parameters"></a>パラメーター

*szInitializationString*<br/>
から初期化文字列。

*fPromptForInfo*<br/>
からこの引数がに設定さ **`true`** れている場合、 `OpenFromInitializationString` は、DBPROP_INIT_PROMPT プロパティを DBPROMPT_COMPLETEREQUIRED に設定します。これにより、詳細な情報が必要な場合にのみ、ユーザーに確認を求めるメッセージが表示されます。 これは、初期化文字列がパスワードを必要とするデータベースを指定し、その文字列にパスワードが含まれていない場合に便利です。 ユーザーは、データベースに接続しようとすると、パスワード (またはその他の不足している情報) の入力を求められます。

既定値は **`false`** で、ユーザーにプロンプトが表示されないことを指定します (DBPROP_INIT_PROMPT を DBPROMPT_NOPROMPT に設定します)。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。

## <a name="cdatasourceopenwithpromptfilename"></a><a name="openwithpromptfilename"></a> CDataSource:: OpenWithPromptFileName

このメソッドは、ダイアログ ボックスをユーザーに表示し、ユーザーが指定したファイルを使用してデータ ソースを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,
   LPCOLESTR szInitialDirectory = NULL) throw();
```

#### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[入力] ダイアログ ボックスの親であるウィンドウへのハンドル。

*dwPromptOptions*<br/>
[入力] 表示するロケーター ダイアログ ボックスのスタイルを指定します。 使用できる値については、Msdasc.h を参照してください。

*szInitialDirectory*<br/>
[入力] ロケーター ダイアログ ボックスに表示される初期ディレクトリ。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。 詳細については、『 [OLE DB プログラマーズガイド』](/previous-versions/windows/desktop/ms713643(v=vs.85))の OLE DB リファレンスを参照してください。

## <a name="cdatasourceopenwithservicecomponents"></a><a name="openwithservicecomponents"></a> CDataSource:: OpenWithServiceComponents

oledb32.dll 内のサービス コンポーネントを使用してデータ ソース オブジェクトを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);

HRESULT OpenWithServiceComponents (LPCSTR szProgID,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);
```

#### <a name="parameters"></a>パラメーター

*clsid*<br/>
から `CLSID` データプロバイダーの。

*szProgID*<br/>
[入力] データ プロバイダーのプログラム ID。

*pPropset*<br/>
から設定するプロパティと値を格納している [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体の配列へのポインター。 Windows SDK の*OLE DB プログラマーリファレンス*の「[プロパティセットとプロパティグループ](/previous-versions/windows/desktop/ms713696(v=vs.85))」を参照してください。 データ ソース オブジェクトが初期化されている場合、プロパティはデータ ソース プロパティ グループに属している必要があります。 *PPropset*で同じプロパティが複数回指定されている場合、使用される値はプロバイダー固有です。 *Ulpropsets*がゼロの場合、このパラメーターは無視されます。

*ulPropSets*<br/>
から*PPropSet*引数で渡される[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の数。 この値が0の場合、プロバイダーは *pPropset*を無視します。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>注釈

このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。 詳細については、『 [OLE DB プログラマーズガイド』](/previous-versions/windows/desktop/ms713643(v=vs.85))の OLE DB リファレンスを参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)

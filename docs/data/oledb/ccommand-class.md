---
title: CCommand クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
- CCommand.Close
- CCommand::Close
- CCommand.Create
- CCommand::Create
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
- CCommand.Prepare
- CCommand::Prepare
- Prepare
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
helpviewer_keywords:
- CCommand class
- Close method
- Create method [C++]
- CreateCommand method
- GetNextResult method
- GetParameterInfo method
- Open method
- Prepare method
- ReleaseCommand method
- SetParameterInfo method
- Unprepare method
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
ms.openlocfilehash: beabe73ff4ce0e6be8aaccfcdc636adc1ba04d5c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838439"
---
# <a name="ccommand-class"></a>CCommand クラス

コマンドを設定して実行するためのメソッドを提供します。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset,
   class TMultiple = CNoMultipleResults>
class CCommand :
   public CAccessorRowset <TAccessor, TRowset>,
   public CCommandBase,
   public TMultiple
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
コマンドで使用するアクセサークラスの型 ( `CDynamicParameterAccessor` 、 `CDynamicStringAccessor` 、またはなど `CEnumeratorAccessor` )。 既定値はです `CNoAccessor` 。これは、クラスがパラメーターまたは出力列をサポートしていないことを指定します。

*TRowset*<br/>
コマンドで使用する行セットクラスの型 ( `CArrayRowset` やなど `CNoRowset` )。 既定では、 `CRowset`です。

*TMultiple*<br/>
複数の結果を返すことができる OLE DB コマンドを使用するには、 [C乗数 Eresults](../../data/oledb/cmultipleresults-class.md)を指定します。 それ以外の場合は、 [Cno乗数 Eresults](../../data/oledb/cnomultipleresults-class.md)を使用します。 詳細については、「 [IMultipleResults](/previous-versions/windows/desktop/ms721289(v=vs.85))」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[閉じる](#close)|現在のコマンドを閉じます。|
|[GetNextResult](#getnextresult)|複数の結果セットを使用するときに、次の結果をフェッチします。|
|[[ファイル]](#open)|コマンドを実行し、必要に応じてバインドします。|

### <a name="inherited-methods"></a>継承されたメソッド

| 名前 | 説明 |
|-|-|
|[作成](#create)|指定されたセッションに対して新しいコマンドを作成し、コマンドテキストを設定します。|
|[CreateCommand](#createcommand)|新しいコマンドを作成します。|
|[GetParameterInfo](#getparameterinfo)|コマンドのパラメーターとその名前、およびその型の一覧を取得します。|
|[立て](#prepare)|現在のコマンドを検証して最適化します。|
|[ReleaseCommand](#releasecommand)|必要に応じてパラメーターアクセサーを解放してから、コマンドを解放します。|
|[SetParameterInfo](#setparameterinfo)|各コマンドパラメーターのネイティブな型を指定します。|
|[Unprepare](#unprepare)|現在のコマンド実行プランを破棄します。|

## <a name="remarks"></a>解説

このクラスは、パラメーターベースの操作を実行したり、コマンドを実行したりする必要がある場合に使用します。 単純な行セットを開く必要があるだけの場合は、代わりに [CTable](../../data/oledb/ctable-class.md) を使用します。

使用しているアクセサークラスによって、パラメーターとデータをバインドする方法が決まります。

OLE DB Provider for Jet でストアドプロシージャを使用することはできません。このプロバイダーではストアドプロシージャがサポートされていないためです (クエリ文字列では定数のみが許可されます)。

## <a name="ccommandclose"></a><a name="close"></a> CCommand:: Close

コマンドに関連付けられているアクセサー行セットを解放します。

### <a name="syntax"></a>構文

```cpp
void Close();
```

### <a name="remarks"></a>解説

コマンドは、行セット、結果セットアクセサー、および (必要に応じて) パラメーターアクセサーを使用します。これは、パラメーターをサポートせず、パラメーターアクセサーを必要としないテーブルとは異なります。

コマンドを実行するときは、 `Close` コマンドの後にと [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) の両方を呼び出す必要があります。

同じコマンドを繰り返し実行する場合は、を呼び出す前にを呼び出して、各結果セットアクセサーを解放する必要があり `Close` `Execute` ます。 シリーズの最後に、を呼び出してパラメーターアクセサーを解放する必要があり `ReleaseCommand` ます。 もう1つの一般的なシナリオは、出力パラメーターを持つストアドプロシージャを呼び出すことです。 多くのプロバイダー (SQL Server の OLE DB プロバイダーなど) では、結果セットのアクセサーを閉じるまで、出力パラメーターの値にはアクセスできません。 を呼び出して、 `Close` 返された行セットと結果セットアクセサーを閉じます。ただし、パラメーターアクセサーは使用しないため、出力パラメーターの値を取得できます。

### <a name="example"></a>例

次の例は、同じコマンドを繰り返し実行する場合に `Close` と `ReleaseCommand` を呼び出す方法を示しています。

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="ccommandgetnextresult"></a><a name="getnextresult"></a> CCommand:: GetNextResult

使用できる場合は、次の結果セットをフェッチします。

### <a name="syntax"></a>構文

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>パラメーター

*pulRowsAffected*<br/>
[入力/出力]コマンドの影響を受ける行の数を返すメモリへのポインターが返されます。

*bBind*<br/>
から実行後にコマンドを自動的にバインドするかどうかを指定します。 既定値はです **`true`** 。これにより、コマンドが自動的にバインドされます。 *Bbind*をに設定すると、コマンドが自動的にバインドされ **`false`** ず、手動でバインドできるようになります。 (手動バインドは OLAP ユーザーにとって特に重要です)。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

結果セットが既にフェッチされている場合、この関数は前の結果セットを解放し、列をバインド解除します。 *Bbind*がの場合は **`true`** 、新しい列をバインドします。

`CCommand`テンプレートパラメーター *tmultiple*を設定して複数の結果を指定した場合にのみ、この関数を呼び出す必要があり = `CMultipleResults` ます。

## <a name="ccommandopen"></a><a name="open"></a> CCommand:: Open

コマンドを実行し、必要に応じてバインドします。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   LPCSTR szCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   INT szCommand = NULL,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
からコマンドを実行するセッション。

*wszCommand*<br/>
から実行するコマンド。 Unicode 文字列として渡されます。 を使用する場合、NULL を指定できます `CAccessor` 。この場合、コマンドは [DEFINE_COMMAND](../../data/oledb/define-command.md) マクロに渡された値から取得されます。 詳細については、 *OLE DB プログラマーリファレンス*の「 [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) 」を参照してください。

*szCommand*<br/>
から *WszCommand* と同じですが、このパラメーターは ANSI コマンド文字列を受け取る点が異なります。 このメソッドの4番目の形式は、NULL 値を受け取ることができます。 詳細については、このトピックで後述する「解説」を参照してください。

*pPropSet*<br/>
から設定するプロパティと値を格納している [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体の配列へのポインター。 Windows SDK の*OLE DB プログラマーリファレンス*の「[プロパティセットとプロパティグループ](/previous-versions/windows/desktop/ms713696(v=vs.85))」を参照してください。

*pRowsAffected 影響を受けた*<br/>
[入力/出力]コマンドの影響を受ける行の数を返すメモリへのポインターが返されます。 * \* Prowsaffected を受け*たが NULL の場合、行数は返されません。 それ以外の場合は、 `Open` 次の条件に従って、適用される* \* prowsaffected*設定します。

|状況|THEN|
|--------|----------|
|`cParamSets`の要素 `pParams` が1を超えています。|* \* prowsaffected* 、実行時に指定されたすべてのパラメーターセットの影響を受ける行の合計数を表します。|
|影響を受ける行の数は使用できません|* \* prowsaffected* -1 に設定されています。|
|このコマンドでは、行の更新、削除、または挿入は行われません。|* \* 影響を受ける prowsaffected*定義されていません。|

*guidCommand*<br/>
からコマンドテキストの解析に使用するプロバイダーの構文と一般的な規則を指定する GUID。 詳細については*OLE DB プログラマーリファレンス*の「 [ICommandText:: Getcommandtext](/previous-versions/windows/desktop/ms709825(v=vs.85)) And [ICommandText:: setcommandtext](/previous-versions/windows/desktop/ms709757(v=vs.85)) 」を参照してください。

*bBind*<br/>
から実行後にコマンドを自動的にバインドするかどうかを指定します。 既定値はです **`true`** 。これにより、コマンドが自動的にバインドされます。 *Bbind*をに設定すると、コマンドが自動的にバインドされ **`false`** ず、手動でバインドできるようになります。 (手動バインドは OLAP ユーザーにとって特に重要です)。

*ulPropSets*<br/>
から*PPropSet*引数で渡される[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の数。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

最初の3つの形式は、セッションを取得し、 `Open` コマンドを作成し、必要に応じてパラメーターをバインドして、コマンドを実行します。

の最初の形式は `Open` Unicode コマンド文字列を受け取り、既定値はありません。

2番目の形式のは `Open` ansi コマンド文字列を受け取り、既定値はありません (既存の ANSI アプリケーションとの旧バージョンとの互換性のために用意されています)。

の3番目の形式では、 `Open` コマンド文字列を null にすることができます。これは、型の既定値が null であるため **`int`** です。 またはを呼び出すために用意されてい `Open(session, NULL);` `Open(session);` ます。 NULL は型 **`int`** です。 このバージョンでは、パラメーターが NULL であることを要求し、アサートし **`int`** ます。

`Open`コマンドが既に作成されていて、1回の[準備](../../data/oledb/ccommand-prepare.md)と複数の実行を実行する場合は、の4番目の形式を使用します。

> [!NOTE]
> `Open``Execute`はを呼び出し、はを呼び出し `GetNextResult` ます。

## <a name="ccommandcreate"></a><a name="create"></a> CCommand:: Create

[CCommand:: CreateCommand](../../data/oledb/ccommand-createcommand.md)を呼び出して、指定されたセッションのコマンドを作成し、 [ICommandText:: setcommandtext](/previous-versions/windows/desktop/ms709825(v=vs.85))を呼び出してコマンドテキストを指定します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::Create(const CSession& session,
   LPCWSTR wszCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();

HRESULT CCommandBase::Create(const CSession& session,
   LPCSTR szCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
からコマンドを作成するセッション。

*wszCommand*<br/>
からコマンド文字列の Unicode テキストへのポインター。

*szCommand*<br/>
からコマンド文字列の ANSI テキストへのポインター。

*guidCommand*<br/>
からコマンドテキストの解析に使用するプロバイダーの構文と一般的な規則を指定する GUID。 ダイアレクトの詳細については、 *OLE DB プログラマーリファレンス*の「 [ICommandText:: getcommandtext](/previous-versions/windows/desktop/ms709825(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

の最初の形式は、 `Create` Unicode のコマンド文字列を受け取ります。 の2番目の形式は、 `Create` ansi コマンド文字列を受け取ります (既存の ansi アプリケーションとの下位互換性のために用意されています)。

## <a name="ccommandcreatecommand"></a><a name="createcommand"></a> CCommand:: CreateCommand

新しいコマンドを作成します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
から `CSession` 新しいコマンドに関連付けられるオブジェクト。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

このメソッドは、指定されたセッションオブジェクトを使用してコマンドを作成します。

## <a name="ccommandgetparameterinfo"></a><a name="getparameterinfo"></a> CCommand:: GetParameterInfo

コマンドのパラメーターとその名前、およびその型の一覧を取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [ICommandWithParameters:: getparameterinfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="ccommandprepare"></a><a name="prepare"></a> CCommand::P repare

現在のコマンドを検証して最適化します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>パラメーター

*cExpectedRuns*<br/>
からコマンドの実行に予想される回数。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

このメソッドは、OLE DB メソッド [ICommandPrepare::P repare](/previous-versions/windows/desktop/ms718370(v=vs.85))をラップします。

## <a name="ccommandreleasecommand"></a><a name="releasecommand"></a> CCommand:: ReleaseCommand

パラメーターアクセサーを解放してから、コマンド自体を解放します。

### <a name="syntax"></a>構文

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>解説

`ReleaseCommand` は、と組み合わせて使用され `Close` ます。 詳細については、「 [Close](../../data/oledb/ccommand-close.md) 」を参照してください。

## <a name="ccommandsetparameterinfo"></a><a name="setparameterinfo"></a> CCommand:: SetParameterInfo

各コマンドパラメーターのネイティブな型を指定します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [ICommandWithParameters:: setparameterinfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="ccommandunprepare"></a><a name="unprepare"></a> CCommand:: Unprepare

現在のコマンド実行プランを破棄します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

このメソッドは、OLE DB メソッド [ICommandPrepare:: Unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85))をラップします。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)

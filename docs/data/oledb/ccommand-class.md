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
ms.openlocfilehash: 52c7e2ce5acdd2df33e2a6422535a337f0a43aec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368631"
---
# <a name="ccommand-class"></a>CCommand クラス

コマンドを設定および実行するメソッドを提供します。

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

*Tアクセサー*<br/>
コマンドで使用するアクセサー クラス`CDynamicParameterAccessor`の`CDynamicStringAccessor`型`CEnumeratorAccessor`( 、 、 など) を指定します。 既定では`CNoAccessor`、 クラスがパラメーターまたは出力列をサポートしないことを指定します。

*TRowset*<br/>
コマンドで使用する行セット クラスの`CArrayRowset`型`CNoRowset`( または など ) を指定します。 既定では、 `CRowset`です。

*多重*<br/>
複数の結果を返すことができる OLE DB コマンドを使用するには[、CMultipleResults](../../data/oledb/cmultipleresults-class.md)を指定します。 それ以外の場合は[、CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)を使用します。 詳細については、「[複数の結果」](/previous-versions/windows/desktop/ms721289(v=vs.85))を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[閉じる](#close)|現在のコマンドを閉じます。|
|[次の結果を取得します。](#getnextresult)|複数の結果セットを使用する場合に、次の結果をフェッチします。|
|[開く](#open)|コマンドを実行し、オプションでバインドします。|

### <a name="inherited-methods"></a>継承されたメソッド

|||
|-|-|
|[作成](#create)|指定したセッションに対して新しいコマンドを作成し、コマンド テキストを設定します。|
|[CreateCommand](#createcommand)|新しいコマンドを作成します。|
|[パラメーターの情報](#getparameterinfo)|コマンドのパラメーター、名前、および型の一覧を取得します。|
|[準備](#prepare)|現在のコマンドを検証および最適化します。|
|[コマンドをリリースします。](#releasecommand)|必要に応じてパラメータ アクセサーを解放し、コマンドを解放します。|
|[パラメーターの情報を設定します。](#setparameterinfo)|各コマンド パラメーターのネイティブの型を指定します。|
|[準備を解除する](#unprepare)|現在のコマンド実行プランを破棄します。|

## <a name="remarks"></a>解説

このクラスは、パラメータベースの操作を実行する必要がある場合や、コマンドを実行する必要がある場合に使用します。 単純な行セットを開くだけの場合は、代わりに[CTable を](../../data/oledb/ctable-class.md)使用します。

使用するアクセサー クラスによって、パラメーターとデータのバインド方法が決まります。

プロバイダがストアド プロシージャをサポートしていないため、ストアド プロシージャを使用することはできません ( クエリ文字列で定数のみ使用できます ) 。

## <a name="ccommandclose"></a><a name="close"></a>Cコマンド::閉じる

コマンドに関連付けられているアクセサ行セットを解放します。

### <a name="syntax"></a>構文

```cpp
void Close();
```

### <a name="remarks"></a>解説

コマンドは、行セット、結果セット アクセサー、および (オプションで) パラメーター アクセサー (テーブルとは異なり、パラメーターアクセサーをサポートせず、パラメーター アクセサーは必要ありません) を使用します。

コマンドを実行する場合は、コマンドの後`Close`に、および[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)の両方を呼び出す必要があります。

同じコマンドを繰り返し実行する場合は、 を呼び出す前`Close`に、`Execute`各 Result set アクセサーを呼び出して解放する必要があります。 シリーズの最後に、 を呼び出`ReleaseCommand`してパラメーター アクセサーを解放する必要があります。 もう 1 つの一般的なシナリオは、出力パラメーターを持つストアド プロシージャを呼び出す場合です。 多くのプロバイダ (SQL Server の OLE DB プロバイダなど) では、結果セット アクセサーを閉じるまで出力パラメータ値にアクセスできません。 返`Close`された行セットと結果セット アクセサーを閉じる呼び出しは、パラメーター アクセサーを閉じるため、出力パラメーター値を取得できます。

### <a name="example"></a>例

次の例は、同じコマンドを繰り返し実行する場合に `Close` と `ReleaseCommand` を呼び出す方法を示しています。

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="ccommandgetnextresult"></a><a name="getnextresult"></a>次の結果を取得します。

次の結果セットが使用可能な場合は、その結果セットをフェッチします。

### <a name="syntax"></a>構文

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>パラメーター

*影響を受けるプロウ*<br/>
[イン/アウト]コマンドの影響を受ける行数が返されるメモリへのポインター。

*bバインド*<br/>
[in]コマンドの実行後に自動的にバインドするかどうかを指定します。 デフォルトは**true で**、コマンドは自動的にバインドされます。 *bBind*を**false**に設定すると、コマンドの自動バインドが行われなくなり、手動でバインドできるようになります。 (OLAP ユーザーには、手動バインドが特に必要です)。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

結果セットが既にフェッチされている場合、この関数は前の結果セットを解放し、列をアンバインドします。 *bBind*が**true**の場合、新しい列がバインドされます。

この関数を呼び出す必要があるのは、テンプレート パラメータ`CCommand`*TMultiple*=`CMultipleResults`を設定して複数の結果を指定した場合だけです。

## <a name="ccommandopen"></a><a name="open"></a>Cコマンド::オープン

コマンドを実行し、オプションでバインドします。

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
[in]コマンドを実行するセッション。

*コマンド*<br/>
[in]Unicode 文字列として渡される実行するコマンド。 を使用`CAccessor`する場合は NULL を指定できますが、その場合、コマンドは[DEFINE_COMMAND](../../data/oledb/define-command.md)マクロに渡された値から取得されます。 詳細については *、OLE DB プログラマ リファレンス*の[ICommand::Execute](/previous-versions/windows/desktop/ms718095(v=vs.85))を参照してください。

*コマンド*<br/>
[in]このパラメーターが ANSI コマンド文字列を受け取る点を除いて *、wszCommand*と同じです。 このメソッドの 4 番目の形式は NULL 値を受け取ることができます。 詳細については、このトピックの「解説」を参照してください。

*pPropSet*<br/>
[in]設定するプロパティと値を含む[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の配列へのポインター。 Windows SDK の *「OLE DB プログラマ*リファレンス」の[「プロパティ セットとプロパティ グループ](/previous-versions/windows/desktop/ms713696(v=vs.85))」を参照してください。

*影響を受ける*<br/>
[イン/アウト]コマンドの影響を受ける行数が返されるメモリへのポインター。 * \*pRowsAffected*が NULL の場合、行カウントは返されません。 それ以外`Open`の場合は、次の条件に従って*\*pRowsAffected*を設定します。

|状況|THEN|
|--------|----------|
|の`cParamSets`要素`pParams`が 1 より大きい|pRowsAffected は、実行で指定されたすべてのパラメーター セットによって影響を受ける行の合計数を表します。 * \**|
|影響を受ける行の数が利用できません|pRowsAffected は -1 に設定されます。 * \**|
|コマンドは行を更新、削除、または挿入しません。|pRowsAffected は未定義です。 * \**|

*ガイドコマンド*<br/>
[in]コマンド テキストの解析で使用するプロバイダーの構文と一般的な規則を指定する GUID。 詳細については *、OLE DB プログラマーズ リファレンス*の[ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85))と I コマンド テキストを参照してください。 [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85))

*bバインド*<br/>
[in]コマンドの実行後に自動的にバインドするかどうかを指定します。 デフォルトは**true で**、コマンドは自動的にバインドされます。 *bBind*を**false**に設定すると、コマンドの自動バインドが行われなくなり、手動でバインドできるようになります。 (OLAP ユーザーには、手動バインドが特に必要です)。

*ウルプロップセット*<br/>
[in]引数[pPropSet で](/previous-versions/windows/desktop/ms714367(v=vs.85))渡された*DBPROPSET*構造体の数。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

最初の 3`Open`つの形式は、セッションを取り、コマンドを作成し、コマンドを実行して、必要に応じてパラメーターをバインドします。

最初の形式の`Open`Unicode コマンド文字列を使用し、既定値はありません。

2 番目の`Open`形式の ANSI コマンド文字列を使用し、デフォルト値を使用しません (既存の ANSI アプリケーションとの下位互換性のために提供されます)。

3 番目の`Open`形式では、int 型の既定値が**int**NULL であるため、コマンド文字列を NULL にできます。 これは、呼び出`Open(session, NULL);`し`Open(session);`用に提供されているか、NULL が**int**型であるためです。このバージョンでは **、int**パラメータが NULL であることが必要です。

コマンドを既に作成`Open`し、1 回の[準備](../../data/oledb/ccommand-prepare.md)と複数の実行を実行する場合は、4 番目の形式を使用します。

> [!NOTE]
> `Open`を`Execute`呼び出し、`GetNextResult`を呼び出します。

## <a name="ccommandcreate"></a><a name="create"></a>Cコマンド::作成

[CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md)を呼び出して指定したセッションのコマンドを作成し、コマンド テキストを指定する[ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85))を呼び出します。

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
[in]コマンドを作成するセッション。

*コマンド*<br/>
[in]コマンド文字列の Unicode テキストへのポインター。

*コマンド*<br/>
[in]コマンド文字列の ANSI テキストへのポインター。

*ガイドコマンド*<br/>
[in]コマンド テキストの解析で使用するプロバイダーの構文と一般的な規則を指定する GUID。 方言の詳細については *、OLE DB プログラマ リファレンス*の[ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85))を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

最初の形式は`Create`Unicode コマンド文字列を受け取ります。 2 番目の`Create`形式の ANSI コマンド文字列 (既存の ANSI アプリケーションとの下位互換性のために用意されています) を使用します。

## <a name="ccommandcreatecommand"></a><a name="createcommand"></a>コマンド::コマンドを作成します。

新しいコマンドを作成します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
[in]新`CSession`しいコマンドに関連付けるオブジェクト。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

このメソッドは、指定されたセッション オブジェクトを使用してコマンドを作成します。

## <a name="ccommandgetparameterinfo"></a><a name="getparameterinfo"></a>コマンド::パラメーターの情報

コマンドのパラメーター、名前、および型の一覧を取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>パラメーター

OLE DB プログラマーズ リファレンス の[「ICommandWithParameters::GetParameterInfo」](/previous-versions/windows/desktop/ms714917(v=vs.85))を*参照してください*。

### <a name="return-value"></a>戻り値

標準の HRESULT。

## <a name="ccommandprepare"></a><a name="prepare"></a>Cコマンド::Pレパレ

現在のコマンドを検証および最適化します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>パラメーター

*期待される実行*<br/>
[in]コマンドの実行を予想する回数。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

このメソッドは、OLE DB メソッド[:Pを](/previous-versions/windows/desktop/ms718370(v=vs.85))ラップします。

## <a name="ccommandreleasecommand"></a><a name="releasecommand"></a>コマンド::リリースコマンド

パラメーター アクセサーを解放し、コマンド自体を解放します。

### <a name="syntax"></a>構文

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>解説

`ReleaseCommand`は と組み`Close`合わせて使用されます。 使用法の詳細については[、閉じる](../../data/oledb/ccommand-close.md)を参照してください。

## <a name="ccommandsetparameterinfo"></a><a name="setparameterinfo"></a>コマンド::パラメーターの情報を設定します。

各コマンド パラメーターのネイティブの型を指定します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>パラメーター

OLE DB プログラマーズ リファレンス の[「ICommandWithParameters::SetParameterInfo」](/previous-versions/windows/desktop/ms725393(v=vs.85))を*参照してください*。

### <a name="return-value"></a>戻り値

標準の HRESULT。

## <a name="ccommandunprepare"></a><a name="unprepare"></a>コマンド::準備を解除する

現在のコマンド実行プランを破棄します。

### <a name="syntax"></a>構文

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

このメソッドは、OLE DB メソッドをラップします[。](/previous-versions/windows/desktop/ms719635(v=vs.85))

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)

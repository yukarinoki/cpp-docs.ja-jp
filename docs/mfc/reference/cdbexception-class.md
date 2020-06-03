---
title: CDBException クラス
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: 1ab7daeb3af55c92985c951c632b1d4050681474
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321894"
---
# <a name="cdbexception-class"></a>CDBException クラス

データベース クラスから発生する例外状態を表現します。

## <a name="syntax"></a>構文

```
class CDBException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[例外::m_nRetCode](#m_nretcode)|タイプ RETCODE のオープン データベース接続 (ODBC) リターン コードが含まれています。|
|[例外:m_strError](#m_strerror)|エラーを英数字で説明する文字列を含みます。|
|[例外:m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC によって返されるエラー コードの観点から、エラーを説明する文字列を含みます。|

## <a name="remarks"></a>解説

このクラスには、例外の原因を特定したり、例外を説明するテキスト メッセージを表示したりするために使用できる 2 つのパブリック データ メンバーが含まれています。 `CDBException`オブジェクトは、データベース クラスのメンバー関数によって構築およびスローされます。

> [!NOTE]
> このクラスは、MFC のオープン データベース接続 (ODBC) クラスの 1 つです。 代わりに新しいデータ アクセス オブジェクト (DAO) クラスを使用する場合は、代わりに[CDaoException を使用します](../../mfc/reference/cdaoexception-class.md)。 DAO クラス名はすべてプレフィックスとして "CDao" を持ちます。 詳細については、「[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

例外は、データ・ソースやネットワーク入出力エラーなど、プログラムの制御外の状態を伴う異常実行の場合です。 通常、プログラムの実行過程で発生する可能性のあるエラーは、例外とは見なされません。

CATCH**式の**スコープ内でこれらのオブジェクトにアクセスできます。 グローバル関数を使用`CDBException`して、独自のコードからオブジェクト`AfxThrowDBException`をスローすることもできます。

例外処理全般または`CDBException`オブジェクトの詳細については、「[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md) 」および「[例外: データベース例外](../../mfc/exceptions-database-exceptions.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="cdbexceptionm_nretcode"></a><a name="m_nretcode"></a>例外::m_nRetCode

ODBC アプリケーション・プログラミング・インターフェース (API) 関数によって戻されるタイプ RETCODE の ODBC エラー・コードを含みます。

### <a name="remarks"></a>解説

この型には、ODBC で定義された SQL プレフィックスコードと、データベース クラスによって定義されるAFX_SQLプレフィックスコードが含まれます。 の場合`CDBException`、このメンバには次のいずれかの値が含まれます。

- AFX_SQL_ERROR_API_CONFORMANCE または`CDatabase::Open`呼び`CDatabase::OpenEx`出しのドライバーが、必要な ODBC API 準拠レベル 1 (SQL_OAC_LEVEL1) に準拠していません。

- AFX_SQL_ERROR_CONNECT_FAIL データ ソースへの接続に失敗しました。 レコードセット コンストラクター`CDatabase`に NULL ポインタを渡し、その後に失敗した`GetDefaultConnect`接続を作成しようとしました。

- AFX_SQL_ERROR_DATA_TRUNCATED ストレージを指定したデータよりも多くのデータを要求しました。 `CString`データ型または`CByteArray`データ型に対して提供されるデータ ストレージを増`nMaxLength`やす方法については、「マクロとグローバル」の[RFX_Text](record-field-exchange-functions.md#rfx_text)と[RFX_Binary](record-field-exchange-functions.md#rfx_binary)の引数を参照してください。

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED ダイナ`CRecordset::Open`セットの要求に失敗しました。 ダイナセットはドライバでサポートされていません。

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST テーブルを開こうとしましたが (または指定したものをプロシージャ呼び出しまたは**SELECT**ステートメントとして識別できませんでした)、`DoFieldExchange`上書きのレコード フィールド エクスチェンジ (RFX) 関数呼び出しで識別される列がありません。

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH`DoFieldExchange`オーバーライドの RFX 関数の型が、レコードセットの列データ型と互換性がありません。

- AFX_SQL_ERROR_ILLEGAL_MODE 以前`CRecordset::Update`に呼び`CRecordset::AddNew`出`CRecordset::Edit`したり、 を呼び出さずに呼び出したのです。

- AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED ODBC ドライバがロックをサポートしていないため、更新用のレコードをロックする要求を満たしていません。

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED 一`CRecordset::Update`意`Delete`のキーを持たないテーブルを呼び出したり、複数のレコードを変更したりした場合。

- AFX_SQL_ERROR_NO_CURRENT_RECORD 以前に削除したレコードを編集または削除しようとしました。 削除後に、新しいカレント レコードまでスクロールする必要があります。

- AFX_SQL_ERROR_NO_POSITIONED_UPDATES ODBC ドライバーが位置指定更新をサポートしていないため、ダイナセットの要求を満たしませんでした。

- AFX_SQL_ERROR_NO_ROWS_AFFECTED または`CRecordset::Update``Delete`に電話しましたが、操作が開始されたときにレコードが見つかりませんでした。

- AFX_SQL_ERROR_ODBC_LOAD_FAILED ODBC を読み込もうとしました。DLL が失敗しました。この DLL が見つからないか、または読み込めませんでした。 このエラーは致命的です。

- AFX_SQL_ERROR_ODBC_V2_REQUIRED レベル 2 準拠の ODBC ドライバーが必要なため、ダイナセットの要求を満たしませんでした。

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY データ ソースが後方スクロールをサポートしていないため、スクロールできませんでした。

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED スナップショットの`CRecordset::Open`要求の呼び出しに失敗しました。 スナップショットはドライバによってサポートされていません。 (これは ODBC カーソル ライブラリ ODBCCURS の場合にのみ発生します。DLL が存在しません。

- AFX_SQL_ERROR_SQL_CONFORMANCE または`CDatabase::Open`呼び`CDatabase::OpenEx`出しのドライバーが、必要な ODBC SQL 準拠レベル "最小" (SQL_OSC_MINIMUM) に準拠していません。

- AFX_SQL_ERROR_SQL_NO_TOTAL ODBC ドライバはデータ値の合計サイズを`CLongBinary`指定できませんでした。 グローバル メモリ ブロックを事前に割り当てることができなかったため、操作が失敗した可能性があります。

- AFX_SQL_ERROR_RECORDSET_READONLY読み取り専用のレコードセットを更新しようとしたか、データ ソースが読み取り専用です。 レコードセットまたは関連付けられているオブジェクトでは`CDatabase`、更新操作を実行できません。

- SQL_ERROR関数に失敗しました。 ODBC 関数`SQLError`によって返されるエラー メッセージは、データ`m_strError`メンバーに格納されます。

- SQL_INVALID_HANDLE無効な環境ハンドル、接続ハンドル、またはステートメント ハンドルが原因で関数が失敗しました。 これは、プログラミング エラーを示します。 ODBC 関数`SQLError`から追加の情報を入手できません。

SQL プレフィックスコードは ODBC によって定義されます。 AFX プレフィックスのコードは AFXDB で定義されます。H、 MFC\INCLUDE で見つかりました。

## <a name="cdbexceptionm_strerror"></a><a name="m_strerror"></a>例外:m_strError

例外の原因となったエラーを説明する文字列を含みます。

### <a name="remarks"></a>解説

この文字列は、エラーを英数字で表します。 詳細と例については、を参照してください`m_strStateNativeOrigin`。

## <a name="cdbexceptionm_strstatenativeorigin"></a><a name="m_strstatenativeorigin"></a>例外:m_strStateNativeOrigin

例外の原因となったエラーを説明する文字列を含みます。

### <a name="remarks"></a>解説

文字列は "State:%s,Native:%ld,Origin:%s" の形式で、書式コードは次の内容を記述する値に置き換えられます。

- SQLSTATE は、ODBC 関数`SQLError`の*szSqlState*パラメーターに返される 5 文字のエラー コードを含む NULL で終わる文字列です。 SQLSTATE の値は[、ODBC](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes)プログラマ リファレンス の付録 A ODBC エラー コード に記載*されています*。 例: "S0022"。

- `SQLError`関数の*pfNativeError*パラメーターに返される、データ ソースに固有のネイティブ エラー コード。 例: 207。

- 関数の*szErrorMsg*パラメーターに返されるエラー`SQLError`メッセージ テキスト。 このメッセージは、複数の角括弧で囲まれた名前で構成されます。 エラーがソースからユーザーに渡されると、各 ODBC コンポーネント (データ ソース、ドライバー、ドライバー マネージャー) が独自の名前を追加します。 この情報は、エラーの原因を特定するのに役立ちます。 例: [マイクロソフト][ODBC SQL サーバー ドライバー][SQL サーバー]

フレームワークはエラー文字列を解釈し、そのコンポーネントを`m_strStateNativeOrigin`に置きます。複数`m_strStateNativeOrigin`のエラーの情報が含まれている場合、エラーは改行で区切られます。 フレームワークは、英数字のエラー テキスト`m_strError`を に挿入します。

この文字列を構成するために使用されるコードの詳細については、『ODBC プログラマ リファレンス』の[SQLError](/sql/odbc/reference/syntax/sqlerror-function)関数*を参照してください*。

### <a name="example"></a>例

ODBC から: "状態:S0022,ネイティブ:207,\[起源:\[ODBC SQL\[Server ドライバー] SQL サーバー] 無効な列名 'ColName'"

で`m_strStateNativeOrigin`: "状態:S0022,ネイティブ:207,\[起源:\[マイクロソフト] ODBC\[SQLサーバードライバ] SQLサーバー]

In `m_strError`: "無効な列名 'ColName' "

## <a name="see-also"></a>関連項目

[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdatabase-class.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)<br/>
[クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[レコードセット::更新](../../mfc/reference/crecordset-class.md#update)<br/>
[Cレコード::D](../../mfc/reference/crecordset-class.md#delete)<br/>
[クラスの例外](../../mfc/reference/cexception-class.md)

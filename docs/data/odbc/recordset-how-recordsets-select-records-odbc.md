---
title: 'レコード セット: レコード選択が (ODBC) を記録する方法 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2f1f5ba7da2e2e61de9356b82f51bc9f2ef1cce9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055542"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>レコードセット: レコード選択のしくみ (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [ロールとレコードを選択すると、オプション](#_core_your_options_in_selecting_records)します。

- [レコード セットの生成する SQL ステートメントとレコードの選択](#_core_how_a_recordset_constructs_its_sql_statement)します。

- [選択範囲のカスタマイズを行うことができます](#_core_customizing_the_selection)します。

レコード セットは、ドライバーに SQL ステートメントを送信することによって、ODBC ドライバーを通じてデータ ソースからレコードを選択します。 送信される SQL は、設計方法と、レコード セット クラスを開きますかによって異なります。

##  <a name="_core_your_options_in_selecting_records"></a> レコードの選択

次の表では、レコードを選択するときのオプションを示します。

### <a name="how-and-when-you-can-affect-a-recordset"></a>レコード セットの影響を与えることができる方法とタイミング

|ときにします。|できます|
|--------------|-------------|
|使用してレコード セット クラスの宣言、**クラスの追加**ウィザード|選択するテーブルを指定します。<br /><br /> 含める列を指定します。<br /><br /> 参照してください[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)します。|
|レコード セット クラスの実装を完了します。|など、メンバー関数をオーバーライド`OnSetOptions`アプリケーション固有のオプションを設定するか、既定値を変更する (詳細)。 パラメーター化されたレコード セットの場合は、パラメーター データ メンバーを指定します。|
|レコード セット オブジェクトを作成する (呼び出す前に`Open`)|検索条件 (場合によっては複合) で使用するための指定、**場所**レコードをフィルター処理する句。 参照してください[レコード セット: レコード (ODBC) のフィルター処理](../../data/odbc/recordset-filtering-records-odbc.md)します。<br /><br /> 使用するための並べ替え順序を指定する**ORDER BY**並べ替え句。 参照してください[レコード セット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)します。<br /><br /> クラスに追加するすべてのパラメーターのパラメーターの値を指定します。 参照してください[レコード セット: レコード セット (ODBC) をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)します。|

|レコード セットのクエリを呼び出すことによって実行`Open`|セットアップ ウィザードで既定の SQL 文字列を置換するカスタム SQL 文字列を指定します。 参照してください[:open](../../mfc/reference/crecordset-class.md#open)で、*クラス ライブラリ リファレンス*と[SQL: レコード セットの SQL ステートメント (ODBC) のカスタマイズ](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)|。

|呼び出す`Requery`データ ソースの最新の値でクエリを再実行する |新しいパラメーター、フィルター、または並べ替えを指定します。 参照してください[レコード セット: レコード セット (ODBC) のクエリを再実行](../../data/odbc/recordset-requerying-a-recordset-odbc.md)|。

##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> レコード セットが、SQL ステートメントを作成する方法

レコード セット オブジェクトを呼び出すと[オープン](../../mfc/reference/crecordset-class.md#open)メンバー関数は、`Open`以下のデータの一部またはすべてを使用して SQL ステートメントの作成します。

- *LpszSQL*に渡されるパラメーター`Open`します。 NULL 以外の場合、このパラメーターは、カスタム SQL 文字列またはいずれかの一部を指定します。 フレームワークは、文字列を解析します。 文字列が SQL の場合**選択**ステートメントまたは ODBC**呼び出す**ステートメントでは、フレームワークは、レコード セットの SQL ステートメントとして文字列を使用します。 SQL の構築に供給される文字列が"SELECT"または"{CALL"で始まっていない場合、フレームワークには使用**FROM**句。

- によって返される文字列[GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)します。 既定では、これは、ウィザードで、レコード セットの指定したテーブルの名前が、関数が返すを変更することができます。 Framework 呼び出し`GetDefaultSQL`: 文字列が"SELECT"または"{CALL"で始まっていない場合、SQL 文字列を構築するために使用するテーブル名を指定すると見なされます。


- フィールド データ メンバー、レコード セットのテーブルの特定の列にバインドするのには。 フレームワークは、バッファーとしてそれらを使用して、これらのメンバーのアドレスに、レコードの列をバインドします。 フレームワークからテーブル列をフィールド データ メンバーの相関関係の決定、 [RFX](../../data/odbc/record-field-exchange-using-rfx.md)またはレコード セットのバルク RFX 関数を呼び出す[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)メンバー関数。

- [フィルター](../../data/odbc/recordset-filtering-records-odbc.md) 、レコード セットに存在する場合に含まれる、[か](../../mfc/reference/crecordset-class.md#m_strfilter)データ メンバー。 フレームワークでは、この文字列を使用して、SQL の構築**場所**句。

- [並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)、いずれかに含まれる場合、レコード セットの順序、[レコード](../../mfc/reference/crecordset-class.md#m_strsort)データ メンバー。 フレームワークでは、この文字列を使用して、SQL の構築**ORDER BY**句。


    > [!TIP]
    >  SQL を使用する**GROUP BY**句 (および場合によって、 **HAVING**句)、フィルター文字列の末尾に句を追加します。

- 値を[パラメーター データ メンバー](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)クラスを指定します。 呼び出す直前に、パラメーター値を設定する`Open`または`Requery`します。 フレームワークにバインドするパラメーターの値"?"SQL 文字列内のプレース ホルダーです。 コンパイル時に、プレース ホルダーを含む文字列を指定します。 フレームワークは、実行時に渡すパラメーターの値に基づいて詳細で塗りつぶします。

`Open` SQL を構築します**選択**ステートメントこれらの構成要素から。 参照してください[選択範囲をカスタマイズする](#_core_customizing_the_selection)詳細については、フレームワークが、構成要素を使用する方法について。

ステートメントを構築した後`Open`ODBC ドライバー マネージャー (およびメモリ内にある場合、ODBC カーソル ライブラリ) に、SQL を送信します。 特定の DBMS の ODBC ドライバーに送信します。 ドライバーは、データ ソースの選択項目に、実行するために DBMS と通信し、最初のレコードをフェッチします。 フレームワークは、レコード セットのフィールド データ メンバーに、レコードを読み込みます。

これらの手法の組み合わせを使用して開くことができます[テーブル](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)に基づいてクエリを作成して、[結合](../../data/odbc/recordset-performing-a-join-odbc.md)の複数のテーブル。 呼び出すことができます、さらにカスタマイズ[の定義済みクエリ](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)(ストアド プロシージャ) 選択テーブルの列がデザイン時に不明と[バインド](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)にレコード セット フィールドまたは他の大半を実行できますデータ アクセス タスク。 はまだレコード セットをカスタマイズすることで実現できないタスクを行うことができます[ODBC API 関数を呼び出して](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)を持つ SQL ステートメントを直接実行または[:executesql](../../mfc/reference/cdatabase-class.md#executesql)します。

##  <a name="_core_customizing_the_selection"></a> 選択範囲をカスタマイズします。

フィルター、並べ替え順、またはパラメーターを指定して、だけでなく、レコード セットの選択をカスタマイズするには、次の操作を実行できます。

- カスタム SQL 文字列を渡す*lpszSQL*を呼び出すと[オープン](../../mfc/reference/crecordset-class.md#open)のレコード セット。 何かを渡す*lpsqSQL*ものよりも優先、 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)メンバー関数を返します。

   詳細については、次を参照してください。 [SQL: の SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)、型について説明する SQL ステートメント (または部分的なステートメント) に渡すことができます`Open`とそれには、フレームワーク。

    > [!NOTE]
    >  指定したカスタムの文字列が"SELECT"または"{CALL"で始まっていない場合、MFC テーブル名が含まれている前提としています。 これは、次の項目にも適用されます。

- ウィザードで生成したレコード セットの文字列を alter`GetDefaultSQL`メンバー関数。 返される内容を変更するのには関数のコードを編集します。 既定では、ウィザードが書き込まれます、`GetDefaultSQL`を 1 つのテーブル名を返す関数。

   した`GetDefaultSQL`で渡すことができる項目のいずれかを返す、 *lpszSQL*パラメーターを`Open`します。 カスタム SQL 文字列を渡さないかどうか*lpszSQL*、フレームワークは、文字列を使用している`GetDefaultSQL`を返します。 少なくとも`GetDefaultSQL`1 つのテーブル名を返す必要があります。 完全な複数のテーブル名を返すことができますが、**選択**ステートメントでは、ODBC**を呼び出す**ステートメントでは、という具合です。 渡すことができますの一覧については*lpszSQL* - かが`GetDefaultSQL`を返すを参照してください[SQL: の SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)します。

   2 つ以上のテーブルの結合を実行している場合は、書き換え`GetDefaultSQL`SQL で使用されるテーブルのリストをカスタマイズする**FROM**句。 詳細については、次を参照してください。[レコード セット: 結合 (ODBC) を実行する](../../data/odbc/recordset-performing-a-join-odbc.md)します。


- 取得するスキーマについては、データ ソースの実行時に基づくなど、追加のフィールド データ メンバーを手動でバインドします。 フィールド データ メンバーをレコード セット クラスに追加する[RFX](../../data/odbc/record-field-exchange-using-rfx.md)またはバルク RFX 関数の呼び出しに、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)メンバー関数、およびクラスのコンス トラクター内のデータ メンバーの初期化。 詳細については、次を参照してください。[レコード セット: データ列を動的にバインド (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)します。

- レコード セットのメンバー関数のオーバーライドをなど`OnSetOptions`アプリケーション固有のオプションを設定する、または既定値を上書きします。

複雑な SQL ステートメントに、レコード セットを基にする場合は、これらのカスタマイズの手法のいくつかの組み合わせを使用する必要があります。 たとえば、SQL 句を使用する場合がありますし、レコード セットまたはおそらくによって直接サポートされているキーワードは複数のテーブルへの参加します。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[ODBC の基礎](../../data/odbc/odbc-basics.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
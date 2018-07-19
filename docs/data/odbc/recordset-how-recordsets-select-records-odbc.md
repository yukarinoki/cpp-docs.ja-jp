---
title: ': レコード選択レコードのしくみ (ODBC) |Microsoft ドキュメント'
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
ms.openlocfilehash: a9ff2f1e9946eb32356eb09fa2ee216aa636a351
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093231"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>レコードセット: レコード選択のしくみ (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [役割とオプションのレコードを選択する](#_core_your_options_in_selecting_records)です。  
  
-   [レコード セットの SQL ステートメントの構築し、レコードの選択](#_core_how_a_recordset_constructs_its_sql_statement)です。  
  
-   [選択範囲のカスタマイズを行うことができます](#_core_customizing_the_selection)です。  
  
 レコード セットは、ドライバーに SQL ステートメントを送信することによって、ODBC ドライバーを通じてデータ ソースからレコードを選択します。 送信された SQL は、設計方法と、レコード セット クラスを開くかによって異なります。  
  
##  <a name="_core_your_options_in_selecting_records"></a> オプションのレコードを選択します。  
 次の表は、レコードを選択するオプションを示します。  
  
### <a name="how-and-when-you-can-affect-a-recordset"></a>方法とタイミング レコード セットに影響することができます。  
  
|ときにします。|できます|  
|--------------|-------------|  
|使用してレコード セット クラスの宣言、**クラスの追加**ウィザード|選択するテーブルを指定します。<br /><br /> 含める列を指定します。<br /><br /> 参照してください[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)です。|  
|レコード セット クラスの実装を完了します。|など、メンバー関数をオーバーライド`OnSetOptions`(高度な) アプリケーション固有のオプションを設定するか、既定値を変更します。 パラメーター化されたレコード セットの場合は、パラメーター データ メンバーを指定します。|  
|レコード セット オブジェクトを作成する (呼び出す前に**開く**)|使用する (単一または複合) 検索条件の指定、**場所**レコードをフィルター処理する句。 参照してください[レコード セット: レコード (ODBC) のフィルター処理](../../data/odbc/recordset-filtering-records-odbc.md)です。<br /><br /> 使用するための並べ替え順序を指定、 **ORDER BY**並べ替え句。 参照してください[レコード セット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)です。<br /><br /> クラスに追加するすべてのパラメーターのパラメーターの値を指定します。 参照してください[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)です。|  

|呼び出すことによって、レコード セットのクエリを実行**開く**|セットアップ ウィザードによって既定の SQL 文字列を置換するカスタム SQL 文字列を指定します。 参照してください[:open](../../mfc/reference/crecordset-class.md#open)で、*クラス ライブラリ リファレンス*と[SQL: レコード セットの SQL ステートメント (ODBC) のカスタマイズ](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)|。  

|呼び出す**Requery**をデータ ソースの最新の値を持つレコード セットを再実行 |新しいパラメーター、フィルター、または並べ替えを指定します。 参照してください[レコード セット: レコード セット (ODBC) のクエリを再実行](../../data/odbc/recordset-requerying-a-recordset-odbc.md)|。  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> レコード セットが、SQL ステートメントを構築する方法  
 レコード セット オブジェクトを呼び出すと[開く](../../mfc/reference/crecordset-class.md#open)メンバー関数は、**開く**以下のデータの一部またはすべてを使用して SQL ステートメントを作成します。  
  
-   **LpszSQL**に渡されたパラメーター**開く**です。 ない場合**NULL**、このパラメーターは、カスタムの SQL 文字列型またはいずれかの一部を指定します。 フレームワークでは、文字列を解析します。 文字列が SQL の場合**選択**ステートメントまたは ODBC**呼び出す**ステートメントでは、フレームワークは、レコード セットの SQL ステートメントとして文字列を使用します。 SQL を構築するために供給されるフレームワークを使用して、文字列が"SELECT"または「{呼び出し」で始まっていない場合**FROM**句。  
  
-   によって返される文字列[GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)です。 既定では、これは、ウィザードで、レコード セットの指定したテーブルの名前が、関数が返すを変更することができます。 フレームワークによって`GetDefaultSQL`: 文字列が"SELECT"または「{呼び出し」で始まっていない場合、SQL 文字列を構築するために使用されるテーブル名であると見なされます。  
  

-   フィールド データ メンバー、レコード セットのテーブルの特定の列にバインドするのには。 フレームワークは、バッファーとしてそれらを使用して、これらのメンバーのアドレスをレコード列をバインドします。 フレームワークからテーブル列にフィールド データ メンバーの相関関係を決定する、 [RFX](../../data/odbc/record-field-exchange-using-rfx.md)かバルク RFX 関数を呼び出して、レコード セットの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)メンバー関数。  
  
-   [フィルター](../../data/odbc/recordset-filtering-records-odbc.md) 、レコード セットに存在する場合に含まれている、[か](../../mfc/reference/crecordset-class.md#m_strfilter)データ メンバーです。 フレームワークでは、この文字列を使用して、SQL を生成**場所**句。  
  
-   [並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)、いずれかに含まれている場合、レコード セットの順序、[レコード](../../mfc/reference/crecordset-class.md#m_strsort)データ メンバーです。 フレームワークでは、この文字列を使用して、SQL を生成**ORDER BY**句。  

  
    > [!TIP]
    >  SQL を使用する**GROUP BY**句 (および場合によって、 **HAVING**句)、フィルター文字列の末尾に句を追加します。  
  
-   いずれかの値[パラメーター データ メンバー](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)クラスを指定します。 だけを呼び出す前に、パラメーター値を設定する**開く**または**Requery**です。 フレームワークをバインドするパラメーターの値"?"SQL 文字列内のプレース ホルダーです。 コンパイル時に、プレース ホルダーで文字列を指定します。 実行時に、フレームワークを渡すパラメーターの値に基づいて詳細で塗りつぶします。  
  
 **開いている**SQL を構築**選択**ステートメントこれらの構成要素から。 参照してください[選択範囲をカスタマイズする](#_core_customizing_the_selection)フレームワークが、構成要素を使用する方法に関する詳細。  
  
 ステートメントを構築した後**開く**SQL を送り、ODBC ドライバー マネージャー (ODBC カーソル ライブラリがメモリにある場合)、特定の DBMS の ODBC ドライバーに送信します。 ドライバーは、データ ソースの選択項目に、実行するために DBMS と通信し、最初のレコードをフェッチします。 フレームワークは、レコード セットのフィールド データ メンバーにレコードを読み込みます。  
  
 開くには、これらの手法の組み合わせを使用することができます[テーブル](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)に基づいてクエリを作成して、[結合](../../data/odbc/recordset-performing-a-join-odbc.md)複数のテーブルです。 その他のカスタマイズを呼び出すことができます[の定義済みクエリ](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)(ストアド プロシージャ) を選択テーブルのデザイン時に認識されない列と[バインド](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)他の大半を実行すると、レコード セット フィールドまたはデータ アクセス タスク。 レコード セットをカスタマイズすることで実現できないタスクを引き続き行うことができます[ODBC API 関数を呼び出して](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)を持つ SQL ステートメントを直接実行または[:executesql](../../mfc/reference/cdatabase-class.md#executesql)です。  
  
##  <a name="_core_customizing_the_selection"></a> 選択範囲をカスタマイズします。  
 以外にも、フィルター、並べ替え順、またはパラメーター、レコード セットの選択をカスタマイズするのには、次の操作を実行できます。  
  
-   カスタム SQL 文字列を渡す**lpszSQL**を呼び出すと[開く](../../mfc/reference/crecordset-class.md#open)レコード セットのです。 渡すもの**lpsqSQL**ものよりも優先、 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)メンバー関数を返します。  
  
     詳細については、次を参照してください[SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)、種類を説明する SQL ステートメント (または部分的なステートメント) に渡すことができます**開く**フレームワークの役割と。  
  
    > [!NOTE]
    >  カスタム指定した文字列が"SELECT"または「{呼び出し」で始まっていない場合、MFC はテーブル名が含まれていると仮定します。 これは、次の項目にも適用されます。  
  
-   レコード セットのウィザードで生成される文字列を alter`GetDefaultSQL`メンバー関数。 返される内容を変更する関数のコードを編集します。 既定では、ウィザードで生成、`GetDefaultSQL`を 1 つのテーブル名を返す関数。  
  
     ことが`GetDefaultSQL`で渡すことのできるアイテムのいずれかを返す、 **lpszSQL**パラメーターを**開く**です。 カスタム SQL 文字列を渡さないかどうか**lpszSQL**、フレームワークは、文字列を使用している`GetDefaultSQL`を返します。 少なくとも`GetDefaultSQL`1 つのテーブル名を返す必要があります。 複数のテーブル名、完全を返すことができますが、**選択**ステートメントでは、ODBC**呼び出す**ステートメントというようにします。 渡すことの一覧については**lpszSQL** — かが`GetDefaultSQL`を返すを参照してください[SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)です。  
  
     2 つ以上のテーブルの結合を実行する場合を書き換える`GetDefaultSQL`SQL で使用されるテーブルの一覧をカスタマイズする**FROM**句。 詳細については、次を参照してください。[レコード セット: 結合 (Odbc)](../../data/odbc/recordset-performing-a-join-odbc.md)です。  
  

-   取得するスキーマについては、データ ソースの実行時に基づくなど、他のフィールド データ メンバーを手動でバインドします。 レコード セット クラスのフィールド データ メンバーを追加する[RFX](../../data/odbc/record-field-exchange-using-rfx.md)バルク RFX 関数にするにまたは、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)メンバー関数とクラスのコンス トラクター内のデータ メンバーの初期化します。 詳細については、次を参照してください。[レコード セット: データ列を動的に結びつける (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)です。  
  
-   などのレコード セットのメンバー関数をオーバーライド`OnSetOptions`アプリケーション固有のオプションを設定する、または既定値をオーバーライドします。  
  
 複雑な SQL ステートメントをレコード セットを基にする場合は、これらのカスタマイズ手法のいくつかの組み合わせを使用する必要があります。 たとえば、SQL 句を使用したい場合と、直接サポートされていないレコード セットしたりキーワードは、複数のテーブルを結合します。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [: レコード更新レコードのしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [ODBC の基礎](../../data/odbc/odbc-basics.md)   
 [SQL](../../data/odbc/sql.md)   
 [レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
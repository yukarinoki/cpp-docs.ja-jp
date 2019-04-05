---
title: レコードセット (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, snapshots
- recordsets, creating
- dynamic recordsets
- forward-only recordsets
- recordsets, dynasets
- ODBC recordsets, CRecordset objects
- ODBC recordsets
- recordsets, about recordsets
- snapshots, ODBC recordsets
- dynasets
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
ms.openlocfilehash: b201e152d83d3812253aa4803eebe715d726219d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034496"
---
# <a name="recordset-odbc"></a>レコードセット (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

A [CRecordset](../../mfc/reference/crecordset-class.md)オブジェクト データ ソースから選択されたレコードのセットを表します。 レコードになります。

- テーブルです。

- クエリ。

- 1 つまたは複数のテーブルにアクセスするストアド プロシージャ。

テーブルに基づくレコード セットの例は、"all customers"、Customer テーブルにアクセスします。 クエリの例は、「すべての請求書 Joe Smith」 ストアド プロシージャ (定義済みのクエリとも呼ばれます) に基づいてレコード セットの例は、「すべての未払い」バック エンド データベースでストアド プロシージャを呼び出します。 レコード セットは、同じデータ ソースからテーブルが異なるデータ ソースからテーブルではなく、2 つ以上参加できます。

> [!NOTE]
>  ウィザードを使用してレコード セット クラスを派生させる方法の詳細については、次を参照してください。 [MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)と[データベースのサポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)します。

> [!NOTE]
>  一部の ODBC ドライバーでは、データベースのビューをサポートします。 この意味でビューとは、SQL で作成されたクエリ`CREATE VIEW`ステートメント。 ウィザードは現在のビューをサポートしてが自分でこのサポートをコーディングすることができます。

##  <a name="_core_recordset_capabilities"></a> レコード セットの機能

すべてのレコード セット オブジェクトでは、次の機能を共有します。

- レコード セットがあることを指定するには、データ ソースは、読み取り専用には場合、[更新可能な](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、[追加可能](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、または読み取り専用です。 ペシミスティックまたはオプティミスティックのいずれかを選択できる、レコード セットが更新可能な場合は、[ロック](../../data/odbc/recordset-locking-records-odbc.md)メソッド、提供、ドライバーは、適切なロック サポートを提供します。 データ ソースが読み取り専用の場合は、レコード セットは読み取り専用になります。

- メンバー関数を呼び出すことができます[スクロール](../../data/odbc/recordset-scrolling-odbc.md)を通じて選択されたレコード。

- できます[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)から利用できるように選択するレコードを制限するレコード。

- できます[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)を昇順または降順に並べ替え、レコードは 1 つまたは複数の列に基づきます。

- できます[をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)実行時にレコード セットの選択を修飾するために、レコード セット。

##  <a name="_core_snapshots_and_dynasets"></a> スナップショットとダイナセット

2 つのプリンシパルの種類のレコード セットがある:[スナップショット](../../data/odbc/snapshot.md)と[ダイナセット](../../data/odbc/dynaset.md)します。 クラスでサポートされる両方`CRecordset`します。 すべてのレコード セットの共通の特性を共有それぞれが、それぞれが独自の特殊な方法でも共通の機能を拡張します。 スナップショットは、データの静的なビューを提供しはレポートと特定の時点に存在していたデータのビューが必要なその他の状況に適しています。 ダイナセットを使う場合は、クエリを再実行またはレコード セットを更新することがなく、レコード セットで表示される他のユーザーによって行われた更新する場合に役立ちます。 スナップショットとダイナセットを使う場合は、更新可能または読み取り専用を指定できます。 追加されたレコードが反映または呼び出し、その他のユーザーによって削除された[:requery](../../mfc/reference/crecordset-class.md#requery)します。

`CRecordset` 他の 2 つの種類のレコード セットのことができます。 動的レコード セットと順方向専用のレコード。 動的レコード セットがダイナセット; に似ています。ただし、動的レコード セットが追加または削除を呼び出さずに、すべてのレコードを反映`CRecordset::Requery`します。 このため、動的レコード セットは、一般に、DBMS での処理時間に関してコストが、多くの ODBC ドライバーはサポートされません。 これに対し、順方向専用レコード セットは、レコード セットの更新プログラムまたは旧バージョンとスクロールを必要としないデータ アクセスの最も効率的な方法を提供します。 たとえば、順方向専用レコード セットを使用して、データを移行する 1 つのデータ ソースから、場所だけで済みます順方向にデータを移動する可能性があります。 順方向専用レコード セットを使用するには、次の両方を行う必要があります。

- オプションを渡す`CRecordset::forwardOnly`として、*できるかどうか*のパラメーター、[オープン](../../mfc/reference/crecordset-class.md#open)メンバー関数。

- 指定`CRecordset::readOnly`で、 *dwOptions*パラメーターの`Open`します。

    > [!NOTE]
    >  ダイナセットの ODBC ドライバーの要件については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)します。 このバージョンの Visual C に含まれる ODBC ドライバーの一覧については、および追加のドライバーの入手方法については、「 [ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)します。

##  <a name="_core_your_recordsets"></a> レコード セット

派生したクラスの定義通常すべての個別のテーブル、ビュー、またはアクセスするストアド プロシージャの`CRecordset`します。 (例外は、1 つのレコード セットが 2 つ以上のテーブルから列を表しますデータベースが結合です)。レコード セット クラスを派生するときまたは有効にしたレコード フィールド エクス (チェンジ RFX) メカニズム、バルク レコード フィールド エクス チェンジ (Bulk RFX) メカニズムはダイアログ データ エクス (チェンジ DDX) メカニズムに似ています。 バルク RFX データ ソースからのデータは、レコード セットへの転送を簡略化します。RFX はさらに、データ ソースに、レコード セットからデータを転送します。 詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)と[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

レコード セット オブジェクトでは、選択したすべてのレコードにアクセスできます。 使用して複数の選択したレコードをスクロールする`CRecordset`などのメンバー関数`MoveNext`と`MovePrev`します。 レコード セット オブジェクトには、同時に、選択のレコードでは、現在のレコードの 1 つだけを表します。 現在のレコードのフィールドは、レコード セットの列、またはデータベース クエリから作成されるレコードのテーブルの列に対応するクラスのメンバー変数を宣言することを確認できます。 レコード セットのデータ メンバーについては、次を参照してください。[レコード セット。構造 (ODBC)](../../data/odbc/recordset-architecture-odbc.md)します。

次のトピックでは、レコード セット オブジェクトの使用の詳細について説明します。 トピックは、機能のカテゴリとシーケンシャルな読み取りを許可するように参照を自然な順序で表示されます。

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>開く、読み取り、およびレコード セットの終了のしくみに関するトピック

- [レコード セット:構造 (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [レコード セット:テーブル (ODBC) クラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [レコード セット:作成するレコード セットと破棄 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [レコード セット:スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

- [レコード セット:ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [レコード セット:レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [レコード セット:レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [レコード セット:レコード セット (ODBC) をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>レコード セットの変更のしくみに関するトピック

- [レコード セット:追加、更新、および削除 (Odbc)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [レコード セット:レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [レコード セット:クエリの再実行 (Odbc)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>高度な手法をいくらかに関するトピック

- [レコード セット:結合 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [レコード セット:クラスの宣言、定義済みクエリ (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [レコード セット:動的に結びつける方法 (ODBC) のデータ列](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [レコード セット:方法 (ODBC) 内のレコードをフェッチしています](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [レコード セット:大規模なデータ アイテム (ODBC) の操作](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [レコード セット:合計およびその他の集計の計算 (ODBC) を取得します。](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>レコード セットのしくみに関するトピック

- [レコード セット:レコード セットの選択が (ODBC) を記録する方法](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [レコード セット:レコード セットの更新が (ODBC) を記録する方法](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>関連項目

[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)
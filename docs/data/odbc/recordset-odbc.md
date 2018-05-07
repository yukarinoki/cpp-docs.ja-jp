---
title: レコード セット (ODBC) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0c59de3c5db2e1ec658a09279cb42e2833a4109e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-odbc"></a>レコードセット (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 A [CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトは、データ ソースから選択されたレコードのセットを表します。 レコードになります。  
  
-   テーブルです。  
  
-   クエリ。  
  
-   1 つまたは複数のテーブルにアクセスするストアド プロシージャ。  
  
 テーブルに基づくレコード セットの例は、Customer テーブルにアクセスする"all customers、"です。 クエリの例は、「すべての請求書山田太郎」 ストアド プロシージャ (定義済みのクエリとも呼ばれます) に基づいてレコード セットの例は、「すべての不履行のアカウントでは、」バックエンド データベースでストアド プロシージャを呼び出します。 レコード セットは、同じデータ ソースからテーブルが異なるデータ ソースのテーブルではなく、2 つ以上参加できます。  
  
> [!NOTE]
>  ウィザードを使用してレコード セット クラスを派生させる方法については、次を参照してください。 [MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)と[データベースのサポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)です。  
  
> [!NOTE]
>  一部の ODBC ドライバーでは、データベースのビューをサポートします。 この意味でビューとは、SQL を使用して作成したクエリ`CREATE VIEW`ステートメントです。 ウィザードはサポートされていません、ビューが、このサポートをコーディングすること。  
  
##  <a name="_core_recordset_capabilities"></a> レコード セットの機能  
 すべてのレコード セット オブジェクトでは、次の機能を共有します。  
  
-   レコード セットがあることを指定するには、データ ソースは、読み取り専用には場合、[更新可能な](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、[追加可能](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、または読み取り専用です。 レコード セットが更新可能な場合は、ことができますオプティミスティックかペシミスティック[ロック](../../data/odbc/recordset-locking-records-odbc.md)ドライバーが適切なロックのサポートを提供するメソッド、用意されています。 データ ソースが読み取り専用の場合は、レコード セットは読み取り専用にされます。  
  
-   メンバー関数を呼び出すことができます[スクロール](../../data/odbc/recordset-scrolling-odbc.md)選択したレコードをします。  
  
-   実行できます[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)から利用できるように選択するレコードを制限するレコード。  
  
-   実行できます[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)を昇順または降順に並べ替え、レコードは 1 つまたは複数の列に基づきます。  
  
-   実行できます[パラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)実行時にレコード セットの選択を修飾するために、レコード セット。  
  
##  <a name="_core_snapshots_and_dynasets"></a> スナップショットとダイナセットを使う場合  
 レコード セットの 2 種類がある:[スナップショット](../../data/odbc/snapshot.md)と[ダイナセット](../../data/odbc/dynaset.md)です。 クラスでサポートされて両方`CRecordset`です。 すべてのレコード セットの共通の特性を共有それぞれは、それぞれが独自の特殊な方法でも共通の機能が拡張です。 スナップショットは、データの静的なビューを提供し、レポートと特定の時点で存在していたデータのビューが必要なその他の状況に便利です。 ダイナセットを使う場合は、更新プログラムを再クエリまたはレコード セットを更新することがなく、レコード セットで表示するその他のユーザーによって行われた場合に役立ちます。 スナップショットとダイナセットを使う場合は、更新可能または読み取り専用に指定できます。 追加されたレコードの反映を呼び出す他のユーザーによって削除された[:requery](../../mfc/reference/crecordset-class.md#requery)です。  
  
 `CRecordset` 他の 2 つの種類のレコード セットのこともできます。 動的レコード セットと順方向専用レコード セット。 動的レコード セットが; ダイナセットを使う場合と似ています。ただし、動的レコード セットがすべてのレコードを追加または削除を呼び出さずを反映`CRecordset::Requery`です。 このため、動的レコード セットは一般に、DBMS での処理時間に関してコストがかかります、多くの ODBC ドライバーはサポートされません。 これに対し、前方スクロール専用レコードは、更新および後方スクロールを必要としないレコード セットのデータ アクセスの最も効率的な方法を提供します。 たとえば、順方向専用レコード セットを使用してデータを移行する 1 つのデータ ソース間だけで十分で前方にデータを移動する可能性があります。 順方向専用レコード セットを使用するのには、次の両方を行う必要があります。  
  
-   オプションを渡す**crecordset::forwardonly**として、`nOpenType`のパラメーター、[開く](../../mfc/reference/crecordset-class.md#open)メンバー関数。  
  
-   指定**crecordset::readonly**で、`dwOptions`のパラメーター**開く**です。  
  
    > [!NOTE]
    >  ダイナセット用 ODBC ドライバーの要件については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)です。 このバージョンの Visual C に含まれている ODBC ドライバーの一覧、および追加のドライバーを取得する方法についてを参照してください。 [ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)です。  
  
##  <a name="_core_your_recordsets"></a> レコード セット  
 派生したクラスの定義通常すべての個別のテーブル、ビュー、またはアクセスするストアド プロシージャの`CRecordset`します。 (例外は、1 つのレコード セットが 2 つ以上のテーブルから列を表すをデータベースが結合です)。レコード セット クラスを派生させる場合、または有効にレコード フィールド エクス (チェンジ RFX) メカニズム バルク レコード フィールド エクス チェンジ (Bulk RFX) 機構をダイアログ データ エクス (チェンジ DDX) メカニズムに似ています。 バルク RFX、レコード セットへのデータ ソースからデータの転送を簡略化します。RFX はさらに、データ ソースに、レコード セットからデータを転送します。 詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)と[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 レコード セット オブジェクトでは、選択したすべてのレコードにアクセスできます。 使用して複数の選択したレコードをスクロールする`CRecordset`などのメンバー関数`MoveNext`と`MovePrev`です。 レコード セット オブジェクトには、同時に、選択したレコードを現在のレコードの 1 つだけを表します。 レコード セットの列、またはデータベース クエリから返されたレコードのテーブルの列に対応するクラスのメンバー変数を宣言することによって、現在のレコードのフィールドを確認できます。 レコード セットのデータ メンバーについては、次を参照してください。[レコード セット: 構造 (ODBC)](../../data/odbc/recordset-architecture-odbc.md)です。  
  
 次のトピックでは、レコード セット オブジェクトの使い方の詳細について説明します。 トピックは、機能カテゴリとシーケンシャルな読み取りを許可するように参照の自然な順序で一覧表示されます。  
  
### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>開く、読み取り、およびレコード セットを閉じるのしくみに関するトピック  
  
-   [レコードセット: レコードセットの構造 (ODBC)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [レコードセット: テーブルにアクセスするレコードセット クラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [レコードセット: レコードセットの生成と破棄 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [レコードセット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)  
  
-   [レコードセット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [レコードセット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [レコードセット: パラメーターを利用したレコードセット (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>レコード セットを変更した場合のしくみに関するトピック  
  
-   [レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [レコードセット: クエリの再実行 (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### <a name="topics-about-somewhat-more-advanced-techniques"></a>高度な手法をいくらかに関するトピック  
  
-   [レコードセット: 結合 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)  
  
-   [レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)  
  
-   [レコードセット: 大量のデータの処理 (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [レコードセット: 集計値の計算 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### <a name="topics-about-how-recordsets-work"></a>レコード セットのしくみに関するトピック  
  
-   [レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)  
  
-   [レコードセット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## <a name="see-also"></a>関連項目  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [MFC ODBC コンシューマーします。](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)
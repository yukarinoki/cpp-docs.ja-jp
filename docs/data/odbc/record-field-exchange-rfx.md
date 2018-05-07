---
title: レコード フィールド エクス (チェンジ RFX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b214cf05115056efc96c4a078dedd4b7f9a3a1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-rfx"></a>レコード フィールド エクスチェンジ (RFX)
MFC ODBC データベース クラスが、データ ソースの間でデータの移動を自動化し、[レコード セット](../../data/odbc/recordset-odbc.md)オブジェクト。 クラスを派生する[CRecordset](../../mfc/reference/crecordset-class.md)バルク行フェッチを使用しないと、レコード フィールド エクス (チェンジ RFX) メカニズムによってデータを転送します。  
  
> [!NOTE]
>  派生にバルク行フェッチを実装している場合`CRecordset`クラス、フレームワーク バルク レコード フィールド エクス チェンジ (Bulk RFX) 機構を使ってデータを転送します。 詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 Rfx 関数は、ダイアログ データ エクス (チェンジ DDX) に似ています。 レコード セットの複数の呼び出しデータ ソースとレコード セットのフィールド データ メンバーの間でデータ移動が必要です[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)関数かなりの相互作用、framework 間および[ODBC](../../data/odbc/odbc-basics.md). RFX メカニズムがタイプ セーフし、などの ODBC 関数を呼び出すことの作業を保存する **:: SQLBindCol**です。 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
 RFX は意識する必要はほとんどの場合です。 MFC アプリケーション ウィザードを使用して、レコード セット クラスを宣言するかどうかまたは**クラスの追加**(」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md))、RFX がそれらに自動的に組み込まれています。 レコード セット クラスは基底クラスから派生する必要があります`CRecordset`フレームワークによって提供されます。 MFC アプリケーション ウィザードでは、最初のレコード セット クラスを作成できます。 **クラスの追加**したり、必要に応じて、他のレコード セット クラスを追加することができます。 詳細と例については、次を参照してください。 [MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)です。  
  
 場合に 3 つのケースでは、少量の RFX コードを追加する必要があります手動で。  
  
-   パラメーター化クエリを使用します。 詳細については、次を参照してください。[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)です。  
  
-   結合 (2 つ以上のテーブルの列の 1 つのレコード セットの使用) を実行します。 詳細については、次を参照してください。[レコード セット: 結合 (Odbc)](../../data/odbc/recordset-performing-a-join-odbc.md)です。  
  
-   データ列を動的にバインドします。 これは、パラメーター化ほど一般的です。 詳細については、次を参照してください。[レコード セット: データ列を動的に結びつける (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)です。  
  
 RFX の高度な知識を必要がある場合は、次を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 次のトピックでは、レコード セット オブジェクトの使い方の詳細について説明します。  
  
-   [レコード フィールド エクスチェンジ: RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [レコード フィールド エクスチェンジ: RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## <a name="see-also"></a>関連項目  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [MFC ODBC コンシューマーします。](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [データベースのサポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)
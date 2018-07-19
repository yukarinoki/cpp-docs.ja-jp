---
title: 'レコード セット: を作成するレコード セットと破棄 (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbf020e12151e666aa8f88098865b1624403b828
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092103"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>レコードセット: レコードセットの生成と破棄 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 レコード セットを使用するのには、レコード セット オブジェクトを構築およびを呼び出す、**開く**メンバー関数をレコード セットのクエリを実行し、レコードを選択します。 レコード セットが完了したらと閉じるオブジェクトを破棄します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [レコード セット オブジェクトを作成するタイミングと方法](#_core_creating_recordsets_at_run_time)です。  
  
-   [パラメーター化、フィルター、並べ替え、またはコンピューターをロックし、レコード セットの動作の条件を指定できますタイミングと方法](#_core_setting_recordset_options)です。  
  
-   [レコード セット オブジェクトをクローズする方法とタイミング](#_core_closing_a_recordset)です。  
  
##  <a name="_core_creating_recordsets_at_run_time"></a> 実行時にレコード セットの作成  
 レコード セット オブジェクトを作成するには、プログラムで、前に通常アプリケーション固有のレコード セット クラスを作成します。 この手順の詳細については、次を参照してください。 [MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)です。  
  
 データ ソースからレコードを選択する必要がある場合は、ダイナセットまたはスナップショットのオブジェクトを開きます。 作成するオブジェクトの種類を行う必要がありますに依存アプリケーションではどのような ODBC ドライバーをサポートしているデータを使用します。 詳細については、次を参照してください。[ダイナセット](../../data/odbc/dynaset.md)と[スナップショット](../../data/odbc/snapshot.md)です。  
  
#### <a name="to-open-a-recordset"></a>レコード セットを開く  
  
1.  オブジェクトの構築、 `CRecordset`-クラスを派生します。  
  
     ヒープ上または関数のスタック フレーム上のオブジェクトを構築することができます。  
  
2.  必要に応じて既定のレコード セットの動作を変更します。 詳細については、次を参照してください。[レコード セットのオプションを設定](#_core_setting_recordset_options)です。  
  
3.  オブジェクトの[開く](../../mfc/reference/crecordset-class.md#open)メンバー関数。  
  
 、そのコンス トラクターへのポインターを渡す、`CDatabase`オブジェクト、または渡す**NULL**一時的なを使用するフレームワークが構築して表示するデータベース オブジェクトがによって返される接続文字列に基づく、 [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect)メンバー関数。 `CDatabase`オブジェクトは、データ ソースに既に接続可能性があります。  
  
 呼び出し**開く**SQL を使用して、データ ソースからレコードを選択します。 (存在する場合) を選択した最初のレコードは、現在のレコードです。 このレコードのフィールドの値は、レコード セット オブジェクトのフィールド データ メンバーに格納されます。 すべてのレコードが選択されている場合両方、`IsBOF`と`IsEOF`メンバー関数は 0 を返します。  
  
 [開く](../../mfc/reference/crecordset-class.md#open)呼び出しすることができます。  
  
-   レコード セットは、ダイナセットまたはスナップショットかどうかを指定します。 レコード セットは、既定では、スナップショットとして開きます。 または、前方スクロール、順方向専用のレコードを指定することができます。  
  
     既定では、レコード セットに格納されている既定の型を使用して、`CRecordset`データ メンバー**によって**です。 ウィザードを初期化するコードを記述する**によって**ウィザードで選択したレコード セットの種類にします。 この既定値を受け入れではなく、別のレコード セットの種類を置き換えることができます。  
  
-   既定の SQL を置換する文字列を指定**選択**レコード セットを作成するステートメント。  
  
-   レコード セットが読み取り専用、または追加専用かどうかを指定します。 レコード セットを許可するフル既定では、更新またはされるを制限するには新しいレコードのみを追加することもすべての更新を禁止することができます。  
  
 次の例は、クラスの読み取り専用スナップショット オブジェクトを開く方法を示しています。 `CStudentSet`、アプリケーション固有のクラス。  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 呼び出した後**開く**レコードを使用するオブジェクトのメンバー関数とデータ メンバーを使用します。 場合によっては、クエリを再実行またはデータ ソースで発生した変更を含めるレコード セットを更新することができます。 詳細については、次を参照してください。[レコード セット: レコード セット (ODBC) のクエリを再実行](../../data/odbc/recordset-requerying-a-recordset-odbc.md)です。  
  
> [!TIP]
>  開発時に使用する接続文字列は、ユーザーが実際に必要な接続文字列をできない可能性があります。 この点で、アプリケーションを汎用化する方法については、次を参照してください。[データ ソース: 接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)です。  
  
##  <a name="_core_setting_recordset_options"></a> レコード セットのオプションの設定  
 呼び出す前に、レコード セット オブジェクトを構築した後、**開く**レコードを選択するには、レコード セットの動作を制御するいくつかのオプションを設定する可能性があります。 すべてのレコード セットの次の操作を実行できます。  
  
-   指定して、[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)レコードの選択を制限します。  
  
-   指定して、[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)レコードの順序。  
  
-   指定[パラメーター](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)情報を取得または実行時に計算を使用してレコードを選択できるようにします。  
  
 条件を満たす場合、次のオプションを設定することもできます。  
  
-   レコード セットが更新可能であるあり、ロック オプションをサポートする場合は、指定、[ロック](../../data/odbc/recordset-locking-records-odbc.md)メソッドの更新に使用します。  
  
> [!NOTE]
>  レコードの選択に影響する可能性を呼び出す前に、これらのオプションを設定する必要があります、**開く**メンバー関数。  
  
##  <a name="_core_closing_a_recordset"></a> レコード セットを閉じる  
 Recordset を完了したら、破棄してから、メモリを解放します。  
  
#### <a name="to-close-a-recordset"></a>レコード セットを閉じる  
  
1.  呼び出す、[閉じる](../../mfc/reference/crecordset-class.md#close)メンバー関数。  
  
2.  レコード セット オブジェクトを破棄します。  
  
     関数のスタック フレームに宣言したオブジェクトがスコープ外に出るときに、オブジェクトに自動的に破棄されます。 それ以外の場合を使用して、**削除**演算子。  
  
 **閉じる**レコード セットの解放**HSTMT**を処理します。 C++ オブジェクトは破棄しません。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)   
 [レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
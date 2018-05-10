---
title: 'レコード セット: レコード セット (ODBC) のパラメーター化 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 275cd9d2ee7ccbd4c9972c00ae6fbb8f33166a0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>レコードセット: パラメーターを利用したレコードセット (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 場合もあります計算またはエンドユーザーから取得した情報を使用して、実行時にレコードを選択することにする可能性があります。 レコード セットのパラメーターを使用して、その目的を達成できます。  
  
 このトピックでは、次の内容について説明します。  
  
-   [パラメーター化されたレコード セットの目的は、](#_core_parameterized_recordsets)です。  
  
-   [タイミングと理由は、レコード セットをパラメーター化することができます](#_core_when_to_use_parameters)です。  
  
-   [レコード セット クラスのデータ メンバーのパラメーターを宣言する方法](#_core_parameterizing_your_recordset_class)です。  
  
-   [実行時に、レコード セット オブジェクトにパラメーター情報を渡す方法](#_core_passing_parameter_values_at_run_time)です。  
  
##  <a name="_core_parameterized_recordsets"></a> パラメーター化されたレコード セット  
 パラメーター化されたレコード セットを使用して、実行時にパラメーター情報を渡すことができます。 これにより、2 つの重要な影響があります。  
  
-   実行速度を向上させることがあります。  
  
-   これにより、情報が、ユーザーから取得した、または実行時に計算など、デザイン時に使用できない情報に基づいて、実行時にクエリを作成できます。  
  
 呼び出すと**開く**クエリを実行するには、レコード セット情報を使用してパラメーター完了その**SQL SELECT**ステートメントです。 すべてのレコード セットをパラメーター化できます。  
  
##  <a name="_core_when_to_use_parameters"></a> パラメーターを使用する場合  
 パラメーターの一般的な用途は次のとおりです。  
  
-   定義済みクエリを実行時引数を渡します。  
  
     ストアド プロシージャにパラメーターを渡す、完全なカスタム ODBC を指定する必要があります**呼び出す**ステートメント — パラメーター プレース ホルダーで — を呼び出すと**開く**、レコード セットの既定の SQL ステートメントをオーバーライドします。 詳細については、次を参照してください[:open](../../mfc/reference/crecordset-class.md#open)で、*クラス ライブラリ リファレンス*と[SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)と[。レコード セット: 定義済みクエリ (ODBC) クラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)です。  

  
-   異なるパラメーター情報をそのつどを効率的に実行しています。  
  
     たとえば、エンドユーザーは学生登録データベースの特定の受講者に関する情報を検索するたびに指定できます受講者の名前または ID ユーザーから取得した、パラメーターとして。 次に、レコード セットを呼び出すと**Requery**メンバー関数の場合、クエリがそのスチューデントのレコードのみを選択します。  
  
     格納されたレコード セットのフィルター文字列**か**、次のようになります。  
  
    ```  
    "StudentID = ?"  
    ```  
  
     変数の学生 ID を取得すると仮定`strInputID`です。 パラメーターを設定すると`strInputID`によって表されるパラメーターのプレース ホルダーに (たとえば、学生 ID 100)、変数の値がバインドされている、"?"フィルター文字列にします。  
  
     パラメーターの値に割り当てます。  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     このように、フィルター文字列を設定しません。  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     フィルター文字列の引用符を正しく使用する方法の詳細については、次を参照してください。[レコード セット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)です。  
  
     パラメーター値が異なる新しい学生 ID のレコード セットを再実行するたびにです。  
  
    > [!TIP]
    >  パラメーターを使用することは、単にフィルターより効率的です。 データベースは、パラメーター化されたレコード セットの SQL を処理する必要があります**選択**ステートメントを 1 回のみです。 パラメーターを指定しないフィルター選択されたレコード セットの**選択**ステートメントを処理する必要があるたびに**Requery**新しいフィルター値を持つ。  
  
 フィルターの詳細については、次を参照してください。[レコード セット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)です。  
  
##  <a name="_core_parameterizing_your_recordset_class"></a> レコード セット クラスのパラメーター化  
  
> [!NOTE]
>  このセクションから派生したオブジェクトに適用されます`CRecordset`バルク行フェッチは実装されていません。 バルク行フェッチ、パラメーターを実装を使用している場合は、同様のプロセスです。 詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 レコード セット クラスを作成する前に、どのようなパラメーターする必要があります、そのデータ型とは何かと、レコード セットでの使用方法を決定します。  
  
#### <a name="to-parameterize-a-recordset-class"></a>レコード セット クラスをパラメーター化するには  
  
1.  実行、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)から**クラスの追加**クラスを作成します。  
  
2.  レコード セットの列のフィールド データ メンバーを指定します。  
  
3.  ウィザードでは、プロジェクト内のファイルにクラスを書き込み後、は、.h ファイルに移動し、手動で 1 つまたは複数のパラメーター データ メンバーをクラス宣言に追加します。 なります次の例のように、スナップショット クラスの一部のため、クエリの回答"受講者に含まれているスキルの限られたクラス?"  
  
    ```  
    class CStudentSet : public CRecordset  
    {  
    // Field/Param Data  
        CString m_strFirstName;  
        CString m_strLastName;  
        CString m_strStudentID;  
        CString m_strGradYear;  
  
        CString m_strGradYrParam;  
    };  
    ```  
  
     ウィザードで生成されたフィールド データ メンバーの後に、パラメーター データ メンバーを追加します。 規則では、各ユーザー定義のパラメーター名に"Param"という単語を追加します。  
  
4.  変更、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) .cpp ファイルでメンバー関数の定義。 クラスに追加する各パラメーター データ メンバーに対して RFX 関数呼び出しを追加します。 RFX 関数の記述方法については、次を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。 1 回の呼び出しでパラメーターの rfx 関数を呼び出す前に。  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  レコード セット クラスのコンス トラクターで、パラメーターのカウントをインクリメント`m_nParams`です。  
  
     詳細については、次を参照してください。[レコード フィールド エクス チェンジ: ウィザード コードの使用](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)です。  
  
6.  このクラスのレコード セット オブジェクトを作成するコードを記述する場合は、配置、"?"各内の場所に、SQL ステートメントの文字列パラメーターが置き換えられます (疑問符 (?))。  
  
     実行時に、"?"プレース ホルダーは、順序で、パラメーター値を渡します。 最初のパラメーター データ メンバーを設定した後、 [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)呼び出すには、最初が置き換えられます"しますか?「SQL 文字列に 2 番目のパラメーター データ メンバーが置き換えられます、2 つ目」しますか?"などです。  
  
> [!NOTE]
>  パラメーターの順序は重要な: RFX の順序の呼び出しのパラメーターに対して、`DoFieldExchange`関数は、SQL 文字列内のパラメーター プレース ホルダーの順序と一致する必要があります。  
  
> [!TIP]

>  使用する最も可能性の高い文字列は、指定した文字列 (存在する場合) のクラスの[か](../../mfc/reference/crecordset-class.md#m_strfilter)データ メンバーが、一部の ODBC ドライバーは、他の SQL 句内のパラメーターをすることができます。  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a> 実行時にパラメーター値の受け渡し  
 呼び出す前に、パラメーター値を指定する必要があります**開く**(新しいレコード セット オブジェクト) のまたは**Requery** (の既存のもの)。  
  
#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>実行時に、レコード セット オブジェクトにパラメーター値を渡す  
  
1.  レコード セット オブジェクトを構築します。  
  
2.  文字列または文字列を準備するなど、**か**SQL ステートメント、またはその一部を含む文字列。 Put"?"パラメーター情報が移動、プレース ホルダーです。  
  
3.  オブジェクトの各パラメーターのデータ メンバーに、実行時のパラメーター値を割り当てます。  
  
4.  呼び出す、**開く**メンバー関数 (または**Requery**、既存のレコード セットの)。  
  
 たとえば、実行時に取得した情報を使用して、レコード セットのフィルター文字列を指定するとします。 クラスのレコード セットを作成したと仮定`CStudentSet`前: と呼ばれる`rsStudents`— 受講者情報の特定の種類のクエリを再実行したいとします。  
  
```  
// Set up a filter string with   
// parameter placeholders  
rsStudents.m_strFilter = "GradYear <= ?";  
  
// Obtain or calculate parameter values   
// to pass--simply assigned here   
CString strGradYear = GetCurrentAcademicYear( );  
  
// Assign the values to parameter data members  
rsStudents.m_strGradYrParam = strGradYear;  
  
// Run the query  
if( !rsStudents.Requery( ) )  
    return FALSE;  
```  
  
 レコード セットには、そのレコードが、フィルターは、実行時パラメーターから構築されたで指定された条件を満たしている受講者にレコードが含まれています。 ここでは、レコード セットには、すべてのスキルの限られた生徒のレコードが含まれています。  
  
> [!NOTE]
>  Null の場合にパラメーター データ メンバーの値を設定するには、必要な場合を使用して[SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull)です。 パラメーター データ メンバーが Null の場合であるかどうかをチェックすることが同様を使用して[調べる](../../mfc/reference/crecordset-class.md#isfieldnull)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: 追加、更新、および削除 (Odbc)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
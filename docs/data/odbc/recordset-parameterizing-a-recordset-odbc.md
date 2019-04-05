---
title: レコード セット:レコード セット (ODBC) をパラメーター化
ms.date: 11/04/2016
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
ms.openlocfilehash: df67256c54cae3e2adb054d653d3e58bb91dd631
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026163"
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>レコード セット:レコード セット (ODBC) をパラメーター化

このトピックの内容は、MFC ODBC クラスに該当します。

場合によって計算またはエンドユーザーから取得した情報を使用して、実行時にレコードを選択することにする可能性があります。 レコード セットのパラメーターを使用して、その目的を達成できます。

このトピックでは、次の内容について説明します。

- [パラメーター化されたレコード セットの目的は、](#_core_parameterized_recordsets)します。

- [タイミングと理由は、レコード セットをパラメーター化する可能性がある](#_core_when_to_use_parameters)します。

- [レコード セット クラスのデータ メンバーのパラメーターを宣言する方法](#_core_parameterizing_your_recordset_class)します。

- [実行時に、レコード セット オブジェクトにパラメーター情報を渡す方法](#_core_passing_parameter_values_at_run_time)します。

##  <a name="_core_parameterized_recordsets"></a> パラメーター化されたレコード セット

パラメーター化されたレコード セットを使用して、実行時にパラメーター情報を渡すことができます。 これにより、2 つの重要な影響があります。

- 実行速度を向上可能性があります。

- 情報が、ユーザーから取得した、または実行時に計算など、デザイン時に使用できない情報に基づいて、実行時にクエリを作成できます。

呼び出すと`Open`、レコード セットのクエリを実行するを完了するパラメーター情報を使用してその**SQL SELECT**ステートメント。 すべてのレコード セットをパラメーター化することができます。

##  <a name="_core_when_to_use_parameters"></a> パラメーターを使用する場合

パラメーターの一般的な用途は次のとおりです。

- 定義済みのクエリを実行時引数を渡します。

   ストアド プロシージャにパラメーターを渡すには、完全なカスタム ODBC を指定する必要があります**呼び出す**ステートメント-パラメーター プレース ホルダーで-を呼び出すと`Open`、レコード セットの既定の SQL ステートメントをオーバーライドします。 詳細については、次を参照してください[:open](../../mfc/reference/crecordset-class.md#open)で、*クラス ライブラリ リファレンス*と[SQL:。レコード セットの SQL ステートメント (ODBC) のカスタマイズ](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)と[レコード セット。クラスの定義済みクエリ (ODBC) 宣言](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)します。

- 別のパラメーター情報をそのつどを効率的に実行します。

   たとえば、たびに、エンド ユーザー、学生登録情報データベースで特定の学生の情報を検索する生徒の名前または ID パラメーターとして指定できます、ユーザーから取得しました。 次に、レコード セットを呼び出すと`Requery`メンバー関数は、クエリがその学生のレコードのみを選択します。

   格納されたレコード セットのフィルター文字列`m_strFilter`、ようになります。

    ```cpp
    "StudentID = ?"
    ```

   変数に学生 ID を取得するとします`strInputID`します。 パラメーターを設定すると`strInputID`によって表されるパラメーターのプレース ホルダーを変数の値をバインド (たとえば、学生 ID が 100)、"?"フィルター文字列。

   パラメーターの値を次のように割り当てます。

    ```cpp
    strInputID = "100";
    ...
    m_strParam = strInputID;
    ```

   このように、フィルター文字列を設定しません。

    ```cpp
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted
                                       // for some drivers
    ```

   フィルター文字列の引用符を正しく使用する方法の詳細については、次を参照してください。[レコード セット。レコード (ODBC) のフィルター処理](../../data/odbc/recordset-filtering-records-odbc.md)します。

   パラメーター値が異なる新しい学生 id、レコード セットを再実行するたびにです。

   > [!TIP]
   > パラメーターを使用することは、単にフィルターよりも効率的です。 データベースのパラメーター化されたレコード セットでは、SQL を処理する必要があります**選択**ステートメントを 1 回のみです。 パラメーターを指定せず、フィルター選択されたレコード セットの**選択**ステートメントを処理する必要があるたび`Requery`フィルター値を新しい値。

フィルターの詳細については、次を参照してください。[レコード セット。レコード (ODBC) のフィルター処理](../../data/odbc/recordset-filtering-records-odbc.md)します。

##  <a name="_core_parameterizing_your_recordset_class"></a> レコード セット クラスをパラメーター化

> [!NOTE]
> このセクションから派生したオブジェクトに適用されます`CRecordset`バルク行フェッチは実装されていません。 バルク行フェッチ、パラメーターの実装を使用している場合は、同様のプロセスです。 詳細については、次を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

レコード セット クラスを作成する前に、必要なパラメーターは、データ型は、レコード セットでの使用方法を決定します。

#### <a name="to-parameterize-a-recordset-class"></a>レコード セット クラスをパラメーター化するには

1. 実行、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)から**クラスの追加**クラスを作成します。

1. レコード セットの列のフィールド データ メンバーを指定します。

1. ウィザードでは、プロジェクト内のファイルにクラスを書き込みます後、は、.h ファイルに移動し、クラス宣言に 1 つまたは複数のパラメーターのデータ メンバーを手動で追加します。 追加は、次の例のようなものになります、スナップショット クラスの一部のため、クエリの回答"受講者に含まれている、シニア クラスか"。

    ```cpp
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

   ウィザードで生成されたフィールドのデータ メンバーの後に、パラメーターのデータ メンバーを追加します。 形式では、各ユーザー定義のパラメーター名に"Param"という単語を追加します。

1. 変更、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) .cpp ファイル内のメンバー関数の定義。 クラスに追加する各パラメーターのデータ メンバーに対して RFX 関数の呼び出しを追加します。 RFX 関数の記述方法の詳細については、次を参照してください。[レコード フィールド エクス チェンジ。RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。 1 回の呼び出しでパラメーターの rfx 関数の呼び出しの前に。

    ```cpp
    pFX->SetFieldType( CFieldExchange::param );
    // RFX calls for parameter data members
    ```

1. レコード セット クラスのコンス トラクターで、パラメーターのカウントをインクリメント`m_nParams`します。

   詳しくは、次を参照してください。[レコード フィールド エクス チェンジ。ウィザード コードの使用](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)します。

1. このクラスのレコード セット オブジェクトを作成するコードを記述する場合、配置、"?"適切な各場所で、SQL ステートメントの文字列パラメーターが置き換えられます (疑問符) 記号です。

   実行時に、"でしょうか。"プレース ホルダーは、順序で、パラメーターの値によって渡します。 最初のパラメーターのデータ メンバーを設定した後、 [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)呼び出すには、最初が置き換えられます"でしょうか。"で SQL 文字列、2 番目のパラメーターのデータ メンバーは置き換えます 2 番目の"でしょうか。"など。

> [!NOTE]
> パラメーターの順序が重要です: RFX の順序の呼び出しのパラメーターに対して、`DoFieldExchange`関数は、SQL 文字列内のパラメーター プレース ホルダーの順序と一致する必要があります。

> [!TIP]
> 使用する可能性が最も高い文字列が指定した文字列が (あれば) のクラスの[か](../../mfc/reference/crecordset-class.md#m_strfilter)データ メンバーが、一部の ODBC ドライバーは、他の SQL 句でパラメーターを許可可能性があります。

##  <a name="_core_passing_parameter_values_at_run_time"></a> 実行時にパラメーター値の受け渡し

呼び出す前に、パラメーター値を指定する必要があります`Open`(の新しいレコード セット オブジェクト) または`Requery`(用、既存のもの)。

#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>実行時に、レコード セット オブジェクトをパラメーター値を渡す

1. レコード セット オブジェクトを構築します。

1. 文字列または文字列を準備するなど、 `m_strFilter` SQL ステートメント、またはその一部を含む文字列。 配置"?"パラメーターの情報が移動して、プレース ホルダーです。

1. オブジェクトの各パラメーターのデータ メンバーに、実行時のパラメーター値を割り当てます。

1. 呼び出す、`Open`メンバー関数 (または`Requery`、既存のレコード セットの)。

たとえば、実行時に取得した情報を使用して、レコード セットのフィルター文字列を指定したいとします。 クラスのレコード セットを作成したと仮定`CStudentSet`前: と呼ばれる`rsStudents`: ここで、生徒の情報の特定の種類のクエリを再実行するとします。

```cpp
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

レコード セットには、レコードが含まれる実行時パラメーターから構築されていると、フィルターで指定された条件を満たしている受講者にレコードが含まれています。 この場合、レコード セットには、上級生のレコードが含まれています。

> [!NOTE]
>  Null の場合、パラメーターのデータ メンバーの値を設定するには、必要な場合を使用して[SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull)します。 同様に、パラメーターのデータ メンバーが null の場合でかどうかを確認できますを使用して[調べる](../../mfc/reference/crecordset-class.md#isfieldnull)します。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコード セット:追加、更新、および削除 (Odbc)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[レコード セット:レコード セットの選択が (ODBC) を記録する方法](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
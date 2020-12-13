---
description: '詳細情報: レコードセット: 合計およびその他の集計結果の取得 (ODBC)'
title: 'レコードセット: 集計値の計算 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
ms.openlocfilehash: 10a2ef3b013d9eba0d9733cc321591ae8d6681f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136488"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>レコードセット: 集計値の計算 (ODBC)

> [!NOTE]
> MFC ODBC コンシューマー ウィザードは、Visual Studio 2019 以降はご利用いただけなくなります。 引き続き、コンシューマーを手動で作成することはできます。

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の [SQL](../../data/odbc/sql.md) キーワードを使用して集計の結果を取得する方法について説明します。

- **SUM** では、数値データ型の列において値の合計を計算します。

- **MIN** では、数値データ型の列において最小値を抽出します。

- **MAX** では、数値データ型の列において最大値を抽出します。

- **AVG** では、数値データ型の列において、すべての値の平均値を計算します。

- **COUNT** では、任意のデータ型の列においてレコードの数をカウントします。

これらの SQL 関数は、データ ソースからレコードを抽出するためではなく、データ ソース内のレコードに関する統計情報を取得するために使用します。 作成されるレコードセットは通常、1 つの値を含む 1 つのレコードで構成されます (すべての列が集計列である場合)。 ( **GROUP by** 句を使用した場合、複数のレコードが存在する可能性があります)。この値は、SQL 関数によって実行される計算または抽出の結果です。

> [!TIP]
> SQL **GROUP BY** 句 (および場合によって **HAVING** 句) を SQL ステートメントに追加するには、`m_strFilter`の末尾に追加します。 次に例を示します。

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

列をフィルターおよび並べ替えすることによって、集計結果を得るために使用するレコードの数を制限できます。

> [!CAUTION]
> 一部の集計演算子では、集計される列とは異なるデータ型が返されます。

- **SUM** と **AVG** は次の大きなデータ型を返す場合があります (たとえば、を指定してを呼び出すと、 **`int`** **LONG** またはが返さ **`double`** れます)。

- **COUNT** では通常、ターゲット列の型に関係なく **LONG** が返されます。

- **MAX** および **MIN** では、計算する列と同じデータ型が返されます。

     たとえば、クラスの **追加** ウィザードは **`long`** `m_lSales` Sales 列を格納するために作成しますが、集計結果を格納するには、これをデータメンバーに置き換える必要があり `double m_dblSumSales` ます。 次の例を参照してください。

#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>レコードセットの集計結果を取得するには

1. 「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」の説明に従って、集計結果を取得する基になる列を含むレコードセットを作成します。

1. レコードセットの [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 関数を変更します。 列名を表す文字列 ([RFX](../../data/odbc/record-field-exchange-using-rfx.md) 関数呼び出しの 2 番目の引数) を、列の集計関数を表す文字列に置き換えます。 たとえば、次を置き換えるとします。

    ```
    RFX_Long(pFX, "Sales", m_lSales);
    ```

     次の内容に置き換えます。

    ```
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)
    ```

1. レコードセットを開きます。 集計操作の結果は `m_dblSumSales` に残されています。

> [!NOTE]
> ウィザードでは、実際にはハンガリアン記法の接頭辞を付けずにデータ メンバー名が割り当てられます。 たとえば、ウィザードによって Sales 列に対して生成されるのは、先ほどの説明に使用した `m_lSales` 名ではなく、`m_Sales` です。

データを表示するために [CRecordView](../../mfc/reference/crecordview-class.md) クラスを使用している場合は、新しいデータ メンバー値を表示するように DDX 関数呼び出しを変更する必要があります。この場合、以下を変更します。

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);
```

変更後:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);
```

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

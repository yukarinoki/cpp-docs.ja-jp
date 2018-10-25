---
title: 'レコード セット: 集計とその他の集計の計算 (ODBC) を取得する |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 639c5fb2df443de7e2eee963f942c9154dc4de6e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50058051"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>レコードセット: 集計値の計算 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次を使用して集計の結果を取得する方法を説明します[SQL](../../data/odbc/sql.md)キーワード。

- **合計**数値データ型の列の値の合計を計算します。

- **MIN**数値データ型の列の最小値を抽出します。

- **最大**数値データ型の列の最大値を抽出します。

- **AVG**数値データ型の列のすべての値の平均値を計算します。

- **カウント**任意のデータ型の列内のレコードの数をカウントします。

データ ソースからレコードを抽出するのではなく、データ ソース内のレコードについての統計情報を取得するは、これらの SQL 関数を使用します。 通常作成されるレコード セットは、1 つの値を含む (すべての列は、集計が) 場合に記録します。 (を使用した場合、1 つ以上のレコードにすることがあります、 **GROUP BY**句)。この値は計算または SQL 関数で実行される抽出の結果です。

> [!TIP]
>  SQL を追加する**GROUP BY**句 (および場合によって、 **HAVING**句) するには、SQL ステートメントの末尾に追加`m_strFilter`します。 例えば:

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

フィルター選択、列の並べ替えと集計の結果を得るために使用するレコードの数を制限することができます。

> [!CAUTION]
>  いくつかの集計演算子は、集計される列から別のデータ型を返します。

- **合計**と**AVG**次の大きいデータ型を返す可能性があります (などを呼び出す`int`返します**長い**または**二重**)。

- **カウント**通常返します**長い**ターゲット列の種類に関係なく。

- **最大**と**MIN**計算列と同じデータ型を返します。

     たとえば、**クラスの追加**ウィザードによって作成されます`long``m_lSales`が Sales 列では、対応するために、これを置き換える必要があります、`double m_dblSumSales`集計結果に対応するデータ メンバー。 次の例を参照してください。

#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>レコード セットの集計結果を取得するには

1. レコード セットの作成」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)集計結果を取得する列を格納しています。

1. 変更、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)レコード セットの関数。 列名を表す文字列に置き換えます (2 番目の引数の[RFX](../../data/odbc/record-field-exchange-using-rfx.md)関数呼び出し) 列の集計関数を表す文字列を使用します。 たとえば、次のように置き換えます。

    ```
    RFX_Long(pFX, "Sales", m_lSales);
    ```

     次の内容に置き換えます。

    ```
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)
    ```

1. レコード セットを開きます。 集計操作の結果のままに`m_dblSumSales`します。

> [!NOTE]
>  ウィザードは、実際には、ハンガリー語プレフィックスなしのデータ メンバー名を割り当てます。 ウィザードは、たとえば、 `m_Sales` 、売上の列ではなく、`m_lSales`名の前の図に使用します。

使用する場合、 [CRecordView](../../mfc/reference/crecordview-class.md)クラスのデータを表示する、新しいデータ メンバー値を表示する、DDX 関数の呼び出しを変更する必要がここでは、変更することから。

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);
```

移動先:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);
```

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
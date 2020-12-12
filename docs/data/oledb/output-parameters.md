---
description: '詳細情報: 出力パラメーター'
title: 出力パラメーター
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
ms.openlocfilehash: c52877483d40d7de1a8313eb806769ce92af7337
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316935"
---
# <a name="output-parameters"></a>出力パラメーター

ストアドプロシージャの呼び出しは、SQL コマンドの実行に似ています。 主な違いは、ストアドプロシージャでは、出力パラメーター (または "outparameters") と戻り値を使用することです。

次のストアドプロシージャでは、最初の '? ' は戻り値 (phone)、2番目の '? ' は入力パラメーター (name) です。

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

パラメーターマップで in パラメーターと out パラメーターを指定します。

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

アプリケーションでは、ストアドプロシージャから返された出力を処理する必要があります。 結果の処理中には、さまざまな OLE DB プロバイダーからさまざまなタイミングで出力パラメーターと戻り値が返されます。 たとえば、Microsoft OLE DB provider for SQL Server (SQLOLEDB) は、ストアドプロシージャから返された結果セットをコンシューマーが取得またはキャンセルした後に、出力パラメーターとリターンコードを提供しません。 出力は、サーバーからの最後の TDS パケットで返されます。

## <a name="row-count"></a>行数

OLE DB コンシューマーテンプレートを使用して、outparameters を持つストアドプロシージャを実行する場合、行セットを閉じるまで行数は設定されません。

たとえば、行セットと outparameter を持つストアドプロシージャを考えてみます。

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

`@_rowcount`Outparameter は、テストテーブルから返された行数を報告します。 ただし、このストアドプロシージャでは行の数が50に制限されます。 たとえば、テストで100行があった場合、rowcount は50になります (このコードでは上位の50行のみが取得されるため)。 テーブルに30行しかない場合、rowcount は30になります。 `Close` `CloseAll` 値をフェッチする前に、またはを呼び出して、outparameter を設定してください。

## <a name="see-also"></a>関連項目

[ストアドプロシージャの使用](../../data/oledb/using-stored-procedures.md)

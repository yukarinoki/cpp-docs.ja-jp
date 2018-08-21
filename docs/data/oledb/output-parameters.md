---
title: 出力パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae742f27f7e2fd13de9acfc3c814b36c85e9e106
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339027"
---
# <a name="output-parameters"></a>出力パラメーター
ストアド プロシージャの呼び出しは、SQL コマンドの呼び出しに似ています。 主な違いは、ストアド プロシージャが出力パラメーター (または"出力パラメーター") を使用して、戻り値です。  
  
 ストアド プロシージャを次のように最初の ' ですか? '戻り値 (電話) と、2 つ目は、'?' (名) の入力パラメーターです。  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 パラメーターのマップでは、in、out パラメーターを指定します。  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 アプリケーションでは、ストアド プロシージャから返された出力を処理する必要があります。 さまざまな OLE DB プロバイダーでは、出力パラメーターを返すし、結果の処理中にさまざまなタイミングで戻り値。 たとえば、Microsoft OLE DB provider for SQL Server (SQLOLEDB) が出力パラメーターを指定しない、およびまでコードを返す、コンシューマーが取得またはストアド プロシージャによって返される結果セットが取り消されましたは。 出力は、最後の TDS パケットで、サーバーから返されます。  
  
## <a name="row-count"></a>行の数  
 出力パラメーターを持つストアド プロシージャを実行する OLE DB コンシューマー テンプレートを使用する場合行の数は、行セットを終了するまで設定されません。  
  
 たとえば、行セットと、出力パラメーターを使用してストアド プロシージャを考えてみます。  
  
```sql  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @_rowcount出力パラメーターは、行の数は、実際にテスト テーブルから返されたを報告します。 ただし、このストアド プロシージャは、最大 50 個の行の数を制限します。 たとえば、テストでの 100 行がある場合は、(このコードでは、上位 50 行のみを取得します) ために、行数は 50 になります。 テーブルには、30 行あったのみ、行数が 30 になります。 呼び出す必要があります`Close`または`CloseAll`値をフェッチする前に、出力パラメーターを設定します。  
  
## <a name="see-also"></a>関連項目  
 [ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)
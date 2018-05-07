---
title: 出力パラメーター |Microsoft ドキュメント
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
ms.openlocfilehash: 8733b967ddab7e6f68fcbee1c80e78500a679f96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="output-parameters"></a>出力パラメーター
ストアド プロシージャの呼び出しは、SQL コマンドの呼び出しに似ています。 主な違いは、ストアド プロシージャが出力パラメーター (または「出力パラメーター」) を使用して、戻り値です。  
  
 次のストアド プロシージャ、最初 '? '戻り値 (phone) と、2 つ目は、'?' (名) の入力パラメーターは。  
  
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
  
 アプリケーションでは、ストアド プロシージャから返される出力を処理する必要があります。 さまざまな OLE DB プロバイダーでは、出力パラメーターを取得し、結果の処理中に、異なる時刻で値を返します。 やなどの Microsoft OLE DB プロバイダーの SQL Server (SQLOLEDB) はない出力パラメーターを指定する、コンシューマーが取得されたまたはストアド プロシージャによって返される結果セットを取り消されるまでのコードを返します。 出力は、サーバーから最後の TDS パケットで返されます。  
  
## <a name="row-count"></a>行の数  
 出力パラメーターを持つストアド プロシージャを実行する OLE DB コンシューマー テンプレートを使用する場合、行セットを終了するまで、行の数は設定されません。  
  
 たとえば、行セットと、出力パラメーターを持つストアド プロシージャについて考えてみます。  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @_rowcount行の数は、実際にテストのテーブルから返された出力パラメーターをレポートします。 ただし、このストアド プロシージャは、最大 50 個の行の数を制限します。 たとえば、テストで 100 行があった場合、行数は 50 になります (ため、このコードは、上位 50 行のみを取得します)。 発生した場合のみ 30 行の表に、行カウントが 30 になります。 呼び出す必要があります**閉じる**または**CloseAll**をその値をフェッチする前に、出力パラメーターを設定します。  
  
## <a name="see-also"></a>関連項目  
 [ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)
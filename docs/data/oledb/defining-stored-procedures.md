---
title: ストアド プロシージャの定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e03a5ae2e7c75d905216a6be92630376484d047
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="defining-stored-procedures"></a>ストアド プロシージャの定義
ストアド プロシージャを呼び出す前にする必要があります最初にそれを定義してを使用して、 [DEFINE_COMMAND](../../data/oledb/define-command.md)マクロです。 コマンドを定義するときに、パラメーター マーカーとして疑問符 (?) でパラメーターを表します。  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 このトピックのコード例で使用される構文 (中かっこの使用など) が SQL Server に固有である注意してください。 ストアド プロシージャで使用する構文を使用するプロバイダーに応じて異なる可能性があります。  
  
 次に、マップでは、パラメーターには、コマンドで発生した順序でパラメーターを一覧表示のコマンドで使用したパラメーターを指定します。  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 前の例は、ストアド プロシージャを定義します。 通常、コードの再利用できるように効率的なデータベースのセットを含む"Year Sales"や"dt_adduserobject"などの名前を持つ定義済みのストアド プロシージャ SQL Server Enterprise Manager を使用してその定義を表示することができます。 次のように呼び出します (の配置、'?' パラメーターは、ストアド プロシージャのインターフェイスによって異なります)。  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 次に、コマンド クラスを宣言します。  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>  
```  
  
 最後に、ストアド プロシージャを呼び出して`OpenRowset`次のようにします。  
  
```  
CSession m_session;  

HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);  
}  
```  
  
 データベース属性を使用してストアド プロシージャを定義できることにも注意してください[db_command](../../windows/db-command.md)次のようにします。  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## <a name="see-also"></a>関連項目  
 [ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)
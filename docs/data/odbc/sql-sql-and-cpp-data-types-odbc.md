---
title: 'SQL: SQL と C++ のデータ型 (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6a137c4f648f518420d06f5cbd98ea189a030aee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL と C++ のデータ型 (ODBC)
> [!NOTE]
>  この情報は、MFC ODBC クラスに適用されます。 MFC DAO クラスを使用する場合は、"比較の Microsoft Jet データベース エンジン SQL と ANSI SQL"DAO ヘルプのトピックを参照してください。  
  
 次の表は、ANSI SQL データ型を C++ のデータ型にマップします。 これにより、C 言語を指定した情報の付録 D が強化、 *ODBC SDK* *プログラマーズ リファレンス*MSDN ライブラリの CD にします。 ウィザードでは、ほとんどのデータ型のマッピングを管理します。 ウィザードを使用しない場合は、フィールド exchange コードを手動で作成するのに役立つマッピング情報を使用することができます。  
  
### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ のデータ型にマップされている ANSI SQL データ型  
  
|ANSI SQL データ型|C++ データ型|  
|------------------------|---------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**INTEGER**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT 型**|`CString` 1|  
|**バイナリ**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**時間**|**CTime、CString**|  
|**TIMESTAMP**|**CTime、CString**|  
  
 1. ANSI **DECIMAL**と**数値**マップ`CString`ため**SQL_C_CHAR** ODBC の既定の転送種類は、します。  
  
 2. マップされているときに既定では 255 文字を超える文字データは切り捨てられます`CString`です。 切り捨ての長さを拡張するには明示的に設定して、`nMaxLength`の引数`RFX_Text`です。  
  
 3. マップされているときに既定では 255 文字を超えるバイナリ データは切り捨てられます`CByteArray`です。 切り捨ての長さを拡張するには明示的に設定して、`nMaxLength`の引数`RFX_Binary`です。  
  
 ODBC カーソル ライブラリを使用していない 2 つの更新を試みているとき、または、Microsoft SQL Server ODBC ドライバーと、MFC ODBC データベース クラスを使用して複数の長い可変長フィールドに問題が発生した可能性があります。 ODBC 型**SQL_LONGVARCHAR**と**SQL_LONGVARBINARY**テキストにマップ、およびイメージの SQL Server の種類。 A`CDBException`に同じ呼び出しで 2 つ以上の長い可変長のフィールドを更新する場合にスローされる`CRecordset::Update`です。 そのため、同時に、複数の長い列を更新しない`CRecordset::Update`です。 長い列が複数を同時に更新するには、ODBC API で**SQLPutData**です。 ODBC カーソル ライブラリを使用することもできますが、これは、カーソルをサポートし、カーソル ライブラリは必要ありません、SQL Server ドライバーなどのドライバーは推奨されません。  
  
 MFC ODBC データベース クラスと、Microsoft SQL Server ODBC ドライバーの ODBC カーソル ライブラリを使用している場合、 **ASSERT**と共に発生する可能性があります、`CDBException`への呼び出し`CRecordset::Update`への呼び出しに依存して`CRecordset::Requery`です。 代わりに、`CRecordset::Close`と`CRecordset::Open`なく`CRecordset::Requery`です。 別のソリューションをいないと、ODBC カーソル ライブラリが不要なネイティブ サポートするために ODBC カーソル ライブラリを使用します。  
  
## <a name="see-also"></a>関連項目  
 [SQL](../../data/odbc/sql.md)   
 [SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
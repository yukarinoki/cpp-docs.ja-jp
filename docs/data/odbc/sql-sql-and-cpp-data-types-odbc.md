---
description: '詳細情報: sql: SQL と C++ のデータ型 (ODBC)'
title: 'SQL: SQL と C++ のデータ型 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 7dd0e4fe94ef61436a7a62e1bb653e803c0b6168
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185974"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL と C++ のデータ型 (ODBC)

> [!NOTE]
> この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合は、DAO ヘルプの「Microsoft Jet データベースエンジン SQL および ANSI SQL の比較」を参照してください。

次の表では、ANSI SQL データ型を C++ データ型にマップしています。 これにより、 [ODBC プログラマーリファレンス](/sql/odbc/reference/odbc-programmer-s-reference) ドキュメントの付録 D に記載されている C 言語情報が強化されます。 ほとんどのデータ型マッピングは、ウィザードによって管理されます。 ウィザードを使用しない場合は、マッピング情報を使用してフィールド交換コードを手動で記述できます。

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ データ型にマップされた ANSI SQL データ型

|ANSI SQL データ型|C++ データ型|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**DECIMAL**|`CString` 1|
|**SMALLINT**|**`int`**|
|**REAL**|**`float`**|
|**INTEGER**|**`long`**|
|**FLOAT**|**`double`**|
|**DOUBLE**|**`double`**|
|**NUMERIC**|`CString` 1|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`、 `CString` 2|
|**BIT**|**型**|
|**TINYINT**|**BYTE**|
|**BIGINT**|`CString` 1|
|**バイナリ**|`CByteArray`|
|**可変長**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`、 `CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**TIME**|`CTime`, `CString`|
|**TIMESTAMP**|`CTime`, `CString`|

1. ANSI **DECIMAL** および **NUMERIC** はにマップ `CString` されます。これは **SQL_C_CHAR** が既定の ODBC 転送型であるためです。

2. 255文字を超える文字データは、にマップされるときに既定で切り捨てられ `CString` ます。 の *Nmaxlength* 引数を明示的に設定することにより、切り捨ての長さを拡張でき `RFX_Text` ます。

3. にマップした場合、255文字を超えるバイナリデータは既定で切り捨てられ `CByteArray` ます。 の *Nmaxlength* 引数を明示的に設定することにより、切り捨ての長さを拡張でき `RFX_Binary` ます。

ODBC カーソルライブラリを使用していない場合、Microsoft SQL Server ODBC ドライバーおよび MFC ODBC データベースクラスを使用して、複数の長い可変長フィールドを更新しようとすると問題が発生することがあります。 ODBC の型、 **SQL_LONGVARCHAR** および **SQL_LONGVARBINARY** は、text および image SQL Server 型にマップされます。 `CDBException`を同じ呼び出しで2つ以上の長い可変長フィールドを更新すると、がスローされ `CRecordset::Update` ます。 そのため、複数の長い列をで同時に更新しないで `CRecordset::Update` ください。 ODBC API では、複数の長い列を同時に更新でき `SQLPutData` ます。 ODBC カーソルライブラリを使用することもできますが、カーソルをサポートし、カーソルライブラリを必要としないドライバー (SQL Server ドライバーなど) には使用しないことをお勧めします。

ODBC カーソルライブラリを MFC ODBC データベースクラスおよび Microsoft SQL Server ODBC ドライバーと共に使用している場合、への呼び出しがの呼び出しに続いている場合は、 **アサート** がと共に発生する可能性があり `CDBException` `CRecordset::Update` `CRecordset::Requery` ます。 代わりに、で `CRecordset::Close` `CRecordset::Open` はなくを呼び出し `CRecordset::Requery` ます。 別の解決策として、ODBC カーソルライブラリを使用しないこともできます。これは、SQL Server と SQL Server ODBC ドライバーがカーソルをネイティブでサポートしており、ODBC カーソルライブラリが不要なためです。

## <a name="see-also"></a>関連項目

[SQL](../../data/odbc/sql.md)<br/>
[SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

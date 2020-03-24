---
title: 'SQL: SQL と C++ のデータ型 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 1c1ce908b5c8d345906d49adc79e322225ed49f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212616"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL と C++ のデータ型 (ODBC)

> [!NOTE]
>  この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合は、DAO ヘルプの「Microsoft Jet データベースエンジン SQL および ANSI SQL の比較」を参照してください。

次の表では、ANSI SQL データC++型をデータ型にマップしています。 これにより、MSDN ライブラリ CD の*ODBC SDK* *プログラマーリファレンス*の付録 D に記載されている C 言語情報が強化されます。 ほとんどのデータ型マッピングは、ウィザードによって管理されます。 ウィザードを使用しない場合は、マッピング情報を使用してフィールド交換コードを手動で記述できます。

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>データ型にC++マップされる ANSI SQL データ型

|ANSI SQL データ型|C++ データ型|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**DECIMAL**|`CString` 1|
|**SMALLINT**|**int**|
|**REAL**|**float**|
|**INTEGER**|**long**|
|**FLOAT**|**double**|
|**DOUBLE**|**double**|
|**NUMERIC**|`CString` 1|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`、`CString` 2|
|**BIT**|**BOOL**|
|**TINYINT**|**BYTE**|
|**BIGINT**|`CString` 1|
|**バイナリ**|`CByteArray`|
|**可変長**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`、`CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**TIME**|`CTime`, `CString`|
|**TIMESTAMP**|`CTime`, `CString`|

1. ANSI **DECIMAL**および**NUMERIC** map for `CString` には、 **SQL_C_CHAR**が既定の ODBC 転送型であるためです。

2. 255文字を超える文字データは、`CString`にマップされると、既定では切り捨てられます。 `RFX_Text`の*Nmaxlength*引数を明示的に設定することにより、切り捨ての長さを拡張できます。

3. 255文字を超えるバイナリデータは、`CByteArray`にマップされると、既定では切り捨てられます。 `RFX_Binary`の*Nmaxlength*引数を明示的に設定することにより、切り捨ての長さを拡張できます。

ODBC カーソルライブラリを使用していない場合、Microsoft SQL Server ODBC ドライバーおよび MFC ODBC データベースクラスを使用して、複数の長い可変長フィールドを更新しようとすると問題が発生することがあります。 ODBC の型、 **SQL_LONGVARCHAR**および**SQL_LONGVARBINARY**は、text および image SQL Server 型にマップされます。 同じ呼び出しで2つ以上の長い可変長フィールドを `CRecordset::Update`に更新すると、`CDBException` がスローされます。 そのため、`CRecordset::Update`では、複数の長い列を同時に更新しないでください。 ODBC API `SQLPutData`を使用すると、複数の長い列を同時に更新できます。 ODBC カーソルライブラリを使用することもできますが、カーソルをサポートし、カーソルライブラリを必要としないドライバー (SQL Server ドライバーなど) には使用しないことをお勧めします。

ODBC カーソルライブラリを MFC ODBC データベースクラスおよび Microsoft SQL Server ODBC ドライバーと共に使用している場合、`CRecordset::Update` の呼び出しが `CRecordset::Requery`の呼び出しに続いている場合、`CDBException` と共に**アサート**が発生する可能性があります。 代わりに、`CRecordset::Requery`ではなく `CRecordset::Close` と `CRecordset::Open` を呼び出します。 別の解決策として、ODBC カーソルライブラリを使用しないこともできます。これは、SQL Server と SQL Server ODBC ドライバーがカーソルをネイティブでサポートしており、ODBC カーソルライブラリが不要なためです。

## <a name="see-also"></a>参照

[SQL](../../data/odbc/sql.md)<br/>
[SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

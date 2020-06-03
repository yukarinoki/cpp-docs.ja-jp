---
title: 'SQL: SQL と C++ のデータ型 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: cffe44b832ac1eb28d368072b8f0e92ea9f57feb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374474"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL と C++ のデータ型 (ODBC)

> [!NOTE]
> この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合は、DAO ヘルプのトピック「Microsoft Jet データベース エンジン SQL と ANSI SQL の比較」を参照してください。

次の表は、ANSI SQL データ型を C++ データ型にマップしています。 これにより、MSDN ライブラリ CD の*ODBC SDK* *プログラマ リファレンス*の付録 D に示す C 言語情報が強化されます。 ウィザードは、ほとんどのデータ型マッピングを管理します。 ウィザードを使用しない場合は、マッピング情報を使用して、フィールド交換コードを手動で記述できます。

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ データ型にマップされた ANSI SQL データ型

|ANSI SQL データ型|C++ データ型|
|------------------------|---------------------|
|**Char**|`CString`|
|**10 進**|`CString`1|
|**Smallint**|**int**|
|**本当の**|**float**|
|**整数**|**長い**|
|**フロート**|**double**|
|**ダブル**|**double**|
|**数値**|`CString`1|
|**Varchar**|`CString`|
|**ロングバーチャル**|`CLongBinary`、2 `CString`|
|**ビット**|**Bool**|
|**Tinyint**|**バイト**|
|**Bigint**|`CString`1|
|**バイナリ**|`CByteArray`|
|**Varbinary**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`、3 `CByteArray`|
|**日付**|`CTime`, `CString`|
|**時間**|`CTime`, `CString`|
|**タイムスタンプ**|`CTime`, `CString`|

1. SQL_C_CHAR**がデフォルト**の ODBC 転送`CString`タイプであるため、ANSI **DECIMAL**および**NUMERIC**マップがデフォルトの ODBC 転送タイプであるため、

2. 255 文字を超える文字データは、 に`CString`マップされると、既定で切り捨てられます。 切り捨ての長さを拡張するには *、nMaxLength*引数を`RFX_Text`明示的に設定します。

3. 255 文字を超えるバイナリ データは、 に`CByteArray`マップされると既定で切り捨てられます。 切り捨ての長さを拡張するには *、nMaxLength*引数を`RFX_Binary`明示的に設定します。

ODBC カーソル ライブラリを使用していない場合は、MICROSOFT SQL Server ODBC ドライバと MFC ODBC データベース クラスを使用して、2 つ以上の長い可変長フィールドを更新しようとすると、問題が発生することがあります。 ODBC 型 **、SQL_LONGVARCHAR**および**SQL_LONGVARBINARY**は、テキストおよびイメージ SQL Server 型にマップされます。 A`CDBException`は、同じ呼び出しで 2 つ以上の長い`CRecordset::Update`可変長フィールドを更新するとスローされます。 したがって、複数の長い列をで`CRecordset::Update`同時に更新しないでください。 ODBC API`SQLPutData`を使用して、複数の長い列を同時に更新できます。 ODBC カーソル ライブラリを使用することもできますが、SQL Server ドライバなどのドライバでは、カーソルをサポートし、カーソル ライブラリを必要としないドライバには推奨されません。

MFC ODBC データベース クラスと共に ODBC カーソル ライブラリを使用し、ODBC ドライバを使用している場合は、`CDBException`呼び出`CRecordset::Update`しの後に呼`CRecordset::Requery`び出しを行う場合に、 と共に**アサート**が発生する可能性があります。 代わりに、 `CRecordset::Close` `CRecordset::Open`ではなく`CRecordset::Requery`を呼び出します。 SQL Server と SQL Server ODBC ドライバはネイティブでカーソルをサポートし、ODBC カーソル ライブラリは必要ないので、ODBC カーソル ライブラリを使用しないもう 1 つの解決策があります。

## <a name="see-also"></a>関連項目

[SQL](../../data/odbc/sql.md)<br/>
[SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

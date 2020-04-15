---
title: ODBC データ ソースでのテーブルのプログラム作成
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 6cf26cad7fe39f374daf371902525087b446658c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358839"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>データ ソース: プログラムにおける ODBC データ ソースのテーブルの作成

このトピックでは、CREATE **TABLE** SQL ステートメントを含む文字列`ExecuteSQL`を関数に渡`CDatabase`すクラスのメンバー関数を使用して、データ ソースのテーブルを作成する方法について説明します。

MFC の ODBC データ ソースの一般情報については、「[データ ソース (ODBC) 」](../../data/odbc/data-source-odbc.md)を参照してください。 「[データ ソース: プログラムによる ODBC データ ソースの設定](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md)」では、データ ソースの作成について説明します。

データ ソースを確立すると、メンバー関数と**CREATE TABLE** `ExecuteSQL` SQL ステートメントを使用してテーブルを簡単に作成できます。 たとえば、`CDatabase``myDB`というオブジェクトがある場合は、次の MFC コードを使用してテーブルを作成できます。

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

このコード例では、Access データ ソース接続に "OFFICES" というテーブルを`myDB`作成します。テーブルには、"OfficeID" と "Office 名" の 2 つのフィールドが含まれています。

> [!NOTE]
> **CREATE TABLE** SQL ステートメントで指定されるフィールド・タイプは、使用している ODBC ドライバーによって異なる場合があります。 Visual C++ 1.5 で配布される Microsoft クエリ プログラムは、データ ソースで使用できるフィールドの種類を検出する方法の 1 つです。 Microsoft Query で、[**ファイル**] をクリックし **、[Table_Definition]** をクリックします。 **Type** インデックスを作成するための SQL 構文も存在します。

## <a name="see-also"></a>関連項目

[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)

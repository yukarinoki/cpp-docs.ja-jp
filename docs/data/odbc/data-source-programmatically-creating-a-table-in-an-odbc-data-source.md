---
title: プログラムによって ODBC データソースにテーブルを作成する
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 25c975560d6a73ce67294d97830b2f5bec9cd635
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213279"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>データ ソース: プログラムにおける ODBC データ ソースのテーブルの作成

このトピックでは、クラス `CDatabase`の `ExecuteSQL` メンバー関数を使用して、データソースのテーブルを作成する方法について説明し、 **CREATE TABLE** SQL ステートメントを含む文字列を関数に渡します。

MFC の ODBC データソースに関する一般的な情報については、「[データソース (odbc)](../../data/odbc/data-source-odbc.md)」を参照してください。 トピック「[データソース: プログラムによる ODBC データソースの構成](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md)」では、データソースの作成について説明します。

データソースが確立されている場合は、`ExecuteSQL` メンバー関数と**CREATE TABLE** SQL ステートメントを使用してテーブルを簡単に作成できます。 たとえば、`myDB`という `CDatabase` オブジェクトがある場合、次の MFC コードを使用してテーブルを作成できます。

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

このコード例では、`myDB`によって管理される Microsoft Access データソース接続に "オフィス" という名前のテーブルを作成します。このテーブルには、2つのフィールド "OfficeID" と "オフィスの Ename" が含まれています。

> [!NOTE]
>  **CREATE TABLE** SQL ステートメントで指定されたフィールドの種類は、使用している ODBC ドライバーによって異なる場合があります。 Microsoft Query プログラム (Visual C++ 1.5 で配布) は、データソースで使用できるフィールドの種類を検出するための1つの方法です。 Microsoft Query で、 **[ファイル]** をクリックし、 **[Table_Definition]** をクリックします。次に、データソースからテーブルを選択し、 **[型]** コンボボックスに表示されている型を確認します。 インデックスを作成するための SQL 構文も存在します。

## <a name="see-also"></a>参照

[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)

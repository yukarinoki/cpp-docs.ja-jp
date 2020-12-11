---
description: '詳細については、「データソース: プログラムによる ODBC データソースでのテーブルの作成」を参照してください。'
title: プログラムによって ODBC データソースにテーブルを作成する
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: b195cc4fb81f1caed0b280c5df6a2032f4944ddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155710"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>データ ソース: プログラムにおける ODBC データ ソースのテーブルの作成

このトピックでは、クラスのメンバー関数を使用して、データソースのテーブルを作成し、 `ExecuteSQL` `CDatabase` **CREATE TABLE** SQL ステートメントを含む文字列を関数に渡す方法について説明します。

MFC の ODBC データソースに関する一般的な情報については、「 [データソース (odbc)](../../data/odbc/data-source-odbc.md)」を参照してください。 トピック「 [データソース: プログラムによる ODBC データソースの構成](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) 」では、データソースの作成について説明します。

データソースが確立されている場合は、 `ExecuteSQL` メンバー関数と **CREATE TABLE** SQL ステートメントを使用してテーブルを簡単に作成できます。 たとえば、 `CDatabase` というオブジェクトがある場合、 `myDB` 次の MFC コードを使用してテーブルを作成できます。

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

このコード例では、によって保持されている Microsoft Access データソース接続に "オフィス" という名前のテーブルを作成し `myDB` ます。このテーブルには、"OfficeID" と "/" の2つのフィールドがあります。

> [!NOTE]
> **CREATE TABLE** SQL ステートメントで指定されたフィールドの種類は、使用している ODBC ドライバーによって異なる場合があります。 Microsoft クエリプログラム (Visual C++ 1.5 で配布) は、データソースで使用できるフィールドの種類を検出するための1つの方法です。 Microsoft Query で、[ **ファイル**] をクリックし、[ **Table_Definition**] をクリックします。次に、データソースからテーブルを選択し、[ **型** ] コンボボックスに表示されている型を確認します。 インデックスを作成するための SQL 構文も存在します。

## <a name="see-also"></a>関連項目

[データソース (ODBC)](../../data/odbc/data-source-odbc.md)

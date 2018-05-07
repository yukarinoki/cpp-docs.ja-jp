---
title: プログラムによって、ODBC データ ソースにテーブルを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5ea8ddc8e683c0e5f0681bdf98cbddca180e4023
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>データ ソース: プログラムにおける ODBC データ ソースのテーブルの作成
このトピックのデータ テーブルを作成する方法について説明を使用して、ソース、`ExecuteSQL`クラスのメンバー関数`CDatabase`、関数を含む文字列に渡すこと、 **CREATE TABLE** SQL ステートメント。  
  
 MFC での ODBC データ ソースの概要については、次を参照してください。[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)です。 トピック[データ ソース: プログラムにおける ODBC データ ソースの設定](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md)データ ソースの作成について説明します。  
  
 確立されたデータ ソースがある場合は、ときにを使用してテーブルを簡単に作成できます、`ExecuteSQL`メンバー関数および**CREATE TABLE** SQL ステートメント。 あった場合など、`CDatabase`と呼ばれるオブジェクト`myDB`テーブルを作成する次の MFC コードを使用できます。  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 このコード例で保持されている Microsoft Access データ ソース接続で「オフィス」と呼ばれるテーブルを作成`myDB`; テーブルには、2 つのフィールド"OfficeID"と"OfficeName"が含まれています。  
  
> [!NOTE]
>  指定されたフィールドの種類、 **CREATE TABLE** SQL ステートメントを使用している ODBC ドライバーによって異なる可能性があります。 (Visual C++ 1.5 を含む)、Query プログラムは、データ ソースに使用できるフィールドの型を検出する方法の 1 つです。 Query 内をクリックして**ファイル**、 をクリックして**Table_Definition**データ ソースからテーブルを選択してに表示されている型を見て、**型**コンボ ボックス。 SQL 構文は、インデックスの作成にも存在します。  
  
## <a name="see-also"></a>関連項目  
 [データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)
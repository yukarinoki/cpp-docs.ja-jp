---
title: OLE DB プログラミング |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3f447c2cc45e0ccc96a1480b9d521f1bde09c9e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677210"
---
# <a name="ole-db-programming"></a>OLE DB プログラミング
Microsoft OLE DB は、レガシ テクノロジです。新しいアプリケーションのリンクされた SQL サーバーの必要なデータ アクセス API になります。 その他のすべての新しいアプリケーションでは、ODBC を使用する必要があります。 SQL Server の現在の OLE DB プロバイダーでは、SQLNCLI11 です。DLL です。 プロバイダーは SQL Server 2016 で引き続き出荷されています。 このドキュメントは、OLE DB を既に使用している既存のアプリケーションを保持している開発者を対象としています。
  
 OLE DB テンプレートは、一般的に使用される多数の OLE DB インターフェイスを実装するクラスを提供して、高性能な OLE DB データベース テクノロジを使いやすくする C++ テンプレートです。 このテンプレート ライブラリはコンシューマー テンプレートとプロバイダー テンプレートに分かれています。  
  
 Visual C++ には OLE DB のスターター アプリケーションを作成するためのウィザードのサポートもあります。  
  
 また、属性を使って OLE DB コンシューマー テンプレートを実装することもできます。  
  
|詳細情報|参照トピック|  
|-------------------------|---------|  
|OLE DB コンシューマー テンプレートの使用方法 (概念説明のトピック)|[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)|  
|OLE DB プロバイダー テンプレートの使用方法 (概念説明のトピック)|[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)|  
|OLE DB テンプレート クラスおよびマクロ|[OLE DB テンプレート リファレンス](../../data/oledb/ole-db-templates.md)(Visual C)|  
|OLE DB コンシューマー属性|[OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)|  
|OLE DB インターフェイス|[OLE DB プログラマーズ リファレンス](/previous-versions/windows/desktop/ms713643\(v=vs.85\))(では、Windows SDK)|  
|OLE DB テンプレート サンプル|[OLE DB テンプレート サンプル](https://github.com/Microsoft/VCSamples)| 
|データ アクセス プログラミングの概要 (Visual C++)|[データ アクセス プログラミング](../../data/data-access-programming-mfc-atl.md)|  
|ODBC の概念説明のトピック|[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)|  

## <a name="see-also"></a>関連項目  
 [データ アクセス](../data-access-in-cpp.md)
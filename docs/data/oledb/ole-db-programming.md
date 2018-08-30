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
ms.openlocfilehash: 5d5804a7437dabd688abab04ebdd50a79decbaaa
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198770"
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
|OLE DB テンプレート サンプル|[OLE DB テンプレート サンプル](https://msdn.microsoft.com/08958863-0b5f-41ad-ae99-fca7440c553c)| 
|データ アクセス プログラミングの概要 (Visual C++)|[データ アクセス プログラミング](../../data/data-access-programming-mfc-atl.md)|  
|ODBC の概念説明のトピック|[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)|  

## <a name="see-also"></a>関連項目  
 [データ アクセス](../data-access-in-cpp.md)
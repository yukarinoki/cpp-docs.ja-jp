---
title: データベース サポート ファイルの再頒布 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- redistributing database support files
- database support files [C++], redistributing
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51697367480569e2d27a4cb67791f5fe4d39a8f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33323876"
---
# <a name="redistributing-database-support-files"></a>データベース サポート ファイルの再頒布
データ アクセス オブジェクト (DAO: Data Access Object) 用のサポート ファイルの再配布、および Microsoft Data Access SDK のデータベース テクノロジのサポート ファイルの再配布が可能です。  
  
## <a name="installing-dao-support-files"></a>DAO サポート ファイルのインストール  
 DAO の最新バージョンを入手する方法については、Microsoft サポートの Web サイトの「[文書番号 239114: Microsoft Jet 4.0 データベース エンジン用の最新の Service Pack の入手方法](http://go.microsoft.com/fwlink/p/?linkid=198014)」を参照してください。  
  
## <a name="installing-microsoft-data-access-sdk-support-files"></a>Microsoft Data Access SDK のサポート ファイル  
 Mdac_typ.exe を使用して、ODBC、OLE DB、ActiveX データ オブジェクト (ADO: ActiveX Data Object)、および RDS (Remote Data Services) に対するサポートをインストールします。 Mdac_typ.exe は、Visual Studio インストール メディアの \WCU\MDAC28\ フォルダーにあります。 Mdac_typ.exe は、[Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/p/?linkid=198015)の Web サイトからもダウンロードできます。  
  
 詳細については、[MSDN](http://go.microsoft.com/fwlink/p/?linkid=198016) Web サイトで、「Redistributing MDAC 2.8 SP1」 (MDAC 2.8 SP1 の再配布) を検索してください。 Visual Studio セットアップ プロジェクトを使用してアプリケーションを配置する場合は、「[配置と依存関係](http://msdn.microsoft.com/en-us/49e9b84d-bd6a-4388-b9ac-46ea79cf0733)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)
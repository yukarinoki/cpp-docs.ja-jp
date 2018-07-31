---
title: OLE DB アーキテクチャのデザインの問題 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b080945309732bec06c63eb665bbf6dd5f4acb5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340564"
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB アーキテクチャのデザインの問題
OLE DB アプリケーションを開始する前に、次の問題を考慮してください。  
  
 **OLE DB アプリケーションを記述するプログラミング実装を使用するか。**  
 Microsoft には、これを実現するいくつかのライブラリが用意されています。 OLE DB テンプレート ライブラリを、OLE DB 属性、および OLE DB SDK では、生の OLE DB インターフェイス。 さらでは、ウィザード ・、プログラムを記述する際に役立つことがあります。 これらの実装については、後述[OLE DB テンプレート、属性、およびその他の実装](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md)します。  
  
 **独自のプロバイダーを記述する必要がありますか。**  
 ほとんどの開発者は、独自のプロバイダーを作成する必要はありません。 Microsoft では、いくつかのプロバイダーを提供します。 (たとえば、コンシューマーを ATL OLE DB コンシューマー ウィザードを使用してプロジェクトに追加する場合)、データ接続を作成するたびに、**データ リンク プロパティ** ダイアログ ボックスには、システムに登録されているすべての利用可能なプロバイダーが一覧表示されます。 これらのプロバイダーのいずれかが、独自のデータ ストアとデータ アクセス アプリケーションの適切な場合は、これらのいずれかは、最も簡単な操作を行います。 ただし、データ ストアがこれらのカテゴリのいずれかにも収まらない場合、独自のプロバイダーを作成する必要あります。 プロバイダーを作成する方法の詳細については、次を参照してください。 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)します。  
  
 **コンシューマーに必要なレベルのサポート**  
 一部のコンシューマーは、非常に基本的です;他のユーザーは、非常に複雑になることができます。 OLE DB オブジェクトの機能は、プロパティによって指定されます。 ATL OLE DB コンシューマー ウィザードを使用してプロバイダーを作成するには、コンシューマーまたはデータベース プロバイダーのウィザードを作成するときに、標準的な一連の機能を提供する適切なオブジェクトのプロパティを設定します。 ただし、ウィザードで生成されたコンシューマーまたはプロバイダーのクラスをサポートしていないすべての実行に必要な場合でこれらのクラス インターフェイスを参照してください、 [OLE DB テンプレート ライブラリ](../../data/oledb/ole-db-templates.md)します。 これらのインターフェイスは、使いやすくために余分な実装を提供する、生の OLE DB インターフェイスをラップします。  
  
 など、行セット内のデータを更新するウィザードを使用して、コンシューマーの作成時に指定されていない場合は、する機能、ファクトの後に設定して指定できます、`DBPROP_IRowsetChange`と`DBPROP_UPDATABILITY`コマンド オブジェクトのプロパティ。 次に、行セットが作成されたときに、`IRowsetChange`インターフェイス。  
  
 **別のデータ アクセス テクノロジ (ADO、ODBC、または DAO) を使用して以前のコードを使用していますか。**  
 (コンポーネントの OLE DB と ADO のコンポーネントを使用して、OLE DB の ODBC コードを移行する) などのテクノロジの組み合わせについて、すべての状況を説明することは、Visual C ドキュメントの範囲外です。 ただし、さまざまなシナリオをカバーする多くの記事は、次の Microsoft Web サイトで使用できます。  
  
-   [Microsoft ヘルプおよびサポート](http://go.microsoft.com/fwlink/p/?linkid=148218)  
  
-   [Microsoft データ アクセス技術記事の概要](http://go.microsoft.com/fwlink/p/?linkid=148217)  
  
-   [Visual Studio ソリューション センター](http://go.microsoft.com/fwlink/p/?linkid=148215)  
  
-   [Microsoft.com を検索します。](http://search.microsoft.com/)  
  
 検索を実行するときに、シナリオに最適なキーワードの組み合わせを入力します。例: を ADO オブジェクトを使用して OLE DB プロバイダーを使用した場合は、ブール型の検索をお試しくださいと**ADO および OLE DB""** します。 DAO の古いコードを ODBC に移行する場合は、「すべての単語」を選択し、文字列を指定します。**移行 DAO**します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)
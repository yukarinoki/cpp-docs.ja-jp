---
title: OLE DB アーキテクチャの設計上の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 75d996416e92ded920f45d3352c6478dd8c67a86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109782"
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB アーキテクチャのデザインの問題
OLE DB アプリケーションを開始する前に、次の問題を考慮してください。  
  
 **OLE DB アプリケーションを作成するプログラミング実装を使用するか。**  
 マイクロソフトは、これを実現するいくつかのライブラリを提供しています。 OLE DB テンプレート ライブラリ、OLE DB 属性、および OLE DB SDK の生の OLE DB インターフェイスです。 さらに、あるウィザード、プログラムを記述する際に役立つ。 これらの実装については、「 [OLE DB テンプレート属性、およびその他実装](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md)です。  
  
 **独自のプロバイダーを記述する必要がありますか。**  
 ほとんどの開発者は、独自のプロバイダーを作成する必要はありません。 Microsoft では、いくつかのプロバイダーを提供します。 (たとえば、ATL OLE DB コンシューマー ウィザードを使用して、プロジェクトにコンシューマーを追加する場合)、データ接続を作成するときに、**データ リンク プロパティ** ダイアログ ボックスに、システムに登録されているすべての利用可能なプロバイダーが一覧表示されます。 これらのプロバイダーのいずれかが、独自のデータ ストアとデータ アクセス アプリケーションの適切な場合を行うには最も簡単な方法は、これらのいずれかを使用します。 ただし場合、これらのカテゴリのいずれかに一致しないデータ ストア、独自のプロバイダーを作成する必要があります。 プロバイダーを作成する方法の詳細については、次を参照してください。 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)です。  
  
 **コンシューマーに必要なレベルのサポート**  
 コンシューマーは、非常に基本的なです。他のユーザーは、非常に複雑になることができます。 OLE DB オブジェクトの機能は、プロパティによって指定されます。 ATL OLE DB コンシューマー ウィザードを使用してプロバイダーを作成するには、コンシューマーまたはデータベース プロバイダー ウィザードでは、作成するときに、標準的な機能のセットを提供する適切なオブジェクトのプロパティを設定します。 ただし、ウィザードで生成されたコンシューマーまたはプロバイダーのクラスを実行できるように必要なすべてをサポートしない場合場合、必要がありますでこれらのクラスのインターフェイスを参照する、 [OLE DB テンプレート ライブラリ](../../data/oledb/ole-db-templates.md)です。 これらのインターフェイスは、使いやすくために余分な実装を提供する、生の OLE DB インターフェイスをラップします。  
  
 たとえば、行セット内のデータを更新する、ウィザードを使用して、コンシューマーの作成時に指定されていない場合を指定できます機能、実際後の設定によって、 **DBPROP_IRowsetChange**と**DBPROP_UPDATABILITY**コマンド オブジェクトのプロパティです。 次に、行セットの作成時に、`IRowsetChange`インターフェイスです。  
  
 **(ADO、ODBC、または DAO) の別のデータ アクセス テクノロジを使用して古いコードはありますか。**  
 可能な (OLE DB コンポーネントと ADO コンポーネントを使用して、OLE db ODBC コードを移行する) などのテクノロジの組み合わせについて、すべての状況を説明することは、Visual C のドキュメントの範囲外です。 ただし、さまざまなシナリオをカバーする多数の記事は、次の Microsoft Web サイトで利用可能です。  
  
-   [Microsoft ヘルプおよびサポート](http://go.microsoft.com/fwlink/p/?linkid=148218)  
  
-   [Microsoft データ アクセス技術情報の概要](http://go.microsoft.com/fwlink/p/?linkid=148217)  
  
-   [Visual Studio ソリューション センター](http://go.microsoft.com/fwlink/p/?linkid=148215)  
  
-   [Microsoft.com を検索します。](http://search.microsoft.com/)  
  
 検索を実行するときに、シナリオに最適なキーワードの組み合わせを入力してください。例: OLE DB プロバイダーで ADO オブジェクトを使用していた場合は、ブール型の検索を再試行してくださいで**ADO および OLE DB""** です。 ODBC に古い DAO コードを移行する場合は、「すべての単語」を選択し、文字列を指定します。**移行 DAO**です。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)
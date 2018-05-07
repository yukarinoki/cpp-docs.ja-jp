---
title: OLE DB プロバイダー テンプレート (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a331e72433ca25d280d35edfd33a56402675aea9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-provider-templates-c"></a>OLE DB プロバイダー テンプレート (C++)
OLE DB は、Microsoft Universal Data Access 戦略の重要な部分です。 OLE DB デザインでは、任意のデータ ソースからのパフォーマンスの高いデータ アクセスを許可します。 表形式データがデータベースからに送信するかどうかに関係なく表示可能な OLE DB を使用します。 柔軟では、膨大な電力量を示します。  
  
 説明したよう[OLE DB コンシューマーとプロバイダー](../../data/oledb/ole-db-consumers-and-providers.md)、OLE DB コンシューマーとプロバイダーの概念を使用します。 コンシューマーは、データに対する要求を行いますプロバイダーは、コンシューマーに表形式でデータを返します。 プログラミングの観点から、最も重要なこのモデルは、プロバイダーがコンシューマーが行う任意の呼び出しを実装する必要があります。  
  
## <a name="what-is-a-provider"></a>プロバイダーとは何ですか。  
 OLE DB プロバイダーは、(データ ストアと呼ばれます)、持続性のあるソースからコンシューマーに表形式でデータを転送するコンシューマーのオブジェクトからのインターフェイスの呼び出しを処理する COM オブジェクトのセットです。  
  
 プロバイダーは、単純または複雑なを指定できます。 プロバイダーは、複数のインターフェイスを実装することによって最小限の機能または本格的な運用環境品質プロバイダーをサポートできます。 プロバイダーでは、テーブルを返す、そのテーブルの形式を指定するクライアントを許可する、およびそのデータに対して操作を実行できます。  
  
 各プロバイダーでは、任意の OLE DB コンシューマー (C++ など、基本的な) 言語に関係なく、任意のプロバイダーからデータにアクセスできること、クライアントからの要求を処理する COM オブジェクトの標準セットを実装します。  
  
 各 COM オブジェクトには、必要なこれらの一部は、これらの一部は省略可能ないくつかのインターフェイスが含まれています。 必須のインターフェイスを実装するは、プロバイダーは、任意のクライアントが使用できる機能 (と呼ばれる対応) の最小レベルを保証します。 プロバイダーは、追加の機能を提供する省略可能なインターフェイスを実装できます。 [OLE DB プロバイダー テンプレート アーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)詳細でこれらのインターフェイスについて説明します。 クライアントは常に呼び出す必要があります`QueryInterface`をプロバイダーが特定のインターフェイスをサポートしているかを判断します。  
  
## <a name="ole-db-specification-level-support"></a>OLE DB 仕様のレベルのサポート  
 OLE DB プロバイダー テンプレートは、OLE DB バージョン 2.7 仕様をサポートします。 OLE DB プロバイダー テンプレートを使用して、レベル 0 の準拠のプロバイダーを実装できます。 プロバイダーのサンプルは、たとえば、DOS DIR コマンドで、ファイル システムのクエリを実行する non-MS-DOS コマンド サーバーを実装するのに、テンプレートを使用します。 プロバイダーのサンプルでは、表形式のデータを返すための標準の OLE DB メカニズムは、行セット内のディレクトリ情報を返します。  
  
 OLE DB テンプレートでサポートされているプロバイダーの最も単純な種類は、コマンドを持たない読み取り専用プロバイダーです。 コマンドでプロバイダーは、ブックマークおよび読み取り/書き込み機能もサポートされます。 読み取り/書き込みプロバイダーを実装するには、追加のコードを記述します。 動的な行セットとトランザクションが現在のバージョンでサポートされていませんが、する場合は追加することができます。  
  
## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>行う必要がある場合、OLE DB プロバイダーを作成するか。  
 常に独自のプロバイダーを作成する必要はありません。Microsoft 提供のいくつかのパッケージ化された、標準的なプロバイダー、**データ リンク プロパティ**Visual C でのダイアログ ボックス。 OLE DB プロバイダーを作成する主な理由は、Universal Data Access 戦略を活用するためにです。 いくつかの実行の利点はそのためは。  
  
-   C++、Basic、および Visual Basic Scripting Edition などの任意の言語を使用してデータにアクセスします。 これにより、どのような言語を使用に関係なく同じ方法で、同じデータにアクセスする、組織内の異なるプログラマできます。  
  
-   SQL Server、Excel、およびアクセスなどソース、データは、その他のデータを公開します。 これは、異なる形式間でデータを転送する場合に役立ちます。  
  
-   (異種) 間のデータ ソースの操作に参加します。 これは、データ ウェアハウスの非常に効果的な方法です。 OLE DB プロバイダーを使用するは、ネイティブ形式でデータを保持し、単純な操作でアクセスできます。  
  
-   クエリの処理などのデータには、その他の機能を追加します。  
  
-   操作方法を制御することでデータへのアクセスのパフォーマンスが向上します。  
  
-   保全性の向上。 独自のデータ形式があればその 1 つだけのプログラマがアクセスできる、危険にさらされています。 OLE DB プロバイダーを使用して、すべてのプログラマをその独自の形式を開くことができます。  
  
## <a name="read-only-and-updatable-providers"></a>読み取り専用であり、更新可能なプロバイダー  
 プロバイダーは、複雑さや機能に大きく異なります。 読み取り専用プロバイダー、および更新可能なプロバイダーにプロバイダーを分類すると便利です。  
  
-   Visual C 6.0 には、読み取り専用プロバイダーのみがサポートされています。 [OLE DB プロバイダーを作成する](../../data/oledb/creating-an-ole-db-provider.md)読み取り専用プロバイダーを作成する方法について説明します。  
  
-   Visual C は、更新可能なプロバイダーは、更新をサポートしています (書き込む) データ ストアです。 更新可能なプロバイダーについては、次を参照してください。[更新可能なプロバイダーを作成する](../../data/oledb/creating-an-updatable-provider.md); [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプルは、更新可能なプロバイダーの例を示します。  
  
 詳細については次を参照してください:  
  
-   [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)  
  
-   [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)  
  
-   [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)  
  
## <a name="see-also"></a>関連項目  
 [データ アクセス](../data-access-in-cpp.md)   
 [OLE DB SDK のドキュメント](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [OLE DB プログラマーズ リファレンス](https://msdn.microsoft.com/en-us/library/ms713643.aspx)
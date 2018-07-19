---
title: プロバイダーのテスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c35b1391e5b8cbfb073255b3680b0376d19ae040
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104790"
---
# <a name="testing-your-provider"></a>プロバイダーのテスト
プロバイダーを解放する前に、示されている順序で次のテストを行う必要があります。 これらのテストでは、ほとんどの潜在的なユーザー用に正しくプロバイダー関数ことを確認します。  
  
1.  使用してプロバイダーをテストする[コンシューマー](../../data/oledb/creating-an-ole-db-consumer.md)の OLE DB コンシューマー テンプレートで作成されたアプリケーション。 テスト コンシューマーは、プロバイダー (すべてのコードを追加または変更した) のすべての機能領域をカバーする必要があります。  
  
2.  ADO で記述されたコンシューマー アプリケーションを使用してプロバイダーをテストします。 ほとんどの開発者 (特に Microsoft Visual Basic および Microsoft c# 開発者) は、コンシューマー アプリケーションの ADO または ADO.NET を使用します。 テスト コンシューマーは、プロバイダーのすべての機能領域をカバーする必要があります。 ADO コンシューマー アプリケーションの例は、次を参照してください。 [ADO コードの例では、Microsoft Visual Basic](https://msdn.microsoft.com/en-us/library/ms807514.aspx)です。  
  
3.  プロバイダーが OLE DB プロバイダーのレベル 0 の標準を満たしていることを確認するには、OLE DB 準拠合致テスト (ADO 準拠合致テストを含む) を実行します。 (レベル 0 の詳細については、「OLE DB レベル 0 準拠合致テスト」で検索[OLE DB プログラマ ガイド](http://go.microsoft.com/fwlink/p/?linkid=121548)です。 これらのテストと関連ドキュメント Data Access SDK の Visual C に含まれます。 これらのテストは、プロバイダーが他の統合されたときに実行されるようにも役立ちます[サービス プロバイダー](../../data/oledb/ole-db-resource-pooling-and-services.md)し、変更、またはプロパティを追加する場合は特に便利です。 準拠合致テストに関する詳細については、Visual Studio Cd のいずれかの上にある、Data Access SDK の Readme ファイルを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
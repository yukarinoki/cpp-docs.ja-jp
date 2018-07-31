---
title: プロバイダーのテスト |Microsoft Docs
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
ms.openlocfilehash: 906156a24cfb58697ff4dd95e922f5ee326fd07d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339729"
---
# <a name="testing-your-provider"></a>プロバイダーのテスト
プロバイダーをリリースする前に示されている順序で次のテストを行う必要があります。 これらのテストでは、ほとんどの潜在的なユーザー用に正しくプロバイダー関数こと確認します。  
  
1.  使用してプロバイダーをテストする[コンシューマー](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB コンシューマー テンプレートで記述されたアプリケーション。 テスト コンシューマーは、(追加または変更するすべてのコード) は、プロバイダーのすべての機能領域をカバーする必要があります。  
  
2.  ADO で作成したコンシューマー アプリケーションを使用してプロバイダーをテストします。 ほとんどの開発者 (特に Microsoft Visual Basic や Microsoft c# 開発者) は、コンシューマー アプリケーションの ADO または ADO.NET を使用します。 テスト コンシューマーは、プロバイダーのすべての機能領域をカバーする必要があります。 ADO のコンシューマー アプリケーションの例は、次を参照してください。 [ADO のコード例では、Microsoft Visual Basic](https://msdn.microsoft.com/library/ms807514.aspx)します。  
  
3.  OLE DB 準拠合致テスト (ADO 準拠テストを含む) を実行すると、OLE DB プロバイダーのプロバイダーが、レベル 0 の標準を満たしていることが確認されます。 (レベル 0 の詳細については、「OLE DB レベル 0 準拠合致テスト」で検索[OLE DB プログラマ ガイド](http://go.microsoft.com/fwlink/p/?linkid=121548)します。 これらのテストと関連付けられているドキュメントは、Data Access SDK の Visual C に含まれています。 これらのテストは、その他の統合されたときに、プロバイダーが実行されるようにも役立ちます[サービス プロバイダー](../../data/oledb/ole-db-resource-pooling-and-services.md)し、変更、またはプロパティを追加する場合は特に便利です。 準拠合致テストの詳細については、Visual Studio Cd のいずれかの上にある Data Access SDK の Readme ファイルを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
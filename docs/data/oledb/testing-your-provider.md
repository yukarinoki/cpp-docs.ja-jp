---
title: プロバイダーのテスト
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: 42186d789c1b85c359b9e3e30883929a6c71ab33
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265114"
---
# <a name="testing-your-provider"></a>プロバイダーのテスト

プロバイダーをリリースする前に示されている順序で、次のテストを行う必要があります。 これらのテストでは、ほとんどの潜在的なユーザー用に正しくプロバイダー関数を表示します。

1. 使用してプロバイダーをテストする[コンシューマー](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB コンシューマー テンプレートで記述されたアプリケーション。 テストのコンシューマーは必要があります (変更または追加したすべてのコード) は、プロバイダーのすべての機能領域をについて説明します。

1. ADO で作成したコンシューマー アプリケーションを使用してプロバイダーをテストします。 ほとんどの開発者 (特に Microsoft Visual Basic や Microsoft c# 開発者) は、コンシューマー アプリケーションの ADO または ADO.NET を使用します。 テスト コンシューマーは、プロバイダーのすべての機能領域をカバーする必要があります。 ADO のコンシューマー アプリケーションの例は、次を参照してください。 [ADO のコード例では、Microsoft Visual Basic](https://msdn.microsoft.com/library/ms807514.aspx)します。

1. OLE DB プロバイダーのプロバイダーが、レベル 0 の標準を満たしていることを表示するには、OLE DB 準拠合致テスト (ADO 準拠テストを含む) を実行します。 (レベル 0 の詳細については、検索**OLE DB レベル 0 の準拠テスト**で[OLE DB プログラマ ガイド](/previous-versions/windows/desktop/ms713643)します。 これらのテストと関連付けられているドキュメントは、Data Access SDK の Visual C に含まれています。 これらのテストは、プロバイダーが他の統合されたときに実行する表示にも役立ちます[サービス プロバイダー](../../data/oledb/ole-db-resource-pooling-and-services.md)し、変更、またはプロパティを追加する場合は特に便利です。 準拠合致テストの詳細については、Visual Studio Cd のいずれかの上にある Data Access SDK の Readme ファイルを参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
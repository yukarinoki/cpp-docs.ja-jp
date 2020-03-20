---
title: プロバイダーのテスト
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: 722757b93d3423b02340c382b16e08a31626bc01
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544538"
---
# <a name="testing-your-provider"></a>プロバイダーのテスト

プロバイダーをリリースする前に、次のテストを示された順序で実行する必要があります。 これらのテストは、プロバイダーがほとんどのユーザーに対して適切に機能していることを示しています。

1. OLE DB コンシューマーテンプレートで記述された[コンシューマー](../../data/oledb/creating-an-ole-db-consumer.md)アプリケーションを使用して、プロバイダーをテストします。 テストコンシューマーは、プロバイダーのすべての機能領域 (追加または変更したすべてのコード) をカバーする必要があります。

1. ADO で記述されたコンシューマーアプリケーションを使用して、プロバイダーをテストします。 ほとんどの開発者 (特に Microsoft C# Visual Basic および microsoft 開発者) は、コンシューマーアプリケーションに ADO または ADO.NET を使用します。 テストコンシューマーは、プロバイダーのすべての機能領域をカバーする必要があります。 ADO コンシューマーアプリケーションの例については、「 [Microsoft Visual Basic の Ado コード例](/previous-versions/ms807514(v=msdn.10))」を参照してください。

1. OLE DB 準拠テスト (ADO 準拠テストを含む) を実行して、プロバイダーが OLE DB プロバイダーのレベル0の標準を満たしていることを示します。 (レベル0の説明については、 [OLE DB プログラマーガイド](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)で**OLE DB レベル0の準拠テスト**を検索してください。 これらのテストと関連ドキュメントは、データC++アクセス SDK のビジュアルに含まれています。 また、これらのテストは、他の[サービスプロバイダー](../../data/oledb/ole-db-resource-pooling-and-services.md)によって集計された場合にプロバイダーが良好に動作することを示すのにも役立ちます。また、プロパティを変更または追加する場合に特に便利です。 準拠テストの詳細については、Visual Studio のいずれかの Cd にある Data Access SDK の Readme ファイルを参照してください。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
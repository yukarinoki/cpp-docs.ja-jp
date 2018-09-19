---
title: OLE DB プロバイダーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 441fdfcf98e08b30e1049cac986ebc9e0f7df682
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030405"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB プロバイダーの作成

OLE DB プロバイダーを作成する推奨される方法は、ウィザードを使用して、ATL COM プロジェクトとプロバイダーを作成し、OLE DB テンプレートを使用してファイルを変更します。 プロバイダーをカスタマイズすると不要なプロパティをコメントにし、省略可能なインターフェイスを追加できます。  
  
基本的な手順を以下に示します。  
  
1. ATL プロジェクト ウィザードを使用して、基本的なプロジェクト ファイルと ATL OLE DB プロバイダー ウィザード、プロバイダーの作成を作成する (選択**ATL OLE DB Provider**で Visual C フォルダーから**クラスの追加**)。  
  
1. コードを変更、 `Execute` CMyProviderRS.h メソッド。 例については、次を参照してください。[読み取り文字列に OLE DB プロバイダー](../../data/oledb/reading-strings-into-the-ole-db-provider.md)します。  
  
1. MyProviderDS.h、MyProviderSess.h、および MyProviderRS.h プロパティ マップを編集します。 ウィザードでは、プロバイダーを実装できるすべてのプロパティが含まれているプロパティのマップを作成します。 プロパティ マップを移動し、削除またはコメント アウト プロパティをプロバイダーがサポートする必要はありません。  
  
1. MyProviderRS.h を記載すると、PROVIDER_COLUMN_MAP を更新します。 例については、次を参照してください。[を格納する文字列で、OLE DB Provider](../../data/oledb/storing-strings-in-the-ole-db-provider.md)します。  
  
1. プロバイダーをテストする準備ができたらは、プロバイダーの列挙体で、プロバイダーを検出することによってテストできます。 列挙体でプロバイダーを検索するテスト コードの例については、次を参照してください。、 [CATDB](https://github.com/Microsoft/VCSamples)と[DBVIEWER](https://github.com/Microsoft/VCSamples)サンプルまたは例では、[を実装する単純なコンシューマーの](../../data/oledb/implementing-a-simple-consumer.md)します。  
  
1. 必要なインターフェイスを追加します。 例については、次を参照してください。[単純な読み取り専用プロバイダーの強化](../../data/oledb/enhancing-the-simple-read-only-provider.md)します。  
  
    > [!NOTE]
    >  既定では、ウィザードは、OLE DB レベル 0 の準拠しているコードを生成します。 アプリケーションが、レベル 0 の準拠を引き続きようにするから取り外さないでくださいウィザードで生成されたインターフェイスのいずれかのコード。  
  
## <a name="see-also"></a>関連項目  

[CATDB](https://github.com/Microsoft/VCSamples)<br/>
[DBVIEWER](https://github.com/Microsoft/VCSamples)
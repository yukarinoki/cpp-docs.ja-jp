---
title: OLE DB プロバイダーの作成 |Microsoft ドキュメント
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
ms.openlocfilehash: f649b5b4c79c4148d0aed026b044485ca2b1eaa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097108"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB プロバイダーの作成
ウィザードを使用して ATL COM プロジェクトとプロバイダーを作成し、OLE DB テンプレートを使用してファイルを変更するは、OLE DB プロバイダーを作成することをお勧めします。 プロバイダーをカスタマイズするには、不要なプロパティをコメントおよび省略可能なインターフェイスを追加できます。  
  
 基本的な手順を以下に示します。  
  
1.  ATL プロジェクト ウィザードを使用して、基本的なプロジェクト ファイルと ATL OLE DB プロバイダー ウィザード、プロバイダーを作成するを作成する (選択**ATL OLE DB プロバイダー** Visual C フォルダーから**クラスの追加**)。  
  
2.  コードを変更、 `Execute` CMyProviderRS.h 内のメソッドです。 例については、次を参照してください。[読み取り文字列に OLE DB プロバイダー](../../data/oledb/reading-strings-into-the-ole-db-provider.md)です。  
  
3.  MyProviderDS.h、MyProviderSess.h、および MyProviderRS.h プロパティ マップを編集します。 ウィザードでは、プロバイダーを実装するすべてのプロパティを含むプロパティ マップを作成します。 プロパティ マップを移動し、削除またはコメント プロパティが、プロバイダーがサポートする必要はありません。  
  
4.  MyProviderRS.h であることができます、PROVIDER_COLUMN_MAP を更新します。 例については、次を参照してください。[を格納する文字列で、OLE DB プロバイダー](../../data/oledb/storing-strings-in-the-ole-db-provider.md)です。  
  
5.  プロバイダーをテストする準備ができたら、する場合は、プロバイダーの列挙体でプロバイダーを検索しようとしてテストすることができます。 列挙のプロバイダーを検索するテスト コードの例については、次を参照してください。、 [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046)と[DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)サンプルまたは例では、[を実装する単純なコンシューマーの](../../data/oledb/implementing-a-simple-consumer.md)します。  
  
6.  必要なインターフェイスを追加します。 例については、次を参照してください。[単純な読み取り専用プロバイダーの向上](../../data/oledb/enhancing-the-simple-read-only-provider.md)です。  
  
    > [!NOTE]
    >  既定では、ウィザードは、OLE DB レベル 0 に準拠したコードを生成します。 レベル 0 の準拠は、アプリケーションが確実に、削除しないでウィザードで生成されたインターフェイスのいずれかのコードから。  
  
## <a name="see-also"></a>関連項目  
 [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)
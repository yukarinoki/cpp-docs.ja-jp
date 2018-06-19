---
title: コマンドとテーブル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, table support
- CCommand class, OLE DB consumer templates
- commands [C++], OLE DB Consumer Templates
- CTable class
- CAccessorRowset class, command and table classes
- rowsets, accessing
- tables [C++], OLE DB Consumer Templates
- OLE DB consumer templates, command support
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 23d2739807a065b93b10a209a9ea68070b36970b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098681"
---
# <a name="commands-and-tables"></a>コマンドとテーブル
コマンドとテーブル行セットにアクセスすることを許可します。つまり、行セットを開き、コマンドを実行し、列をバインドします。 [CCommand](../../data/oledb/ccommand-class.md)と[CTable](../../data/oledb/ctable-class.md)クラスがそれぞれのコマンドとテーブルのオブジェクトをインスタンス化します。 これらのクラスから派生して[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)次の図に示すようにします。  
  
 ![CCommand および CTable](../../data/oledb/media/vccommandstables.gif "vccommandstables")  
コマンドとテーブル クラス  
  
 前の表に`TAccessor`、アクセサーの種類に指定できる[アクセサーの種類](../../data/oledb/accessors-and-rowsets.md)です。 *TRowset*任意の行セット型に指定できる[行セットの種類](../../data/oledb/accessors-and-rowsets.md)です。 *TMultiple* (1 つまたは複数の結果セット) の結果の型を指定します。  
  
 [ATL OLE DB コンシューマー ウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)コマンドまたはテーブル オブジェクトをするかどうかを指定することができます。  
  
-   コマンドせず、データ ソースを使用できます、`CTable`クラスです。 一般的に使用するパラメータを指定しないと、複数の結果を必要とする単純な行セットの。 この単純なクラスは、指定したテーブル名を使用してデータ ソースのテーブルを開きます。  
  
-   をコマンドをサポートするデータ ソースを使用できます、`CCommand`クラスの代わりにします。 コマンドを実行するには、呼び出す[開く](../../data/oledb/ccommand-open.md)このクラスにします。 代わりに、呼び出すことができます`Prepare`2 回以上実行するコマンドを準備します。  
  
     **CCommand** 3 つのテンプレート引数を持つ: アクセサーの型、行セットの種類、および結果型は (`CNoMultipleResults`、既定では、または`CMultipleResults`)。 指定した場合`CMultipleResults`、`CCommand`クラスでサポート、 **IMultipleResults**インターフェイスし、複数の行セットを処理します。 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)サンプルを複数の結果を処理する方法を示します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)
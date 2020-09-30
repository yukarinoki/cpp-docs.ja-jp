---
title: コマンドとテーブル
ms.date: 11/19/2018
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
ms.openlocfilehash: f65bd0f90832039d453d84ab9765781c30750318
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507373"
---
# <a name="commands-and-tables"></a>コマンドとテーブル

コマンドとテーブルを使用すると、行セットにアクセスできます。つまり、行セットを開き、コマンドを実行して、列をバインドします。 [CCommand](../../data/oledb/ccommand-class.md)クラスと[CTable](../../data/oledb/ctable-class.md)クラスは、それぞれコマンドオブジェクトとテーブルオブジェクトをインスタンス化します。 これらのクラスは、次の図に示すように、 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) から派生します。

![CCommand および CTable](../../data/oledb/media/vccommandstables.gif "CCommand および CTable")<br/>
コマンドおよびテーブルクラス

前の表では、は `TAccessor` [アクセサー](../../data/oledb/accessors-and-rowsets.md)型に示されている任意のアクセサー型にすることができます。 `TRowset`[行セット](../../data/oledb/accessors-and-rowsets.md)の型にリストされている任意の行セットの型を指定できます。 `TMultiple` 結果の型 (1 つまたは複数の結果セット) を指定します。

[ATL OLE DB コンシューマーウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)では、コマンドまたはテーブルオブジェクトを使用するかどうかを指定できます。

- コマンドのないデータソースの場合は、クラスを使用でき `CTable` ます。 通常は、パラメーターを指定せず、複数の結果を必要としない単純な行セットに使用します。 この単純なクラスは、指定したテーブル名を使用して、データソースのテーブルを開きます。

- コマンドをサポートするデータソースの場合は、代わりにクラスを使用でき `CCommand` ます。 コマンドを実行するには、このクラスで [Open](./ccommand-class.md#open) を呼び出します。 別の方法として、を呼び出して、 `Prepare` 複数回実行するコマンドを準備することもできます。

   `CCommand`には、アクセサー型、行セット型、および結果型 (既定では、 `CNoMultipleResults` または) の3つのテンプレート引数があります。 `CMultipleResults` を指定した場合、 `CMultipleResults` `CCommand` クラスはインターフェイスをサポート `IMultipleResults` し、複数の行セットを処理します。 [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)サンプルでは、複数の結果を処理する方法を示します。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)

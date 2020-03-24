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
ms.openlocfilehash: 0d5f6bd8d5f813497cba399e5c071f43dc1a7c4d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211524"
---
# <a name="commands-and-tables"></a>コマンドとテーブル

コマンドとテーブルを使用すると、行セットにアクセスできます。つまり、行セットを開き、コマンドを実行して、列をバインドします。 [CCommand](../../data/oledb/ccommand-class.md)クラスと[CTable](../../data/oledb/ctable-class.md)クラスは、それぞれコマンドオブジェクトとテーブルオブジェクトをインスタンス化します。 これらのクラスは、次の図に示すように、 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)から派生します。

![CCommand と CTable](../../data/oledb/media/vccommandstables.gif "CCommand および CTable")<br/>
コマンドおよびテーブルクラス

前の表では、`TAccessor`[アクセサー](../../data/oledb/accessors-and-rowsets.md)型に示されている任意のアクセサー型を使用できます。 `TRowset` は、[行セットの型](../../data/oledb/accessors-and-rowsets.md)に一覧表示されている任意の行セットの型になります。 `TMultiple` 結果の型 (1 つまたは複数の結果セット) を指定します。

[ATL OLE DB コンシューマーウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)では、コマンドまたはテーブルオブジェクトを使用するかどうかを指定できます。

- コマンドのないデータソースの場合は、`CTable` クラスを使用できます。 通常は、パラメーターを指定せず、複数の結果を必要としない単純な行セットに使用します。 この単純なクラスは、指定したテーブル名を使用して、データソースのテーブルを開きます。

- コマンドをサポートするデータソースの場合は、代わりに `CCommand` クラスを使用できます。 コマンドを実行するには、このクラスで[Open](../../data/oledb/ccommand-open.md)を呼び出します。 別の方法として、`Prepare` を呼び出して、複数回実行するコマンドを準備することもできます。

   `CCommand` には、アクセサー型、行セットの型、および結果の型 (`CNoMultipleResults`、既定では `CMultipleResults`) という3つのテンプレート引数があります。 `CMultipleResults`を指定した場合、`CCommand` クラスは `IMultipleResults` インターフェイスをサポートし、複数の行セットを処理します。 [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)サンプルでは、複数の結果を処理する方法を示します。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)

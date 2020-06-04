---
title: アクセサーと行セット
ms.date: 11/19/2018
helpviewer_keywords:
- accessors [C++]
- OLE DB consumer templates, rowset support
- OLE DB consumer templates, accessors
- rowsets [C++], accessing
- bulk rowsets
- CAccessorRowset class, accessor types
- single rowsets
- CArrayRowset class, accessors
- CBulkRowset class, accessors
- array rowsets
- CAccessorBase class
- CRowset class, accessors and rowsets
- accessors [C++], rowsets
- rowsets [C++], supported types
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
ms.openlocfilehash: 45180b3ac2647c9f4f5d25a1322794552bd79004
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212382"
---
# <a name="accessors-and-rowsets"></a>アクセサーと行セット

OLE DB テンプレートでは、データを設定および取得するために、 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)クラスを使用してアクセサーと行セットを使用します。 このクラスは、異なる型の複数のアクセサーを処理できます。

## <a name="accessor-types"></a>アクセサー型

すべてのアクセサーは[CAccessorBase](../../data/oledb/caccessorbase-class.md)から派生します。 `CAccessorBase` には、パラメーターと列のバインドの両方が用意されています。

次の図は、アクセサーの種類を示しています。

![アクセサー型](../../data/oledb/media/vcaccessortypes.gif "アクセサー タイプ")<br/>
アクセサークラス

- [CAccessor](../../data/oledb/caccessor-class.md)このアクセサーは、デザイン時にデータベースソースの構造がわかっている場合に使用します。 `CAccessor` は、バッファーを含むデータベースレコードをデータソースに静的にバインドします。

- [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)このアクセサーは、デザイン時にデータベースの構造がわからない場合に使用します。 `CDynamicAccessor` は `IColumnsInfo::GetColumnInfo` を呼び出して、データベースの列情報を取得します。 アクセサーとバッファーを作成し、管理します。

- [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)このアクセサーを使用して、不明なコマンドの種類を処理します。 コマンドを準備するときに、プロバイダーが `ICommandWithParameters`をサポートしている場合は、`ICommandWithParameters` インターフェイスからパラメーター情報を取得 `CDynamicParameterAccessor` ことができます。

- [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)、 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)、および[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)は、データベーススキーマについての知識がない場合に、これらのクラスを使用します。 `CDynamicStringAccessorA` は、データを ANSI 文字列として取得します。`CDynamicStringAccessorW` は、データを Unicode 文字列として取得します。

- [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)このクラスを使用すると、プロバイダーが型を変換できる場合に、任意のデータ型を使用できます。 結果列とコマンドパラメーターの両方を処理します。

次の表は、OLE DB テンプレートアクセサー型のサポートをまとめたものです。

|アクセサー型|動的|パラメーターを処理します|バッファー|複数のアクセサー|
|-------------------|-------------|--------------------|------------|------------------------|
|`CAccessor`|いいえ|はい|User|はい|
|`CDynamicAccessor`|はい|いいえ|OLE DB テンプレート|いいえ|
|`CDynamicParameterAccessor`|はい|はい|OLE DB テンプレート|いいえ|
|`CDynamicStringAccessor[A,W]`|はい|いいえ|OLE DB テンプレート|いいえ|
|`CManualAccessor`|はい|はい|User|はい|

## <a name="rowset-types"></a>行セットの種類

OLE DB テンプレートでは、3種類の行セットをサポートしています (前の図を参照)。1つの行セット ( [CRowset](../../data/oledb/crowset-class.md)によって実装されます)、一括行セット ( [cbulkrowset](../../data/oledb/cbulkrowset-class.md)によって実装)、および配列行セット ( [CArrayRowset](../../data/oledb/carrayrowset-class.md)によって実装されます)。 `MoveNext` が呼び出されると、1つの行セットが1つの行ハンドルをフェッチします。 一括行セットは、複数の行ハンドルをフェッチできます。 配列行セットは、配列構文を使用してアクセスできる行セットです。

次の図は、行セットの種類を示しています。

![RowsetType グラフィック](../../data/oledb/media/vcrowsettypes.gif "RowsetType グラフィック")<br/>
行セットクラス

[スキーマ行セット](../../data/oledb/obtaining-metadata-with-schema-rowsets.md)は、データストア内のデータにはアクセスせず、代わりに、メタデータと呼ばれるデータストアに関する情報にアクセスします。 スキーマ行セットは、通常、データベース構造がコンパイル時に認識されず、実行時に取得する必要がある状況で使用されます。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)

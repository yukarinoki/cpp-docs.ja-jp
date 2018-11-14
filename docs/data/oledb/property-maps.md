---
title: プロパティ マップ
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 2d01c2f0d7fb581f9f7e93c1ec100e465a6d92f3
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556478"
---
# <a name="property-maps"></a>プロパティ マップ

セッション、行セット、および省略可能なコマンド オブジェクトを使用は、各プロバイダーは、1 つまたは複数のプロパティをサポートします。 によって作成されたヘッダー ファイルに格納されているプロパティのマップでこれらのプロパティが定義されている、 **OLE DB プロバイダー ウィザード**します。 各ヘッダー ファイルには、オブジェクトまたはそのファイルで定義されたオブジェクトに対して定義されている OLE DB プロパティのグループのプロパティのマップが含まれています。 データ ソース オブジェクトを含むヘッダー ファイルには、プロパティのマップも含まれています、 [DataSource プロパティ](https://msdn.microsoft.com/library/ms724188)します。 `Session.h` プロパティのマップが含まれています、[セッション プロパティ](https://docs.microsoft.com/previous-versions/windows/desktop/ms714221(v=vs.85))します。 行セットとコマンド オブジェクトはという 1 つのヘッダー ファイルの*projectname*RS.h します。 これらのプロパティのメンバーである、[行セット プロパティ](https://docs.microsoft.com/previous-versions/windows/desktop/ms711252(v=vs.85))グループ。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>

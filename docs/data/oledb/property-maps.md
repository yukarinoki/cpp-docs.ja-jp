---
title: プロパティ マップ
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 79a65290c24ab016d9f81b54b9b7720d5c4ff352
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544556"
---
# <a name="property-maps"></a>プロパティ マップ

セッション、行セット、および省略可能なコマンドオブジェクトを使用すると、各プロバイダーは1つ以上のプロパティをサポートします。 これらのプロパティは、 **OLE DB プロバイダーウィザード**によって作成されたヘッダーファイルに格納されているプロパティマップで定義されます。 各ヘッダーファイルには、そのファイルで定義されているオブジェクトに対して定義された OLE DB プロパティグループのプロパティのマップが含まれています。 データソースオブジェクトを含むヘッダーファイルには、 [DataSource プロパティ](/previous-versions/windows/desktop/ms724188(v=vs.85))のプロパティマップも含まれています。 `Session.h` には、[セッションプロパティ](/previous-versions/windows/desktop/ms714221(v=vs.85))のプロパティマップが含まれています。 行セットオブジェクトとコマンドオブジェクトは、 *projectname*RS. h という1つのヘッダーファイルにあります。 これらのプロパティは、[行セットプロパティ](/previous-versions/windows/desktop/ms711252(v=vs.85))グループのメンバーです。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>

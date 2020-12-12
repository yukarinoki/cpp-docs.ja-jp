---
description: 詳細については、「プロパティマップ」を参照してください。
title: プロパティ マップ
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 30b277451d871de45902661f7b7e56cbc7409c97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316909"
---
# <a name="property-maps"></a>プロパティ マップ

セッション、行セット、および省略可能なコマンドオブジェクトを使用すると、各プロバイダーは1つ以上のプロパティをサポートします。 これらのプロパティは、 **OLE DB プロバイダーウィザード** によって作成されたヘッダーファイルに格納されているプロパティマップで定義されます。 各ヘッダーファイルには、そのファイルで定義されているオブジェクトに対して定義された OLE DB プロパティグループのプロパティのマップが含まれています。 データソースオブジェクトを含むヘッダーファイルには、 [DataSource プロパティ](/previous-versions/windows/desktop/ms724188(v=vs.85))のプロパティマップも含まれています。 `Session.h`[セッションプロパティ](/previous-versions/windows/desktop/ms714221(v=vs.85))のプロパティマップを格納します。 行セットオブジェクトとコマンドオブジェクトは、 *projectname* RS. h という1つのヘッダーファイルにあります。 これらのプロパティは、 [行セットプロパティ](/previous-versions/windows/desktop/ms711252(v=vs.85)) グループのメンバーです。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>

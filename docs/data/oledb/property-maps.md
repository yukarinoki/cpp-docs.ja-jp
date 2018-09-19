---
title: プロパティ マップ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3fb9c5a5c18925bfcd448bb2349379262b27361
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080988"
---
# <a name="property-maps"></a>プロパティ マップ

に加えて、セッション、行セットと省略可能なコマンド オブジェクトは、各プロバイダーは、1 つまたは複数のプロパティをサポートします。 これらのプロパティは OLE DB プロバイダー ウィザードで作成されたヘッダー ファイルに含まれているプロパティのマップで定義されます。 各ヘッダー ファイルには、オブジェクトまたはそのファイルで定義されたオブジェクトに対して定義されている OLE DB プロパティのグループのプロパティのマップが含まれています。 データ ソース オブジェクトを含むヘッダー ファイルには、プロパティのマップも含まれています、 [DataSource プロパティ](https://msdn.microsoft.com/library/ms724188\(v=vs.140\).aspx)します。 Session.h にはプロパティのマップが含まれています、[セッション プロパティ](/previous-versions/windows/desktop/ms714221\(v=vs.85\))します。 行セットとコマンドのオブジェクトと呼ばれる、1 つのヘッダー ファイル内に存在*projectname*RS.h します。 これらのプロパティのメンバーである、[行セット プロパティ](/previous-versions/windows/desktop/ms711252\(v=vs.85\))グループ。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
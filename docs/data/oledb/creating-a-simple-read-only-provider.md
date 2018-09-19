---
title: 単純な読み取り専用プロバイダーの作成 |Microsoft Docs
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
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9f951fba45b23b7e4dde92fc11f2faabb53bd43d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101567"
---
# <a name="creating-a-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの作成

ATL プロジェクト ウィザードと ATL OLE DB プロバイダー ウィザードを使用して OLE DB プロバイダーを作成するときは、サポートするその他の機能を追加できます。 どのような条件下でコンシューマーに送信するデータの種類を調べることで、プロバイダーのデザインを開始します。 これは、機能は、コマンド、トランザクション、およびその他の省略可能なオブジェクトをサポートするために必要かどうかを判断するは特に重要です。 実装とテスト、前もって優れたデザインが短縮されます。  
  
2 つの部分では、例では、表示されます。  
  
- 最初の部分に示す方法[単純な読み取り専用プロバイダーの作成](../../data/oledb/implementing-the-simple-read-only-provider.md)文字列のペアを読み取る。  
  
- 2 番目の部分に示す方法[単純な読み取り専用プロバイダーの強化](../../data/oledb/enhancing-the-simple-read-only-provider.md)を追加して、`IRowsetLocate`インターフェイス。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)
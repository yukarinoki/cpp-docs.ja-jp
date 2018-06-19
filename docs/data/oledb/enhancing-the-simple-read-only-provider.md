---
title: 単純な読み取り専用プロバイダーの向上 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c88714e4e1651839cdc5fd4b92d3c5222aa08d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100019"
---
# <a name="enhancing-the-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの機能の拡張
このセクションの内容を強化する方法を示しています、[単純な読み取り専用プロバイダー](../../data/oledb/implementing-the-simple-read-only-provider.md)前のセクションで作成します。 `IRowsetLocateImpl` 実装が作成、`IRowsetLocate`インターフェイスし、ブックマーク サポートを追加します。  
  
 プロバイダーがある場合は、ときに、機能を拡張して、トランザクションの処理または行をフェッチするアルゴリズムのパフォーマンスの向上は、プロバイダーの更新を行うことができます。 ほとんどのプロバイダーの機能強化には、既存の COM オブジェクトへのインターフェイスの追加が含まれます。  
  
 次のトピックの例では追加することによって行フェッチのメカニズムの強化、`IRowsetLocate`インターフェイスを`CAgentRowset`です。 トピックが方法を説明します。  
  
-   [RMyProviderRowset IRowsetLocate から継承する](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)です。  
  
-   [コンシューマーに返される列を動的に決定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)です。  
  
## <a name="see-also"></a>関連項目  
 [単純な読み取り専用プロバイダーの作成](../../data/oledb/creating-a-simple-read-only-provider.md)
---
title: プロバイダーでサポートされていないデータを変換する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0be19345ff6c425cfbc020f2096ca82680586d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095467"
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換
コンシューマーはプロバイダーによってサポートされていないデータ型を要求するとき、OLE DB プロバイダー テンプレートのコードに`IRowsetImpl::GetData`データ型に変換する Msdadc.dll を呼び出します。  
  
 ようなインターフェイスを実装する場合`IRowsetChange`データ変換を必要とする、変換を行う Msdaenum.dll を呼び出すことができます。 使用して`GetData`で例として、Atldb.h で定義されています。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
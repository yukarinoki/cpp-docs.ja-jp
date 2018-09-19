---
title: プロバイダーでサポートされていないデータを変換する |Microsoft Docs
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
ms.openlocfilehash: fa9fed1f7c779efc7104ec8138d618b85aeb2a33
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081742"
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換

コンシューマーがプロバイダーによってサポートされていないデータ型を要求すると、OLE DB プロバイダー テンプレートのコードを`IRowsetImpl::GetData`データ型に変換する Msdadc.dll を呼び出します。  
  
ようなインターフェイスを実装する場合`IRowsetChange`データ変換が必要ですが、変換を行う Msdaenum.dll を呼び出すことができます。 使用`GetData`、例として、Atldb.h で定義されています。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
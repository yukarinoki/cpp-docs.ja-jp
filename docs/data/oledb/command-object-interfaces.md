---
title: コマンド オブジェクト インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c597cc30e23ffce2787eac6c13f6ba8c53f96c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="command-object-interfaces"></a>コマンド オブジェクト インターフェイス
コマンド オブジェクトを使用して、`IAccessor`インターフェイス パラメーター バインディングを指定します。 コンシューマーは`IAccessor::CreateAccessor`、配列を渡す`DBBINDING`構造体。 `DBBINDING` 列のバインド (型の長さなど) についてを説明します。 プロバイダーは、構造体を受信し、データの転送方法と、変換が必要かどうかを決定します。  
  
 `ICommandText`インターフェイスには、テキスト コマンドを指定する方法が用意されています。 `ICommandProperties`インターフェイスは、すべてのコマンド プロパティを処理します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
---
title: 有効にして、OLE DB サービスを無効化 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6edd507edc21d58d17435b1d31d918a965db624a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100735"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB サービスの有効化と無効化

OLE DB サービス コンポーネント マネージャーは、コンシューマーが要求された拡張機能を満たすために個々 のサービス コンポーネントを起動するかどうかを判断する、プロバイダーによってサポートされているコンシューマーによって指定されたプロパティを比較します。 たとえば、アプリケーションがスクロール可能なカーソルを要求して、プロバイダーでは、順方向専用カーソルのみがサポート、サービスのコンポーネント マネージャーがスクロール可能な機能を提供する、クライアント カーソル エンジン サービスのコンポーネントを呼び出します。 アプリケーションがプロバイダーの行セットでは、既定でサポートされる拡張機能に依存して、アプリケーションが機能、機能が表示されないことクライアントによって返される行セットに対して要求するプロパティを明示的に設定していない場合カーソル エンジン。 相互運用できるように、アプリケーションが常にプロパティを設定の拡張機能を明示的に要求するために必要な場合。  
  
場合によっては、プロバイダーの特性を推測する既存のアプリケーションでうまく機能する個々 の OLE DB サービスを無効にする必要があります。 OLE DB サービスでは、個々 のサービス、または接続-接続によってごとに 1 つのプロバイダーを使用してすべてのアプリケーションまたはすべてのサービスを無効にする機能を提供します。  
  
## <a name="see-also"></a>関連項目  

[OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)
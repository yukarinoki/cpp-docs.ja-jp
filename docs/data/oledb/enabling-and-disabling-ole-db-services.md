---
title: 有効にして、OLE DB サービスを無効化 |Microsoft ドキュメント
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
ms.openlocfilehash: 785997cafec76bfa438382ace6930d53c31c4dc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099473"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB サービスの有効化と無効化
OLE DB サービス コンポーネント マネージャーは、個々 のサービス コンポーネントを起動して、コンシューマーによって要求された拡張機能を満たすかどうかを決定する、プロバイダーによってサポートされているにコンシューマーによって指定されたプロパティを比較します。 たとえば、アプリケーションがスクロール可能なカーソルを要求し、プロバイダーでは、順方向専用カーソルのみがサポートと場合、サービスのコンポーネント マネージャーは、スクロール可能な機能を提供するクライアント カーソル エンジン サービスのコンポーネントで呼び出されます。 アプリケーションがプロバイダーの行セットでは既定でサポートされている拡張機能に依存することと、アプリケーションが機能、機能が表示されないことクライアントによって返される行セットに対して要求するプロパティを明示的に設定していない場合カーソル エンジンです。 相互運用できるように、アプリケーションは常にプロパティを設定する拡張機能を明示的に要求必要な場所です。  
  
 場合によっては、プロバイダーの特性に関する前提条件を構成する既存のアプリケーションでうまく機能する個々 の OLE DB サービスを無効にする必要があります。 OLE DB サービスは、個々 のサービス、または接続の接続によってごとに、またはすべてのアプリケーションの 1 つのプロバイダーを使用して、すべてのサービスを無効にする機能を提供します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)
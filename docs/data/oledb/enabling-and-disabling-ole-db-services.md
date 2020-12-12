---
description: 詳細については、「OLE DB サービスの有効化と無効化」を参照してください。
title: OLE DB サービスの有効化と無効化
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: a2a3e51b69a0051b6a231d14c18f3b1f416fb547
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317663"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB サービスの有効化と無効化

OLE DB Service コンポーネントマネージャーは、コンシューマーによって指定されたプロパティをプロバイダーによってサポートされるプロパティと比較して、コンシューマーによって要求された拡張機能を満たすために個々のサービスコンポーネントを使用できるかどうかを判断します。 たとえば、アプリケーションがスクロール可能なカーソルを要求し、プロバイダーが順方向専用カーソルをサポートしている場合、サービスコンポーネントマネージャーは、クライアントカーソルエンジンサービスコンポーネントを使用して、スクロール可能な機能を提供します。 アプリケーションがプロバイダーの行セットで既定でサポートされている拡張機能に依存していて、アプリケーションがその機能を要求するように明示的に設定していない場合、クライアントカーソルエンジンによって返される行セットに機能が表示されない可能性があります。 相互運用可能にするには、アプリケーションは常に、必要に応じて拡張機能を明示的に要求するようにプロパティを設定します。

場合によっては、プロバイダーの特性を想定している既存のアプリケーションで、個々の OLE DB サービスを無効にすることが必要になることがあります。 OLE DB サービスは、接続ごとに、または1つのプロバイダーを使用するすべてのアプリケーションで、個々のサービスまたはすべてのサービスを無効にする機能を提供します。

## <a name="see-also"></a>関連項目

[リソースプーリングとサービスの OLE DB](../../data/oledb/ole-db-resource-pooling-and-services.md)

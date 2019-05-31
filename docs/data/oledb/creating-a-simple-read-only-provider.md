---
title: 単純な読み取り専用プロバイダーの作成
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: c0f31818002ce4611926d942b3bc556e31c1ae6f
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524708"
---
# <a name="creating-a-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの作成

::: moniker range="vs-2019"

ATL OLE DB プロバイダー ウィザードは、Visual Studio 2019 以降では使用できません。

::: moniker-end

::: moniker range="vs-2017"

**ATL プロジェクト ウィザード**と **ATL OLE DB プロバイダー ウィザード**を使用して OLE DB プロバイダーを作成した場合、サポートしたい他の機能を追加することができます。 コンシューマーに送信するデータの種類とその条件を調べることからプロバイダーの設計を始めます。 特に重要なのは、コマンド、トランザクション、およびその他の省略可能なオブジェクトをサポートする必要があるかどうかを判断することです。 最初の設計が優れていれば、実装とテストの時間が短縮されます。

この例には 2 つの項目があります。

- まず、文字列のペアを読み取る[単純な読み取り専用プロバイダーを作成する](../../data/oledb/implementing-the-simple-read-only-provider.md)方法を説明します。

- 次に、`IRowsetLocate` インターフェイスを追加して[単純な読み取り専用プロバイダーを強化する](../../data/oledb/enhancing-the-simple-read-only-provider.md)方法を説明します。

::: moniker-end

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)<br/>

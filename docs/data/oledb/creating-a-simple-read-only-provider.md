---
description: 詳細については、「簡単な Read-Only プロバイダーの作成」を参照してください。
title: 単純な読み取り専用プロバイダーの作成
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: 1904e850bc6a681e13e4799a2822963932ad9dfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323221"
---
# <a name="creating-a-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの作成

::: moniker range="msvc-160"

ATL OLE DB プロバイダー ウィザードは、Visual Studio 2019 以降では使用できません。

::: moniker-end

::: moniker range="<=msvc-150"

**ATL プロジェクト ウィザード** と **ATL OLE DB プロバイダー ウィザード** を使用して OLE DB プロバイダーを作成した場合、サポートしたい他の機能を追加することができます。 コンシューマーに送信するデータの種類とその条件を調べることからプロバイダーの設計を始めます。 特に重要なのは、コマンド、トランザクション、およびその他の省略可能なオブジェクトをサポートする必要があるかどうかを判断することです。 最初の設計が優れていれば、実装とテストの時間が短縮されます。

この例には 2 つの項目があります。

- まず、文字列のペアを読み取る[単純な読み取り専用プロバイダーを作成する](../../data/oledb/implementing-the-simple-read-only-provider.md)方法を説明します。

- 次に、`IRowsetLocate` インターフェイスを追加して[単純な読み取り専用プロバイダーを強化する](../../data/oledb/enhancing-the-simple-read-only-provider.md)方法を説明します。

::: moniker-end

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)<br/>

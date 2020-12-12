---
description: 詳細については、「Simple Read-Only プロバイダーの拡張」を参照してください。
title: 単純な読み取り専用プロバイダーの機能の拡張
ms.date: 10/26/2018
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
ms.openlocfilehash: 00a0ea4fb9b759447026353ba0d78c7c856b15ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317637"
---
# <a name="enhancing-the-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの機能の拡張

このセクションでは、前のセクションで作成した [単純な読み取り専用プロバイダー](../../data/oledb/implementing-the-simple-read-only-provider.md) を拡張する方法について説明します。 `IRowsetLocateImpl` インターフェイスの実装を作成 `IRowsetLocate` し、ブックマークサポートを追加します。

動作しているプロバイダーがある場合は、プロバイダーを更新したり、トランザクションを処理したり、行フェッチアルゴリズムのパフォーマンスを向上させたりするために、プロバイダーを拡張することができます。 ほとんどのプロバイダーの拡張機能には、既存の COM オブジェクトへのインターフェイスの追加が含まれます。

次のトピックの例では、にインターフェイスを追加することによって、行フェッチ機構を拡張して `IRowsetLocate` `CAgentRowset` います。 このトピックでは、次の方法について説明します。

- [RCustomRowset を IRowsetLocate から継承](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)します。

- [コンシューマーに返される列を動的に決定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)します。

## <a name="see-also"></a>関連項目

[単純な Read-Only プロバイダーの作成](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>

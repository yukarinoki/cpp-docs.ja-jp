---
description: 詳細については、「コマンドオブジェクトインターフェイス」を参照してください。
title: Command オブジェクト インターフェイス
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 07dce6a71e7afd3a47c63942d48dd78d758103f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307523"
---
# <a name="command-object-interfaces"></a>Command オブジェクト インターフェイス

Command オブジェクトは、インターフェイスを使用して `IAccessor` パラメーターバインディングを指定します。 コンシューマーは `IAccessor::CreateAccessor` を呼び出し、構造体の配列を渡し `DBBINDING` ます。 `DBBINDING` 列のバインド (型や長さなど) に関する情報を格納します。 プロバイダーは、構造体を受け取り、データの転送方法と変換が必要かどうかを決定します。

インターフェイスには、 `ICommandText` テキストコマンドを指定する方法が用意されています。 `ICommandProperties`インターフェイスは、すべてのコマンドプロパティを処理します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>

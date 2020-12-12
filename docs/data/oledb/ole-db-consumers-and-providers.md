---
description: 詳細については、OLE DB のコンシューマーとプロバイダーに関するページを参照してください。
title: OLE DB コンシューマーとプロバイダー
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
ms.openlocfilehash: dedcbe7837cf7fad5bc9db8832e34edd3859a02b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317143"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB コンシューマーとプロバイダー

OLE DB アーキテクチャでは、コンシューマーとプロバイダーのモデルが使用されます。 コンシューマーがデータの要求を行います。 プロバイダーは、データを表形式で配置してコンシューマーに返すことで、これらの要求に応答します。 コンシューマーが行うことができるすべての呼び出しは、プロバイダーに実装する必要があります。

技術的に定義されたコンシューマーは、OLE DB インターフェイスを介してデータにアクセスするシステムコードまたはアプリケーションコード (必ずしも OLE DB コンポーネントではありません) です。 インターフェイスは、プロバイダーで実装されます。 プロバイダーは、データへのアクセスをカプセル化し、他のオブジェクト (つまりコンシューマー) に公開するために OLE DB インターフェイスを実装するソフトウェアコンポーネントです。

ロールの場合、コンシューマーは OLE DB インターフェイスでメソッドを呼び出します。OLE DB プロバイダーは、必要な OLE DB インターフェイスを実装します。

OLE DB は、特に n 層の状況では、これらの役割が常に意味を持たないため、クライアントとサーバーという用語を回避します。 コンシューマーは、別のコンポーネントを提供する層のコンポーネントである可能性があるため、それを呼び出すために、クライアントコンポーネントが混乱する可能性があります。 また、プロバイダーは、サーバーよりもデータベースドライバーのように動作することがあります。

## <a name="see-also"></a>関連項目

[OLE DB プログラミング](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)

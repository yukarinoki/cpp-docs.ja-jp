---
description: '詳細情報: プロバイダー Wizard-Generated ファイル'
title: プロバイダー ウィザードで生成されたファイル
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 95c9641f10acef4a55b8de15752eb125e75d874a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316896"
---
# <a name="provider-wizard-generated-files"></a>プロバイダー ウィザードで生成されたファイル

::: moniker range="msvc-160"

ATL OLE DB プロバイダー ウィザードは、Visual Studio 2019 以降では使用できません。

::: moniker-end

::: moniker range="<=msvc-150"

**ATL OLE DB プロバイダー ウィザード** では、以下のファイルが生成されます。 以下のトピックでは、*Custom* という短い名前が使用されていますが、正確なファイル名は、プロバイダー作成時に選択した名前によって決まります。

|ファイル名|説明|
|---------------|-----------------|
|*Custom* RS.cpp|コマンド ヘルパー `Execute` メソッドとプロバイダーの列マップが含まれます。|
|*Custom* DS.h|データ ソース オブジェクトが実装されます。 このヘッダー ファイルには、データ ソース プロパティのプロパティ マップが含まれます。|
|*Custom* RS.h|コマンドおよび行セットオブジェクトが実装されます。 このヘッダー ファイルには、行セットおよびコマンド プロパティのプロパティ マップが含まれます。|
|*Custom* Sess.h|セッション オブジェクトが実装されます。 このヘッダー ファイルには、セッション プロパティのプロパティ マップが含まれます。|
|*Custom*.rgs|**OLE DB プロバイダー ウィザード** によって生成された登録済みオブジェクトが含まれます。|

::: moniker-end

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)<br/>

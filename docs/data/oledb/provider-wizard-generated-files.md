---
title: プロバイダー ウィザードで生成されたファイル
ms.date: 10/18/2018
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: c93618ebe9d3140864c2c47867ea970777c208b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580935"
---
# <a name="provider-wizard-generated-files"></a>プロバイダー ウィザードで生成されたファイル

**ATL OLE DB プロバイダー ウィザード**次のファイルが生成されます。 次のトピックを使用して、短い名前*カスタム*、正確なファイル名が選択したプロバイダーを作成するときに依存しています。

|ファイル名|説明|
|---------------|-----------------|
|*カスタム*RS.cpp|コマンドのヘルパーを含む`Execute`メソッドとプロバイダーの列のマップ。|
|*カスタム*DS.h|データ ソース オブジェクトを実装します。 このヘッダー ファイルには、データ ソースのプロパティのプロパティのマップが含まれています。|
|*カスタム*RS.h|コマンドや行セット オブジェクトを実装します。 このヘッダー ファイルには、行セットとコマンドのプロパティのプロパティのマップが含まれています。|
|*カスタム*Sess.h|セッション オブジェクトを実装します。 このヘッダー ファイルには、セッションのプロパティのプロパティのマップが含まれています。|
|*カスタム*.rgs|によって生成された登録済みのオブジェクトが含まれています、 **OLE DB プロバイダー ウィザード**します。|

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)<br/>

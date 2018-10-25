---
title: プロバイダー ウィザードで生成されたファイル |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9bc7c85dccdfe095412450d5020fc8a6b42d516
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076972"
---
# <a name="provider-wizard-generated-files"></a>プロバイダー ウィザードで生成されたファイル

ATL OLE DB プロバイダー ウィザードでは、次のファイルを生成します。 次のトピックを使用して、短い名前*カスタム*、正確なファイル名が選択したプロバイダーを作成するときに依存しています。

|ファイル名|説明|
|---------------|-----------------|
|*カスタム*RS.cpp|コマンドのヘルパーを含む`Execute`メソッドとプロバイダーの列のマップ。|
|*カスタム*DS.h|データ ソース オブジェクトを実装します。 このヘッダー ファイルには、データ ソースのプロパティのプロパティのマップが含まれています。|
|*カスタム*RS.h|コマンドや行セット オブジェクトを実装します。 このヘッダー ファイルには、行セットとコマンドのプロパティのプロパティのマップが含まれています。|
|*カスタム*Sess.h|セッション オブジェクトを実装します。 このヘッダー ファイルには、セッションのプロパティのプロパティのマップが含まれています。|
|*カスタム*.rgs|OLE DB プロバイダー ウィザードで生成された登録済みのオブジェクトが含まれています。|

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)
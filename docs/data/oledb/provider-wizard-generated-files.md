---
title: プロバイダー ウィザードで生成されたファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: ac23f06bf1ae697ecd627d493aa5902219488138
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106009"
---
# <a name="provider-wizard-generated-files"></a>プロバイダー ウィザードで生成されたファイル
ATL OLE DB プロバイダー ウィザードでは、次のファイルを生成します。 次のトピックでは、短い名前"MyProvider"を使用するが、正確なファイル名は、プロバイダーを作成するときに対して行った選択によって異なります。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|MyProviderRS.cpp|コマンドのヘルパーを含む`Execute`メソッドとプロバイダー 列のマップ。|  
|MyProviderDS.h|データ ソース オブジェクトを実装します。 このヘッダー ファイルには、データ ソースのプロパティのプロパティ マップが含まれています。|  
|MyProviderRS.h|コマンドや行セット オブジェクトを実装します。 このヘッダー ファイルには、行セットとコマンドのプロパティのプロパティ マップが含まれています。|  
|MyProviderSess.h|セッション オブジェクトを実装します。 このヘッダー ファイルには、セッションのプロパティのプロパティ マップが含まれています。|  
|MyProvider.rgs|OLE DB プロバイダー ウィザードによって生成された登録済みのオブジェクトが含まれています。|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)
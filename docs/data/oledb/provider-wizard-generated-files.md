---
title: プロバイダー ウィザードで生成されたファイル |Microsoft Docs
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
ms.openlocfilehash: 26e20e0417e2253158930a8d3d055171fe767001
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108405"
---
# <a name="provider-wizard-generated-files"></a>プロバイダー ウィザードで生成されたファイル

ATL OLE DB プロバイダー ウィザードでは、次のファイルを生成します。 次のトピックを使用して、短い名前"MyProvider"が、正確なファイル名は、プロバイダーを作成するときに対して行った選択によって異なります。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|MyProviderRS.cpp|コマンドのヘルパーを含む`Execute`メソッドとプロバイダーの列のマップ。|  
|MyProviderDS.h|データ ソース オブジェクトを実装します。 このヘッダー ファイルには、データ ソースのプロパティのプロパティのマップが含まれています。|  
|MyProviderRS.h|コマンドや行セット オブジェクトを実装します。 このヘッダー ファイルには、行セットとコマンドのプロパティのプロパティのマップが含まれています。|  
|MyProviderSess.h|セッション オブジェクトを実装します。 このヘッダー ファイルには、セッションのプロパティのプロパティのマップが含まれています。|  
|MyProvider.rgs|OLE DB プロバイダー ウィザードで生成された登録済みのオブジェクトが含まれています。|  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)
---
title: プロパティ マップ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbed70f7871cb215a944a5143793b26b4196d7bc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052754"
---
# <a name="property-maps"></a>プロパティ マップ

に加えて、セッション、行セットと省略可能なコマンド オブジェクトは、各プロバイダーは、1 つまたは複数のプロパティをサポートします。 これらのプロパティは OLE DB プロバイダー ウィザードで作成されたヘッダー ファイルに含まれているプロパティのマップで定義されます。 各ヘッダー ファイルには、オブジェクトまたはそのファイルで定義されたオブジェクトに対して定義されている OLE DB プロパティのグループのプロパティのマップが含まれています。 データ ソース オブジェクトを含むヘッダー ファイルには、プロパティのマップも含まれています、 [DataSource プロパティ](https://msdn.microsoft.com/library/ms724188)します。 Session.h にはプロパティのマップが含まれています、[セッション プロパティ](/previous-versions/windows/desktop/ms714221)します。 行セットとコマンドのオブジェクトと呼ばれる、1 つのヘッダー ファイル内に存在*projectname*RS.h します。 これらのプロパティのメンバーである、[行セット プロパティ](/previous-versions/windows/desktop/ms711252)グループ。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
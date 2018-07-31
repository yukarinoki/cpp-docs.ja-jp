---
title: 有効にして、プロバイダーのサービスを無効化 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36cb39b467cb413cdf74bef52430cf8caf746199
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340691"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>プロバイダーのサービスの有効化と無効化
各 OLE DB サービスを有効になっているまたは 1 つのプロバイダーにアクセスするすべてのアプリケーションに対して既定で無効になっていることができます。 プロバイダーの CLSID、OLEDB_SERVICES レジストリ エントリを追加することでこれは、`DWORD`次の表に示すように、有効または無効にすると、サービスを指定する値。  
  
|既定のサービスを有効になっています。|キーワードの値|  
|------------------------------|-------------------|  
|すべてのサービス (既定値)|0 xffffffff|  
|プールを除くすべてと自動確保|0xfffffffe|  
|クライアント カーソルを除くすべて|0xfffffffb|  
|プールで自動確保、およびクライアント カーソルを除くすべて|0xfffffff0|  
|サービスはありません。|0x00000000|  
|集計、すべてのサービス使用不可|\<見つからないキー >|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)
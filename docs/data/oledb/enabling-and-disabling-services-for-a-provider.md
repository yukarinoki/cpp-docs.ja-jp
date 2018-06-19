---
title: 有効にして、プロバイダーのサービスを無効化 |Microsoft ドキュメント
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
ms.openlocfilehash: ef36e35234aa4878e30e70748a5b2ba2975c38dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099733"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>プロバイダーのサービスの有効化と無効化
各 OLE DB サービスを有効になっているまたは 1 つのプロバイダーにアクセスするすべてのアプリケーションに対して既定で無効になっていることができます。 これは、追加することで、 **OLEDB_SERVICES**プロバイダーは、下にレジストリ エントリで、CLSID の`DWORD`次の表に示すように、有効または無効にすると、サービスを指定する値。  
  
|既定のサービスを有効になっています。|キーワードの値|  
|------------------------------|-------------------|  
|すべてのサービス (既定値)|0 xffffffff|  
|以外のすべてのプールと自動確保|0xfffffffe|  
|以外のすべてのクライアント カーソル|0xfffffffb|  
|プールが、自動確保、およびクライアント カーソルを除くすべて|0xfffffff0|  
|サービスはありません。|0x00000000|  
|集約なし、すべてのサービスを無効化|\<キーがありません >|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)
---
title: レジストリ エントリ (ATL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac8e202fc2fc3d58e2d57a9fbfa15264d9fd310e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="registry-entries"></a>レジストリ エントリ
DCOM では、アプリケーション Id (Appid)、レジストリで一元的な場所に 1 つまたは複数の DCOM オブジェクトの構成オプションをグループ化の概念が導入されました。 AppID を指定するには、名前付きの下にあるオブジェクトの CLSID 値 AppID の値を示すです。  
  
 既定では、ATL で生成されたサービスは GUID と、CLSID は、AppID を使用します。 `HKEY_CLASSES_ROOT\AppID`DCOM に固有のエントリを指定することができます。 最初に、2 つのエントリが存在します。  
  
-   `LocalService`、、サービスの名前と同じ値を使用します。 この値が存在する場合は、代わりに使用、 `LocalServer32` CLSID の下にあるキー。  
  
-   `ServiceParameters`に等しい値を持つ`-Service`します。 この値は、起動したときにサービスに渡されるパラメーターを指定します。 これらのパラメーターは、サービスに渡される注`ServiceMain`機能しない`WinMain`です。  
  
 DCOM サービスも下にある別のキーを作成する必要があります`HKEY_CLASSES_ROOT\AppID`です。 このキーがの exe ファイルの名前と同じと AppID のエントリを指す AppID 値が含まれている、相互参照として機能します。  
  
## <a name="see-also"></a>関連項目  
 [サービス](../atl/atl-services.md)


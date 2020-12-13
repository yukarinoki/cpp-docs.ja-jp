---
description: 詳細については、「レジストリエントリ」を参照してください。
title: レジストリエントリ (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: c89c8f64a91c09f16333c3381a33d792332543d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138581"
---
# <a name="registry-entries"></a>レジストリ エントリ

DCOM では、アプリケーション Id (AppIDs) の概念が導入されました。これは、1つまたは複数の DCOM オブジェクトの構成オプションをレジストリ内の集中管理された場所にグループ化します。 AppID を指定するには、オブジェクトの CLSID の下にある AppID の名前付きの値を指定します。

既定では、ATL によって生成されるサービスはその CLSID を AppID の GUID として使用します。 で `HKEY_CLASSES_ROOT\AppID` は、DCOM 固有のエントリを指定できます。 最初は2つのエントリが存在します。

- `LocalService`サービスの名前と等しい値を持つ。 この値が存在する場合は、CLSID の下でキーの代わりに使用され `LocalServer32` ます。

- `ServiceParameters`値がに等しい `-Service` 。 この値は、サービスの開始時にサービスに渡されるパラメーターを指定します。 これらのパラメーターは、ではなくサービスの関数に渡されることに注意 `ServiceMain` `WinMain` してください。

また、任意の DCOM サービスで、の下に別のキーを作成する必要があり `HKEY_CLASSES_ROOT\AppID` ます。 このキーは、実行可能ファイルの名前と同じであり、相互参照として機能します。これは、AppID エントリを指す AppID 値を含んでいるためです。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)

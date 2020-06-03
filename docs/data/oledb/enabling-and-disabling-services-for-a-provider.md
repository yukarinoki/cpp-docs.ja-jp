---
title: プロバイダーのサービスの有効化と無効化
ms.date: 07/30/2019
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: a74f8a8b099a30cf25007547e8059c77728435f9
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2019
ms.locfileid: "79544460"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>プロバイダーのサービスの有効化と無効化

1つのプロバイダーにアクセスするすべてのアプリケーションで、個々の OLE DB サービスを既定で有効または無効にすることができます。 これを行うには、次の表に示すように、プロバイダーの CLSID の下に OLEDB_SERVICES レジストリエントリを追加し、有効または無効にするサービスを指定する DWORD 値を設定します。

|既定のサービスが有効|DWORD 値|
|------------------------------|-------------------|
|クライアントカーソルとプールを除くすべてのサービス|0xfffffffa|
|クライアントカーソル以外のすべてのサービス|0xfffffffb|
|プールと自動参加を除くすべてのサービス|0xfffffffc|
|プールを除くすべてのサービス|0xfffffffe|
|すべてのサービス (既定)|~|
|サービスがありません|0x00000000|
|集計なし、すべてのサービスは無効|OLEDB_Services レジストリエントリがありません|

## <a name="see-also"></a>参照

[OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)

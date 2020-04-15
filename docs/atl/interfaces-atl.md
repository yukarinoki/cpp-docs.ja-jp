---
title: インターフェイス (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 56d5a010bc28257dce181ee33e0ddf74655ccd3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319388"
---
# <a name="interfaces-atl"></a>インターフェイス (ATL)

インターフェイスとは、オブジェクトが機能を外部に公開する方法です。 COM では、インターフェイスは、オブジェクトによって実装される関数へのポインタ (C++ vtable など) のテーブルです。 表はインターフェースを表し、それが指す関数はそのインターフェースのメソッドです。 オブジェクトは、選択した数のインターフェイスを公開できます。

各インターフェイスは、基本的な COM インターフェイス[IUnknown](../atl/iunknown.md)に基づいています。 オブジェクトによって公開`IUnknown`される他のインターフェイスへのナビゲーションを許可するメソッド。

また、各インターフェイスには一意のインターフェイス ID (IID) が与えられます。 この一意性により、インターフェイスのバージョン管理を容易にサポートできます。 インターフェイスの新しいバージョンは、単に新しいインターフェイスで、新しい IID を持ちます。

> [!NOTE]
> 標準 COM インターフェイスおよび OLE インターフェイスの IID は、あらかじめ定義されています。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[COM オブジェクトとインターフェイス](/windows/win32/com/com-objects-and-interfaces)

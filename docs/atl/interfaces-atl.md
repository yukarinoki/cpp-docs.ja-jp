---
title: インターフェイス (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 5416fb8a99420f0f6c84318753ee3399ccf5db2a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287376"
---
# <a name="interfaces-atl"></a>インターフェイス (ATL)

インターフェイスは、オブジェクトが外部にその機能を公開する方法です。 COM では、インターフェイスは、(C++ vtable) など、オブジェクトによって実装される関数へのポインターのテーブルです。 テーブルは、インターフェイスを表し、ポイントする関数は、そのインターフェイスのメソッド。 オブジェクトは、インターフェイスを多くを公開できます。

各インターフェイスは、基本的な COM インターフェイスに基づいて[IUnknown](../atl/iunknown.md)します。 メソッド`IUnknown`オブジェクトによって公開されている他のインターフェイスに移動できます。

また、各インターフェイスには、一意のインターフェイス ID (IID) が与えられます。 この一意性は、インターフェイスのバージョン管理のサポートが容易にします。 インターフェイスの新しいバージョンには、新しい IID を持つ、新しいインターフェイスだけです。

> [!NOTE]
>  定義済みは、標準の COM と OLE インターフェイスの Iid。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[COM オブジェクトとインターフェイス](/windows/desktop/com/com-objects-and-interfaces)

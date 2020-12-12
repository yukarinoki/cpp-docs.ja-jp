---
description: '詳細情報: インターフェイス (ATL)'
title: インターフェイス (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: d68f482d05ff828631f5f9f27085f24af188d643
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147694"
---
# <a name="interfaces-atl"></a>インターフェイス (ATL)

インターフェイスは、オブジェクトが外部との間で機能を公開する方法です。 COM では、インターフェイスは、オブジェクトによって実装される関数へのポインター (C++ の vtable など) のテーブルです。 この表は、インターフェイスを表しています。このテーブルが指す関数は、そのインターフェイスのメソッドです。 オブジェクトは、選択された数のインターフェイスを公開できます。

各インターフェイスは、基本的な COM インターフェイス [IUnknown](../atl/iunknown.md)に基づいています。 のメソッドを `IUnknown` 使用すると、オブジェクトによって公開されている他のインターフェイスに移動できます。

また、各インターフェイスには一意のインターフェイス ID (IID) が割り当てられます。 この一意性により、インターフェイスのバージョン管理を簡単にサポートできるようになります。 新しいバージョンのインターフェイスは、新しい IID を使用した新しいインターフェイスにすぎません。

> [!NOTE]
> 標準の COM および OLE インターフェイスの Iid がは事前に定義されています。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[COM オブジェクトとインターフェイス](/windows/win32/com/com-objects-and-interfaces)

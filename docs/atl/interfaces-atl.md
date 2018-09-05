---
title: インターフェイス (ATL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04f77981bd922f73c99102c444a7c95f7240adbc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764621"
---
# <a name="interfaces-atl"></a>インターフェイス (ATL)

インターフェイスは、オブジェクトが外部にその機能を公開する方法です。 COM では、インターフェイスは、(C++ vtable) など、オブジェクトによって実装される関数へのポインターのテーブルです。 テーブルは、インターフェイスを表し、ポイントする関数は、そのインターフェイスのメソッド。 オブジェクトは、インターフェイスを多くを公開できます。

各インターフェイスは、基本的な COM インターフェイスに基づいて[IUnknown](../atl/iunknown.md)します。 メソッド`IUnknown`オブジェクトによって公開されている他のインターフェイスに移動できます。

また、各インターフェイスには、一意のインターフェイス ID (IID) が与えられます。 この一意性は、インターフェイスのバージョン管理のサポートが容易にします。 インターフェイスの新しいバージョンには、新しい IID を持つ、新しいインターフェイスだけです。

> [!NOTE]
>  定義済みは、標準の COM と OLE インターフェイスの Iid。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)   
[COM オブジェクトとインターフェイス](/windows/desktop/com/com-objects-and-interfaces)


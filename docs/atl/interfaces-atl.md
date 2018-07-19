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
ms.openlocfilehash: b7becd9e27294c81ce6144d08c79cfac52636fbf
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848266"
---
# <a name="interfaces-atl"></a>インターフェイス (ATL)
インターフェイスは、オブジェクトが外部にその機能を公開する方法です。 COM では、インターフェイスは、(C++ vtable) など、オブジェクトによって実装される関数へのポインターのテーブルです。 テーブルは、インターフェイスを表し、ポイントする関数は、そのインターフェイスのメソッド。 オブジェクトは、インターフェイスを多くを公開できます。  
  
 各インターフェイスは、基本的な COM インターフェイスに基づいて[IUnknown](../atl/iunknown.md)します。 メソッド`IUnknown`オブジェクトによって公開されている他のインターフェイスに移動できます。  
  
 また、各インターフェイスには、一意のインターフェイス ID (IID) が与えられます。 この一意性は、インターフェイスのバージョン管理のサポートが容易にします。 インターフェイスの新しいバージョンには、新しい IID を持つ、新しいインターフェイスだけです。  
  
> [!NOTE]
>  定義済みは、標準の COM と OLE インターフェイスの Iid。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [COM オブジェクトとインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms690343)


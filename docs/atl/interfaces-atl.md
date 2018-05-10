---
title: インターフェイス (ATL) |Microsoft ドキュメント
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
ms.openlocfilehash: 0db5a79f187cb0fe320bf67aace751a5d4c537d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="interfaces-atl"></a>インターフェイス (ATL)
インターフェイスは、オブジェクトが外部への機能を公開する方法です。 COM では、インターフェイスは、(C++ vtable) のようなオブジェクトによって実装されている関数へのポインターのテーブルです。 テーブルは、インターフェイスを表し、指す関数は、そのインターフェイスのメソッド。 オブジェクトは、選択され、同数のインターフェイスを公開できます。  
  
 各インターフェイスは、基本的な COM インターフェイスに基づいて[IUnknown](../atl/iunknown.md)です。 メソッド**IUnknown**オブジェクトによって公開されるその他のインターフェイスに移動できます。  
  
 また、各インターフェイスには、一意のインターフェイス ID (IID) が与えられます。 この一意性しやすいインターフェイスのバージョン管理をサポートします。 インターフェイスの新しいバージョンは、新しい IID を持つ、新しいインターフェイスだけです。  
  
> [!NOTE]
>  標準の COM と OLE インターフェイスの Iid が定義されています。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [COM オブジェクトとインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms690343)


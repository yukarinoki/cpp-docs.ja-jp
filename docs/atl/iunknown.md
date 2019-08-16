---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 9c9faa4cffcdc8e6840dfbbe141cb63f51155ded
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492073"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)は、他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、次の3つのメソッドを定義します。[QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))、 [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)、および[Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)。 [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))を使用すると、インターフェイスユーザーは、インターフェイスの別のインターフェイスへのポインターをオブジェクトに要求できます。 [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)と[Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)は、インターフェイスの参照カウントを実装します。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[IUnknown とインターフェイスの継承](/windows/win32/com/iunknown-and-interface-inheritance)

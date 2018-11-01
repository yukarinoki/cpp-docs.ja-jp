---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IUnknown
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 760db28f4016ed529b45c72d25eaabf664642cd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430044"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)は他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、3 つのメソッドを定義します。 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))、 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)、および[リリース](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)します。 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))インターフェイス ユーザーに対して、別のインターフェイスへのポインター オブジェクトを要求できます。 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)と[リリース](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)インターフェイスの参照カウントを実装します。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[IUnknown とインターフェイスの継承](/windows/desktop/com/iunknown-and-interface-inheritance)


---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 17561092c6cccbad264bb82d68dbef9c0e078f76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250295"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)は他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、3 つのメソッドを定義します。[QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))、 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)、および[リリース](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)します。 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))インターフェイス ユーザーに対して、別のインターフェイスへのポインター オブジェクトを要求できます。 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)と[リリース](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)インターフェイスの参照カウントを実装します。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[IUnknown とインターフェイスの継承](/windows/desktop/com/iunknown-and-interface-inheritance)

---
title: IUnknown |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5840fc7e4623ee6163b3caf1a43eff358a152e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039038"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)は他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、3 つのメソッドを定義します。 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))、 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)、および[リリース](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)します。 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))インターフェイス ユーザーに対して、別のインターフェイスへのポインター オブジェクトを要求できます。 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)と[リリース](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)インターフェイスの参照カウントを実装します。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[IUnknown とインターフェイスの継承](/windows/desktop/com/iunknown-and-interface-inheritance)


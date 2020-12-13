---
description: '詳細情報: IUnknown'
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: ddfd35155162275885a1c0c842b4589fa6773a4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152647"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) は、他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、 [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))、 [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)、 [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)という3つのメソッドを定義します。 [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) を使用すると、インターフェイスユーザーは、インターフェイスの別のインターフェイスへのポインターをオブジェクトに要求できます。 [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) と [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) は、インターフェイスの参照カウントを実装します。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[IUnknown とインターフェイスの継承](/windows/win32/com/iunknown-and-interface-inheritance)

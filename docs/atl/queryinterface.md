---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: de2762cff3d697261e159336d866a5a7cb10fafa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492001"
---
# <a name="queryinterface"></a>QueryInterface

オブジェクトが静的に提供する機能を (インスタンス化される前に) 表現できるメカニズムがありますが、基本的な COM 機構は、 `IUnknown` [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))と呼ばれるメソッドを使用することです。

すべてのインターフェイスはから`IUnknown`派生しているので、すべて`QueryInterface`のインターフェイスにの実装があります。 実装に関係なく、このメソッドは、呼び出し元がポインターを必要とするインターフェイスの IID を使用してオブジェクトを照会します。 オブジェクトがそのインターフェイスをサポートし`QueryInterface`ている場合、はインターフェイスへのポインターを`AddRef`取得し、もを呼び出します。 それ以外の場合は、E_NOINTERFACE エラーコードを返します。

[参照カウント](../atl/reference-counting.md)ルールは常に従う必要があることに注意してください。 インターフェイスポインターで`Release`を呼び出して参照カウントをゼロに減らすと、そのポインターを再び使用することはできません。 場合によっては、オブジェクトへの弱い参照を取得しなければならないことがあります (つまり、参照カウントをインクリメントせずにインターフェイスの1つへのポインターを取得することもでき`QueryInterface`ます) `Release`が、を呼び出した後にを呼び出すことによって、この操作を実行することはできません。 このような方法で取得したポインターは無効であるため、使用しないでください。 [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces)が定義されている場合は、これがより簡単に明らかになるため、このマクロを定義することで、参照カウントのバグを見つけることができます。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[QueryInterfaceオブジェクト内の移動](/windows/win32/com/queryinterface--navigating-in-an-object)

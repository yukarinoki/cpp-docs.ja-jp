---
description: 詳細については、「QueryInterface」を参照してください。
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: b22163c9e69bd5573f8e6060df0457862813c366
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159168"
---
# <a name="queryinterface"></a>QueryInterface

オブジェクトが静的に提供する機能を (インスタンス化される前に) 表現できるメカニズムがありますが、基本的な COM 機構は、 `IUnknown` [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))と呼ばれるメソッドを使用することです。

すべてのインターフェイスはから派生している `IUnknown` ので、すべてのインターフェイスにの実装があり `QueryInterface` ます。 実装に関係なく、このメソッドは、呼び出し元がポインターを必要とするインターフェイスの IID を使用してオブジェクトを照会します。 オブジェクトがそのインターフェイスをサポートしている場合、は `QueryInterface` インターフェイスへのポインターを取得し、もを呼び出し `AddRef` ます。 それ以外の場合は、E_NOINTERFACE エラーコードを返します。

[参照カウント](../atl/reference-counting.md)ルールは常に従う必要があることに注意してください。 `Release`インターフェイスポインターでを呼び出して参照カウントをゼロに減らすと、そのポインターを再び使用することはできません。 場合によっては、オブジェクトへの弱い参照を取得しなければならないことがあります (つまり、参照カウントをインクリメントせずにインターフェイスの1つへのポインターを取得することもできます) が、を呼び出した後にを呼び出すことによって、この操作を実行することはできません `QueryInterface` `Release` 。 このような方法で取得したポインターは無効であるため、使用しないでください。 これは [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) が定義されている場合にも簡単に明らかになるため、このマクロを定義すると、参照カウントのバグを見つけるのに便利です。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[QueryInterface: オブジェクト内の移動](/windows/win32/com/queryinterface--navigating-in-an-object)

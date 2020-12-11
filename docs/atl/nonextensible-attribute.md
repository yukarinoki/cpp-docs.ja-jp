---
description: 詳細については、「非拡張属性」を参照してください。
title: 非拡張属性
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: 5bad214d6688570bc4a69aca952f6bed98c2b0dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159402"
---
# <a name="nonextensible-attribute"></a>非拡張属性

デュアルインターフェイスが実行時に拡張されない場合 (つまり、vtable 経由では使用できないからのメソッドまたはプロパティを指定しない場合 `IDispatch::Invoke` ) は、 **非拡張** 属性をインターフェイス定義に適用する必要があります。 この属性は、コンパイル時に完全なコード検証を有効にするために使用できるクライアント言語 (Visual Basic など) に情報を提供します。 この属性が指定されていない場合、実行時までクライアントコードでバグが非表示のままになる可能性があります。

**非拡張** 属性と例の詳細については、「[非拡張](../windows/attributes/nonextensible.md)」を参照してください。

## <a name="see-also"></a>関連項目

[デュアルインターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

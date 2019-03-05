---
title: nonextensible 属性
ms.date: 11/04/2016
f1_keywords:
- nonextensible
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: 5aa5b8514435e9876500daa4d92504d75eb6dc23
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257632"
---
# <a name="nonextensible-attribute"></a>nonextensible 属性

かどうかは、デュアル インターフェイスは実行時に拡張できません (つまり、メソッドまたはプロパティを使用してを提供しません`IDispatch::Invoke`は、vtable を使用して使用できません)、適用する必要があります、 **nonextensible**属性のインターフェイスを定義。 この属性は、コンパイル時に完全なコードの検証を有効にするために使用する (Visual Basic) などのクライアント言語に情報を提供します。 この属性が指定されていないバグが非表示のままクライアント コードで実行時まで。

詳細については、 **nonextensible**属性と例を参照してください[nonextensible](../windows/nonextensible.md)します。

## <a name="see-also"></a>関連項目

[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

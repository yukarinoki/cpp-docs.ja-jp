---
title: nonextensible 属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1112f533e2e38dd90b1693e8bd31e5896ebca5e7
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848438"
---
# <a name="nonextensible-attribute"></a>nonextensible 属性
かどうかは、デュアル インターフェイスは実行時に拡張できません (つまり、メソッドまたはプロパティを使用してを提供しません`IDispatch::Invoke`は、vtable を使用して使用できません)、適用する必要があります、 **nonextensible**属性のインターフェイスを定義。 この属性は、コンパイル時に完全なコードの検証を有効にするために使用する (Visual Basic) などのクライアント言語に情報を提供します。 この属性が指定されていないバグが非表示のままクライアント コードで実行時まで。  
  
 詳細については、 **nonextensible**属性と例を参照してください[nonextensible](../windows/nonextensible.md)します。  
  
## <a name="see-also"></a>関連項目  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)


---
title: _variant_t::Attach |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93c4ec0b4d25f1ca0ec03d9aae1dd9e1c16b79a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft 固有の仕様**  
  
 アタッチ、**バリアント**オブジェクトに、`_variant_t`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *varSrc*  
 A**バリアント**オブジェクトにアタッチされる`_variant_t`オブジェクト。  
  
## <a name="remarks"></a>コメント  
 所有権を取得、**バリアント**によってカプセル化しています。 このメンバー関数は、既存のカプセル化を解放**バリアント**、指定されたコピー**バリアント**、設定とその**VARTYPE**に`VT_EMPTY`を確認する、リソースを解放することができますのみ、`_variant_t`デストラクターです。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)
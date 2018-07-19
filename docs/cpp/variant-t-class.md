---
title: _variant_t クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70a3406d53296c778eba2ce9a6794afac2c846bd
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939807"
---
# <a name="variantt-class"></a>_variant_t クラス
**Microsoft 固有の仕様**  
  
 `_variant_t` オブジェクトは、`VARIANT` データ型をカプセル化します。 クラスがリソースの割り当てと解放を管理し、関数の呼び出し`VariantInit`と`VariantClear`に応じて。  
  
### <a name="construction"></a>構築  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|`_variant_t` オブジェクトを構築します。|  
  
### <a name="operations"></a>オペレーション  
  
|||  
|-|-|  
|[添付](../cpp/variant-t-attach.md)|アタッチを`VARIANT`オブジェクトを`_variant_t`オブジェクト。|  
|[クリア](../cpp/variant-t-clear.md)|カプセル化されたクリア`VARIANT`オブジェクト。|  
|[ChangeType](../cpp/variant-t-changetype.md)|型を変更、`_variant_t`オブジェクトを指定された`VARTYPE`します。|  
|[デタッチ](../cpp/variant-t-detach.md)|カプセル化されたデタッチ`VARIANT`オブジェクトからこの`_variant_t`オブジェクト。|  
|[SetString](../cpp/variant-t-setstring.md)|この `_variant_t` オブジェクトに文字列を代入します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../cpp/variant-t-operator-equal.md)|既存の `_variant_t` オブジェクトに新しい値を代入します。|  
|[演算子 = =、! =](../cpp/variant-t-relational-operators.md)|2 つの `_variant_t` オブジェクトを比較して、等しいかどうかを確認します。|  
|[エクス トラクター](../cpp/variant-t-extractors.md)|カプセル化されたデータを抽出`VARIANT`オブジェクト。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<comutil.h >  
  
 **Lib:** comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)
---
title: raw_native_types |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_native_types
dev_langs:
- C++
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5baa3204b14da53f6a6a3232874e0ac7de0fd91b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="rawnativetypes"></a>raw_native_types
**C 固有の仕様**  
  
 高レベルのラッパー関数の COM サポート クラスの使用を無効にし、代わりに低レベルのデータ型の使用を強制します。  
  
## <a name="syntax"></a>構文  
  
```  
raw_native_types  
```  
  
## <a name="remarks"></a>コメント  
 既定では、高レベルのエラー処理メソッドは COM サポート クラスを使用して[_bstr_t](../cpp/bstr-t-class.md)と[_variant_t](../cpp/variant-t-class.md)の代わりに、`BSTR`と**バリアント**データ型と生の COM インターフェイス ポインター。 これらのクラスは、これらのデータ型のメモリ ストレージの割り当てと解放の詳細情報をカプセル化し、型キャストと変換演算を大幅に簡略化します。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
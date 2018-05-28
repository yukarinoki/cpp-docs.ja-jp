---
title: no_injected_text |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74336ffaa5e1f9f1990acedf1669526c9152b82b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="noinjectedtext"></a>no_injected_text
コンパイラがコードの属性を使用した結果として挿入するを防ぎます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 `boolean`(省略可能)  
 **true**しない場合、挿入されたコード**false**挿入するコードを許可します。 **true**既定値です。  
  
## <a name="remarks"></a>コメント  
 最も一般的な使用、 **no_injected_text** C++ 属性は、 [/Fx](../build/reference/fx-merge-injected-code.md)コンパイラ オプションは、挿入、 **no_injected_text** .mrg ファイル属性。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意の場所|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ属性](../windows/compiler-attributes.md)   

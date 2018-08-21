---
title: _bstr_t::GetAddress |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eaa3921d0f1f89df11cf5e3809c9e90e4a03dd3b
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408467"
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Microsoft 固有の仕様**  
  
 既存の文字列を解放し、新しく割り当てられた文字列のアドレスを返します。  
  
## <a name="syntax"></a>構文  
  
```  
BSTR* GetAddress( );  
```  
  
## <a name="return-value"></a>戻り値  
 `BSTR` でラップされた `_bstr_t` へのポインター。  
  
## <a name="remarks"></a>Remarks  
 **GetAddress**すべて影響`_bstr_t`オブジェクトをその共有を`BSTR`します。 1 つ以上`_bstr_t`を共有できる、`BSTR`コピー コンス トラクターを使用してとおよび**演算子 =** します。  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)の例を使用して、 **GetAddress**します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)
---
title: _bstr_t::Detach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: cc8284bd-f68b-4fff-b2e6-ce8354dabf8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8b7bc86ae487843f925668bccfbfd8e67b8685
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940252"
---
# <a name="bstrtdetach"></a>_bstr_t::Detach
**Microsoft 固有の仕様**  
  
 `BSTR` でラップされた `_bstr_t` を返し、`BSTR` から `_bstr_t` をデタッチします。  
  
## <a name="syntax"></a>構文  
  
```  
  
BSTR Detach( ) throw;  
  
```  
  
## <a name="return-value"></a>戻り値  
 `BSTR` によってラップされる `_bstr_t`。  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)の例を使用して、`Detach`します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)
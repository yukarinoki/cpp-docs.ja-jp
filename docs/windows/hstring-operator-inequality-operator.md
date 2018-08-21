---
title: Hstring::operator! = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
dev_langs:
- C++
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3fabc0dcbbc31a1707d1823fb1ec49a53aca6d3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015876"
---
# <a name="hstringoperator-operator"></a>HString::Operator!= 演算子
2 つのパラメーターが異なるかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator!=( const HString& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HStringReference& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
                        const HStringReference& rhs) throw()  
  
inline bool operator!=( const HSTRING& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
                        const HSTRING& rhs) throw()  
```  
  
### <a name="parameters"></a>パラメーター  
 *lhs*  
 比較する最初のパラメーター。 *lhs*できます、 **HString**または`HStringReference`オブジェクト、または、HSTRING ハンドル。  
  
 *rhs*  
 比較する 2 番目のパラメーター。*rhs*できます、 **HString**または`HStringReference`オブジェクト、または、HSTRING ハンドル。  
  
## <a name="return-value"></a>戻り値  
 **true**場合、 *lhs*と*rhs*パラメーターが、それ以外の**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)
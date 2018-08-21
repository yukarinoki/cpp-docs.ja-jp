---
title: _bstr_t::operator = |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dfed780e0769e342ff368af453fc70764a372f0
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404474"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Microsoft 固有の仕様**  
  
 既存の `_bstr_t` オブジェクトに新しい値を代入します。  
  
## <a name="syntax"></a>構文  
  
```  
_bstr_t& operator=(const _bstr_t& s1) throw ( );  
_bstr_t& operator=(const char* s2);  
_bstr_t& operator=(const wchar_t* s3);  
_bstr_t& operator=(const _variant_t& var);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *s1*  
 既存の `_bstr_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。  
  
 *s2*  
 既存の `_bstr_t` オブジェクトに割り当てられるマルチバイト文字列。  
  
 *s3*  
 既存の `_bstr_t` オブジェクトに割り当てられる Unicode 文字列。  
  
 *var*  
 既存の `_variant_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)の使用例については**演算子 =** します。  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)
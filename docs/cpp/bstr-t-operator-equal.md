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
ms.openlocfilehash: 43e28aa7d7b3682c45f4f8b7a94e990374d83b46
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943141"
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
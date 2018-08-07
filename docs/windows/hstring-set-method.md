---
title: Hstring::set メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs:
- C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aecdafe81dcebc7867d30c46be1fee271e60154c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606398"
---
# <a name="hstringset-method"></a>HString::Set メソッド
現在の値を設定**HString**ワイド文字の文字列を指定するオブジェクトまたは**HString**パラメーター。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Set(  
          const wchar_t* str) throw();  
HRESULT Set(   
          const wchar_t* str,   
          unsigned int len  
           ) throw();  
HRESULT Set(  
          const HSTRING& hstr  
           ) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *str*  
 ワイド文字の文字列。  
  
 *len*  
 最大長、 *str*パラメーターに現在割り当てられている**HString**オブジェクト。  
  
 *hstr*  
 既存の**HString**オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)
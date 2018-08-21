---
title: Hstring::copyto メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 28ec7e7840d3fd3a23e7b65fe6c46ce9cbc244c3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017579"
---
# <a name="hstringcopyto-method"></a>HString::CopyTo メソッド
現在のコピー **HString**オブジェクトを HSTRING オブジェクトにします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *str*  
 コピーを受信する HSTRING です。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、 [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx)関数。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)
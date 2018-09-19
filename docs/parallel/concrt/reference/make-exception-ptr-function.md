---
title: make_exception_ptr 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ppltasks/std::make_exception_ptr
dev_langs:
- C++
ms.assetid: 8d81cf7a-818e-4b27-8d49-440ec3088609
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3f483d266b8150dfd4aaa5299ffec280d447157
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037620"
---
# <a name="makeexceptionptr-function"></a>make_exception_ptr 関数
## <a name="syntax"></a>構文  
  
```
template<class _E>
exception_ptr make_exception_ptr(_E _Except);
```  
  
#### <a name="parameters"></a>パラメーター  
*_E*<br/>
例外の種類。

*_Except*<br/>
例外の値。
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [std 名前空間](std-namespace.md)

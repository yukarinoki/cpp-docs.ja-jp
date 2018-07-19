---
title: _com_ptr_t::Release |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a8a734eae486ca5e88009301b13d71b21473d9f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939257"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Microsoft 固有の仕様**  
  
 呼び出し、`Release`のメンバー関数`IUnknown`カプセル化されたインターフェイス ポインター。  
  
## <a name="syntax"></a>構文  
  
```  
  
void Release( );  
  
```  
  
## <a name="remarks"></a>Remarks  
 呼び出し`IUnknown::Release`カプセル化されたインターフェイス ポインターでこのインターフェイス ポインターが NULL の場合は E_POINTER エラーを発生します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
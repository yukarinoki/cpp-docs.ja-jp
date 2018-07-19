---
title: _com_ptr_t::AddRef |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40ed48b54a3862f7ac5804e7652d98b661bb071d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940993"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Microsoft 固有の仕様**  
  
 呼び出し、`AddRef`のメンバー関数`IUnknown`カプセル化されたインターフェイス ポインター。  
  
## <a name="syntax"></a>構文  
  
```  
  
void AddRef( );  
  
```  
  
## <a name="remarks"></a>Remarks  
 呼び出し`IUnknown::AddRef`カプセル化されたインターフェイス ポインターでポインターが NULL の場合は E_POINTER エラーを発生します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
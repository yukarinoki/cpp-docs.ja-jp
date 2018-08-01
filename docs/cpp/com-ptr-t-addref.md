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
ms.openlocfilehash: 4bf56e87b8b7949048b1e6006d3aa32f00af1462
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404260"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Microsoft 固有の仕様**  
  
 呼び出し、`AddRef`のメンバー関数`IUnknown`カプセル化されたインターフェイス ポインター。  
  
## <a name="syntax"></a>構文  
  
```  
void AddRef( );  
```  
  
## <a name="remarks"></a>Remarks  
 呼び出し`IUnknown::AddRef`、カプセル化されたインターフェイス ポインターで発生させる、`E_POINTER`ポインターが NULL の場合のエラー。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
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
ms.openlocfilehash: 1c5da56c3c85c17bcd2cd91f9fa5a5f8399e9528
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404276"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Microsoft 固有の仕様**  
  
 呼び出し、**リリース**のメンバー関数`IUnknown`カプセル化されたインターフェイス ポインター。  
  
## <a name="syntax"></a>構文  
  
```  
void Release( );  
```  
  
## <a name="remarks"></a>Remarks  
 呼び出し`IUnknown::Release`、カプセル化されたインターフェイス ポインターで発生させる、`E_POINTER`このインターフェイス ポインターが NULL の場合のエラー。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
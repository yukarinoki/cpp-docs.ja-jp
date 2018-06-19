---
title: _com_ptr_t::AddRef |Microsoft ドキュメント
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
ms.openlocfilehash: 54a1b629f254bae2b72790546bcbb00185f2c44c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409775"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Microsoft 固有の仕様**  
  
 呼び出し、`AddRef`のメンバー関数**IUnknown**カプセル化されたインターフェイス ポインター。  
  
## <a name="syntax"></a>構文  
  
```  
  
void AddRef( );  
  
```  
  
## <a name="remarks"></a>コメント  
 呼び出し`IUnknown::AddRef`カプセル化されたインターフェイス ポインターでさせると、`E_POINTER`ポインターがある場合はエラー **NULL**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
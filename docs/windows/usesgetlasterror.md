---
title: usesgetlasterror |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 011cf954a0b111e46afcaf6e55a54914075864db
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014563"
---
# <a name="usesgetlasterror"></a>usesgetlasterror
呼び出し元に通知する関数を呼び出すときにエラーがある場合、呼び出し元ことができますし`GetLastError`エラー コードを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[usesgetlasterror]  
```  
  
## <a name="remarks"></a>Remarks  
 **Usesgetlasterror** C++ 属性と同じ機能を持つ、 [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL 属性。  
  
## <a name="example"></a>例  
 参照してください、 [idl_module](../windows/idl-module.md)を使用する方法のサンプルについては、例**usesgetlasterror**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**モジュール**属性|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
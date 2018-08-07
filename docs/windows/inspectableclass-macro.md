---
title: InspectableClass マクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a02e20f2b87afc312c24683417f808d636c2757f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608957"
---
# <a name="inspectableclass-macro"></a>InspectableClass マクロ
ランタイム クラス名と信頼レベルを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
### <a name="parameters"></a>パラメーター  
 *runtimeClassName*  
 ランタイム クラス名のテキスト形式の完全な名前です。  
  
 *trustLevel*  
 1 つ、 [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx)列挙値。  
  
## <a name="remarks"></a>Remarks  
 **InspectableClass**マクロは、Windows ランタイム型でのみ使用できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)
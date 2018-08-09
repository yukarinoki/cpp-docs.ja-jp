---
title: ImplementsHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs:
- C++
helpviewer_keywords:
- ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eca429578fd9b58a2a3229199d53812a494af045
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018349"
---
# <a name="implementshelper-structure"></a>ImplementsHelper 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
### <a name="parameters"></a>パラメーター  
 *RuntimeClassFlagsT*  
 1 つまたは複数を指定するフラグのフィールド[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙子。  
  
 *ILst*  
 インターフェイスの Id の一覧。  
  
 *IsDelegateToClass*  
 指定**true**場合の現在のインスタンス`Implements`で最初のインターフェイス ID の基底クラスは、 *ILst*、それ以外の**false**。  
  
## <a name="remarks"></a>Remarks  
 により、実装、[実装](../windows/implements-structure.md)構造体。  
  
 このテンプレートは、インターフェイスのリストを走査し、基本クラス、および有効にするために必要な情報として追加`QueryInterface`します。  
  
## <a name="members"></a>メンバー  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ImplementsHelper`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [リファレンス (Windows ランタイム ライブラリ)](http://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)
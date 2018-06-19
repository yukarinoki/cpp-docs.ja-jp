---
title: IsBaseOfStrict 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db8f315c0589ceb7cd9411873152fe644985818e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876892"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 基本データ型。  
  
 `Derived`  
 派生型です。  
  
## <a name="remarks"></a>コメント  
 一方の型がもう一方の型の基本クラスであるかどうかをテストします。  
  
 最初のテンプレートは、型が生じる場合、基本型から派生したかどうかを検査**true**または**false**です。 2 番目のテンプレートは、型から派生して、それ自体が常に生成されるかどうかを検査**false**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[IsBaseOfStrict::value 定数](../windows/isbaseofstrict-value-constant.md)|1 つの種類別のベースであるかどうかを示します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)